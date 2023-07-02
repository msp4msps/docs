# Leveraging the Pax8 API in Power Automate

If you are an MSP working with Pax8 today, I believe you should be leveraging their API to automate workflows from a procurement and subscription management perspective. Many Pax8 partners don’t know Pax8 has an API but essentially it can be used at no additional cost and has the following endpoints:

* Customers
* Orders (Purchase net new)
* Subscriptions (Allows you to increment/decrement seats)
* Products (View catalog info and rate plans)
* Contacts
* Invoices
* Usage Summaries (think Azure Billing)

There is a ton you can do here with this API. Most commonly, you might think of adding this as part of a user onboard/offboard process where you are modifying seat counts. You might also take this a step further and integrate directly into QuickBooks Online or some other ERP where you bill out today instead of relying on Pax8’s fixed set of integrations. That is the great part about a vendor being open.

**Real-Life Example**

I personally rely on many workflows generated from Power Automate because of the no code/low code benefits. Right now, I have created a flow with Pax8’s API to automatically generate tickets in PSA when an NCE subscription is coming up for renewal. This allows my team to evaluate the license count before we are locked in again with these strict contract terms. **This provides a ton of value since we have disparate renewal dates for NCE subscriptions on a per customer level currently.**

In this article I will be showing you how to connect to the Pax8 API via Power Automate so hopefully you can start doing some cool things as well.

If you are interested in using Pax8 API as a powershell wrapper, shoutout to Luke Whitelock who has created and published that on github: [lwhitelock/Pax8API: This is a powershell module used to access the Pax8 API (github.com)](https://github.com/lwhitelock/Pax8API)

### Prerequisites

On the Pax8 Side:

* Get a client ID and Client Secret:
  * As a **Primary Partner Admin** or **Partner Admin** => Go to Tools>Partner Shells and find **Pax8 Partner API Partner Shell**

![](https://tminus365.com/wp-content/uploads/2022/08/pic1-1.png)

* Fill out the fields and submit. Once you do you will get info about the API docs. You can always find the API docs up in the right-hand corner under the ? icon

![](https://tminus365.com/wp-content/uploads/2022/08/pic2-1.png)

* Click on your name in the right-hand corner>User Settings>Developer Apps>Create

![](https://tminus365.com/wp-content/uploads/2022/08/pic15-1.png)

* Give it a name of your choosing>Click Create
* You will be given a ClientID and Secret. Store these in a secure location like Azure Key Vault, IT Glue, etc.

**On the Microsoft side:**

* **Premium license on Power Platform**
  * As you will see later in the Power Automate flow, we are going to be using Premium Actions (HTTP request) to get access tokens and call the Pax8 API.
  * Power Platform licensing is confusing but one of the following plans below will get you what you need and technically, you only need one of these licenses.
* &#x20;

![](https://tminus365.com/wp-content/uploads/2022/08/pic3.png)

**\*\*If you are a Silver or Gold member in Microsoft’s Partner Program, it is possible you are already getting these licenses as part of your IURs.**

* **Azure Key Vault(Optional)**
  * Personally, I like to store my ClientID and Secret here so I can populate them dynamically in the flow. There are other ways you can do this outside of Key Vault but this will be what I show in the example.

### The Steps

Normally, I would recommend that you would set Pax8 up as a custom connector in Power Automate, much like I showed doing so in this article: [Creating Syncro as a Custom Connector in Power Automate – (tminus365.com)](https://tminus365.com/creating-syncro-as-a-custom-connector-in-power-automate/)  where we connected Synco. Unfortunately, Pax8’s API uses client credentials for the grant type to create a new accessToken which isn’t currently supported for custom connectors. This basically inhibits our ability to authenticate if we were going to try to build that flow. For this reason, you have to make calls to get access tokens directly within the flow itself. Let’s do that now:

1. Navigate to [https://make.powerautomate.com/](https://make.powerautomate.com/)
2. Click Create>Instant Cloud Flow

3\. Give it a name and chose Manually trigger a flow (this is just for testing and the purposes of this example, you could give this any trigger you want.)

![](https://tminus365.com/wp-content/uploads/2022/08/pic4-1.png)

4\. We will be using our ClientID and Secret to get a new access token during the flow. For security purposes it is best not to expose those in plain text. For this reason I have stored them in Azure Key Vault so we can populate them dynamically. Click New Step>Search **Azure Key Vault**>Click **Get Secret** under actions

![](https://tminus365.com/wp-content/uploads/2022/08/pic5-1.png)

5\. Populate your Client ID

![](https://tminus365.com/wp-content/uploads/2022/08/pic6-1.png)

Pro Tip If you are getting an error message about not being able to connect to a vault, click on Connectors on the left navigation page and edit your key vault connection here. In my experience, I was not able to select the vault after signing in and I only got the error from the flow screen.

6\. Perform the same step to add the Secret

![](https://tminus365.com/wp-content/uploads/2022/08/pic7-1.png)

7\. Click New Step>Search HTTP >Choose HTTP under actions&#x20;

![](https://tminus365.com/wp-content/uploads/2022/08/screenshot1.png)

8\. Here we are going to make the POST call to get the Access Token per the Pax8 API documentation. (Remember you can view this from their portal). Add the URL and the body directly by copying it from the documentation.&#x20;

![](https://tminus365.com/wp-content/uploads/2022/08/pic9-1.png)

10\. Adjust the body to populate the client\_id and client\_secret with your dynamic values coming from Azure Key Vault. Add the header of Content-Type. &#x20;

![](https://tminus365.com/wp-content/uploads/2022/08/pic10-1.png)

11\. Now we need to Parse out the JSON to get the access-token used to make other calls. Search for this value in the next step and chose Parse JSON&#x20;

![](https://tminus365.com/wp-content/uploads/2022/08/pic11-1.png)

12\. For the Content section, dynamically populate the Body Value from the previous step. Copy the Access Token response example from the Pax8 API documentation>Click on Generate from Sample back in the Power Automate flow>Paste in the value. The schema will be generated from this sample.&#x20;

![](https://tminus365.com/wp-content/uploads/2022/08/screenshot2.png)

13\. Now we can make calls to all other API endpoints because we have an accessToken. Here we will just call the company endpoint to test. Select the HTTP action for the next step. Again, use the Pax8 API documentation to populate these records. We will use the **Fetch a paginated list of your companies GET request**. One of the headers we add is Authorization. Here will we dynamically add our access\_Token with the following format “Bearer \<space>\<AccessToken>”&#x20;

![](https://tminus365.com/wp-content/uploads/2022/08/pic13-1.png)

14\. Save the flow and Run a Test. Here we can see the flow run successfully and the output of our company records. &#x20;

![](https://tminus365.com/wp-content/uploads/2022/08/pic14-1.png)

### Conclusion

So that is it! You can use the Parse JSON action to pull out values from these calls and dynamically populate them in other steps. I will post future article showing more examples leveraging the API in future content. Post any questions to the YouTube video:
