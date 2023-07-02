# GDAP Migration with Microsoft 365 Lighthouse

A few months ago, I [published a video](https://tminus365.com/gdap-bulk-migration-demo-cipp-vs-microsoft/) showcasing a comparison of the GDAP migration tools available. Since that time, the Microsoft 365 Lighthouse team has introduced a new migration tool for GDAP to help partners streamline the move, in bulk, across customers. If you watched my previous comparison video, you saw how clunky the old solution was using a CLI and CSVs. The lighthouse team has been working behind the scenes to create a tool that is much more user friendly and catered to the MSP space. In this article, I will be covering key highlights of the tool and giving you an overall comparison when it comes to this tool, CIPP, and the previous bulk migration tool.

### GDAP Timelines

A couple of key dates are coming up which increases the urgency of you adopting a bulk migration tool for GDAP if you have not already.

&#x20;Starting January 17, 2023

* Microsoft will stop creating DAP relationships when a new customer or reseller relationship is created.
* Microsoft will start removing inactive DAP relationships that haven’t been used in 90 days.

Starting March 1, 2023

* The Bulk Migration Tool to upgrade existing DAP connections that were granted by customers to GDAP will no longer be available.
* Microsoft will begin to transition remaining active DAP relationships to GDAP with limited Azure Active Directory (Azure AD) roles to perform least-privilege customer management activities. Partners will be required to perform more steps to continue to have access to Azure subscriptions after the limited roles are granted, as documented.

**A key piece to note here is that the new Lighthouse migration tool will STILL be available after March 1st.** The main difference is that you will not be able to automatically transition your active DAP relationships to GDAP. After the March 1st date, if you use the tool, you will get a GDAP relationship link per tenant that you will manually need to accept on a per customer basis. You will want to avoid that to save some time on the initial move.

### Prerequisites

* To run the tool, you need to be a Global Admin
* There are no customer eligibility requirements. A tenant with any type of licensing will be available to select from in the tool.
* AAD P2 licensing is required to use the JIT features/functionality
* Documentation for this tool can be found here: [Set up GDAP for your customers – Microsoft 365 Lighthouse | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/lighthouse/m365-lighthouse-setup-gdap?wt.mc\_id=365admincsh\_lighthouse\&view=o365-worldwide)

### Using the Tool

![](https://tminus365.com/wp-content/uploads/2022/12/pic1-1.png)

In the wizard, you get predefined tiers that are recommendations on partitioning out the various Azure AD roles within your organization. I believe this is one of the best parts of the tool. You are able to rename the tiers to better match your organization and unselect some of the recommendations if it is an Azure AD role you are not going to use.

![](https://tminus365.com/wp-content/uploads/2022/12/pic2-2.png)

Next, you are able to create GDAP templates and apply one to many tiers to those templates. For our MSP, we use two templates, License Only and Managed Services, to bucketize our permissions. Our license only customers require significantly less permissions than our managed service customers

![](https://tminus365.com/wp-content/uploads/2022/12/pic3-1.png)

Security Group creation is next. You will be creating a new security group for at least each tier you want to use in your environment. The wizard steps you through each of your templates so you can associate the proper security groups. In the example I show below, we also see some additional settings for the **JIT** tier. Just-in-time access is much like PIM but it allows you to have even more security for higher privileged roles like Global Admins, Application Admins, etc. I believe that a JIT/PIM solution is very important to combine with GDAP. Behind the scenes, Lighthouse will create an **Access Package** in your Azure AD environment with the settings you define in this wizard

![](https://tminus365.com/wp-content/uploads/2022/12/pic4.png)

The final section is associating your templates to one or many customers

![](https://tminus365.com/wp-content/uploads/2022/12/pic5.png)

Once you are done, you will get a summary to review and then a status page with the customers that have successfully added a GDAP relationship

![](https://tminus365.com/wp-content/uploads/2022/12/pic6.png)

If you go into Partner Center and search for one of the companies you set up a relationship for, you will see the GDAP relationship listed under the Admin Relationships section

![](https://tminus365.com/wp-content/uploads/2022/12/pic7.png)

### Comparison

![](https://tminus365.com/wp-content/uploads/2022/12/pic8.png)

This diagram is a bit biased towards Lighthouse but I do believe it offers the most comprehensive solution for a migration tool.

* Templates can be created in the bulk migration tool but it is manual with CSVs
* Group Creation is done in both CIPP and Lighthouse but in CIPP you are creating one group per Azure AD role. This can make things a little messy in your tenant from the amount of groups that you are creating. Lighthouse allows you to consolidate those groups and reuse them across templates/roles
* Suggested roles is the #1 feature of Lighthouse in my opinion
* Native PIM/JIT support is only available in Lighthouse. You can do this with the bulk migration tool,but you would have to manually set up the JIT/PIM groups as a prerequisite
* CIPP and Lighthouse are both very easy to use

### Conclusion

If you haven’t started the move to GDAP today, I would highly recommend leveraging the Lighthouse migration tool. I had the privilege of working with the Lighthouse team during earlier phases of the rollout and was very happy to see their level of attention to the MSP space. They are also working on functionality that will provide for the longer-term management of GDAP relationships which I am very excited about.
