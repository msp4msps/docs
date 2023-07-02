# Custom Connector in Power Automate

As an MSP, you should be constantly trying to automate workflows. Power Automate allows you to create workflows across applications with basic triggers and actions. Custom connectors can be established and used as part of your flows. In this article, I will show you how to set up a custom connector for Syncro using their Rest APIs. As an example, I will show you how to create a ticket as an action after setting up the custom connector. These workflows allow you to trigger events in your customer tenants to then create action in your Syncro environment. Triggers can also be set up from Syncro, such as a new contact being created, that generate actions in Microsoft (new user created in Azure AD).

### Prerequisites

It should be noted that this is a more advanced deployment because we are interacting with APIs to create this connection and establish triggers/actions. If you do not have experience in this regard, this may not be worth your time. Here are the other prerequisites I would mention:

* Power Automate subscription per customer (we will be setting up these custom connectors in customer environments. Power Automate comes with most 365 plans.)&#x20;
* An [API key](https://help.syncromsp.com/hc/en-us/articles/360048794414-API-Tokens) created in your Syncro Environment with the necessary permissions for the actions you want to create in Power Automate (i.e. Tickets-Create if you want to create new tickets)
* Access/Knowledge of [Syncro’s Rest API](https://api-docs.syncromsp.com/)
* Postman
  * I like to use postman to test out the API in my environment and grab the necessary IDs we will need to execute our actions (like creating a new ticket)

### Steps

Login to power automate and select Data>Custom Connectors

![](https://tminus365.com/wp-content/uploads/2021/07/pic1.png)

Select **+New Custom Connector>Create from Blank**

![](https://tminus365.com/wp-content/uploads/2021/07/pic2.png)

* Upload an Image (Optional)
* Provide a description (optional)
* In the host section provide the URL that you use to sign in.&#x20;
* In the Base URL add **/api/v1**
* When you are done, click Security ->

![](https://tminus365.com/wp-content/uploads/2021/07/pic3.png)

* Choose API key for the authentication Type.&#x20;
* Enter a parameter label of **api-key**
* For Parameter name enter Authorization
* Click Definition ->

![](https://tminus365.com/wp-content/uploads/2021/07/pic4.png)

Definitions allow you to define actions or triggers in Syncro. In this example, I will show you how to create a ticket as an action. Note that you can make as many actions or triggers as you would like. Start by selecting +New Action and adding the following:

![](https://tminus365.com/wp-content/uploads/2021/07/pic5.png)

* Next, under **Request** select **+Import from Sample.**
* Select post&#x20;
* For the url enter the format of https://yourSubdomain.syncromsp.com/api.v1/tickets
  * Note that this request URL is specific to tickets&#x20;
* In the body you can copy and paste the example value for a post request in Syncro’s API documentation. Here you can determine what fields you would want to have when you create a support ticket. Some of these fields are required like subject, customer\_id, body. This is why I like to use postman to test out the APIs to know exactly what I will need. Additionally, if you have specific use cases in mind for workflows that will use this action, you may just want to add the fields in the body that you would want in the ticket to avoid any clutter
* When you have the body entered, click Import

![](https://tminus365.com/wp-content/uploads/2021/07/pic7-1.png)

![](https://tminus365.com/wp-content/uploads/2021/07/pic6.png)

Now that we entered our request template we can modify the headers and body to add specific information. This is useful when you want static fields that never change. These can be prepopulated with the exact info you want and you can customize them so that they cannot be changed when setting up the action. In this example we will modify the content-type and customer\_ID.&#x20;

Click the 3 dots next to Content-Type and click **Edit**

![](https://tminus365.com/wp-content/uploads/2021/07/pic9.png)

When you modify these fields you can define the default values, make them required, and set them to internal so that no one can change them later. Fill out Content-Type as you see below:

![](https://tminus365.com/wp-content/uploads/2021/07/pic8.png)

When you are done click on the back arrow and then click edit on the body. In the body section you will see all of the fields you added to your JSON. Click on edit for the customer ID. here is where will will also use postman to get the correct customer ID as a prepopulated value in the ticket. This customer should match the customer tenant you are in creating this custom connector.&#x20;

![](https://tminus365.com/wp-content/uploads/2021/07/pic12.png)

Use the customers call to see the unique IDs of your customers in Postman

![](https://tminus365.com/wp-content/uploads/2021/07/pic11.png)

Before you move on to testing, you may want to modify Body and subject as additional fields that are required for the input of the action. For tickets, you will also note that you will have two subjects, one for the main part of the ticket and another for the first comment that is being made. For this reason, you may want to distinguish one with a Default value or title.&#x20;

![](https://tminus365.com/wp-content/uploads/2021/07/pic10.png)

Once you have all fields saved, click **Create Connector**

![](https://tminus365.com/wp-content/uploads/2021/07/pic13.png)

You will receive a success message and now you will want to click on **Test > +New Connetion**

![](https://tminus365.com/wp-content/uploads/2021/07/pic14.png)

Here you will be asked to enter the api key that you created/grabbed in the prerequisites. When you enter the correct format click Create Connection

Important! The format of this entry is extremely important. You will want to put in Bearer (insert API key) into this text field. Again the format is Bearer space API key

![](https://tminus365.com/wp-content/uploads/2021/07/pic15.png)

On the following page, click the refresh button to see the connection you just set up.

![](https://tminus365.com/wp-content/uploads/2021/07/pic16.png)

Below you will see all of the fields you entered of the JSON body. Here you can enter values as an example to test the operation. Fill out the fields and click **Test operation**&#x20;

![](https://tminus365.com/wp-content/uploads/2021/07/pic17.png)

If successful, you will see a 200 status and the body of the ticket you just created. If you get an error it is likely that you either:

1. Did not fill out the necessary fields required for this API call. In this case, you would get an error stated whatever field that is required (i.e. Subject)
2. You get an unauthorized error message which means you either entered your API key in incorrectly or you did not give your API key the necessary permissions in Syncro for the API call you are trying to make.&#x20;

![](https://tminus365.com/wp-content/uploads/2021/07/pic18.png)

Back in Syncro, you can see the ticket that was just generated off of the test event

![](https://tminus365.com/wp-content/uploads/2021/07/pic19.png)

Here you can see all of the fields I entered in power automate that were generated.&#x20;

![](https://tminus365.com/wp-content/uploads/2021/07/pic20-1024x476.png)

Now when you go to create a flow, you can select **Custom** to see your custom connector. Clicking into the connector will allow you to see all of the actions and triggers you have created

![](https://tminus365.com/wp-content/uploads/2021/07/pic21.png)

![](https://tminus365.com/wp-content/uploads/2021/07/pic22.png)

### Conclusion

I hope that this article provided some targeted guidance for creating Syncro as a custom connector in Power Automate. If you are interested in any consulting services to help set this connector up, feel free to [contact me here.](https://tminus365.com/contact/)
