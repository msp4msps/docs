# Leveraging the Huntress API in Power Automate

Many of you may be using the native integrations within Huntress today to automate certain flows to your PSA tool like:

* Writing subscription information to agreements/contracts
* Creating tickets when new incidents occur

The [Huntress API](https://api.huntress.io/docs) provides access to various endpoints that you can leverage for even more automation capabilities. In this article, I will show you how to set up Huntress as a custom connector in Power Automate so you can begin to create your own custom automation flows. You can get creative but here are some reasons why you would want to set this up:

* To chain more automation around when incidents occur
* To facilitate subscription information to 3rd party tools that Huntress does not integrate with natively today (Like QuickBooks)
* To aggregate subscription and device information across vendors.&#x20;

I am currently using it to perform the aggregations:&#x20;

![](https://tminus365.com/wp-content/uploads/2022/09/pic1-4-1024x569.png)

This is a Power BI report in which we can see device information across vendors. I wanted see if there were any disparities between what is reporting out of Intune, our RMM, and Huntress. Additionally, I wanted to pull in subscription information so I can aggregate it at a customer level.&#x20;

![](https://tminus365.com/wp-content/uploads/2022/09/pic2-4.png)

### Prerequisites

* API Credentials with Huntress
  * In the huntress portal, go API Credentials to generate a API Key and API Secret
* Premium Power Platform subscription.
  * Licensing can get confusing here but I recommend one of the following: (Also you may be getting these licenses as part of your Silver or Gold Partnership with Microsoft)

![](https://tminus365.com/wp-content/uploads/2022/08/pic3.png)

### The Steps

1\. Go to https://make.powerautomate.com/ > Data>Custom Connectors>+New Custom Connector>Create from blank

2\. You can upload the Huntress Logo and add the following info:

![](https://tminus365.com/wp-content/uploads/2022/09/pic4-7.png)

3\. On the Security Page, select Basic Authentication. Add the labels of APIKey and APISecret. You will not add your information yet on this page, these are just labels:

![](https://tminus365.com/wp-content/uploads/2022/09/pic5-4.png)

4\. For the Definitions, you will add the Endpoints you want to leverage in your Power Automate flows.&#x20;

![](https://tminus365.com/wp-content/uploads/2022/09/pic6-1.png)

Follow the API documentation to add the correct request URL. You can add parameters as well too if you want. At a minimum, you might want to add the page parameter to facilitate pagination for endpoints that return multiple pages (which is very common with the API).&#x20;

![](https://tminus365.com/wp-content/uploads/2022/09/pic7-1.png)

5\. Go to the Test tab, click on + New Connection. Here you will enter your Huntress API Key and Secret

![](https://tminus365.com/wp-content/uploads/2022/09/pic8-1.png)

![](https://tminus365.com/wp-content/uploads/2022/09/pic9-1.png)

6\. After the connection is entered you will be redirected back to the Test page. Here you can click on the refresh button to generate the connection you just created.

![](https://tminus365.com/wp-content/uploads/2022/09/pic10-1.png)

7\. Finally, you can test the connection by selecting an operation and clicking Test Operation

![](https://tminus365.com/wp-content/uploads/2022/09/pic11-1.png)

8\. If successful, you will get a 200 response.

9\. Create the Connector

10\. Now when you go to create a flow, you will have the Huntress connector as an option under Custom. All Endpoints you created under the Definitions section will be included

![](https://tminus365.com/wp-content/uploads/2022/09/pic12-1.png)

Happy Automating! For the full tutorial, check out my YouTube Video. Feel free to leave any questions or comments on the video:
