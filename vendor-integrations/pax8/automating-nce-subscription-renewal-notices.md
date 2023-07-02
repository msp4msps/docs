# Automating NCE subscription renewal notices

Microsoft New Commerce introduced a new level of liability because of their commitment terms and cancellation policies. On top of that they also introduced new operational complexity through subscription renewal dates which could be different for each customer in your environment if you did not move them to NCE on the same date.

Microsoft has introduced what they call “Coterminosity”. Essentially it allows you to align end dates for customers and one of those options now is by **Calendar month charge cycle**. This means you could potentially align subscriptions more so how they used to be on legacy and how you bill out with PSA. The problem is if you were an earlier adopter of NCE and work with a distributor, its likely they haven’t gotten around to updating your renewal dates to the calendar month. Another new reality is that because of the discounted rate, many of us are using annual contracts now which can also have variable renewal dates per customer.

Finally, because of the strict cancellation/decrement window, its important that you know when renewals are coming up so that you can adjust seat counts before being locked in again. For all of these reasons, I wanted to create some automation around NCE renewals across customers.

### The Solution

Using the Pax8 API, Power Automate, and a custom connector for my PSA in Power Automate, I was able to create a flow that automatically creates a ticket in Syncro (example PSA) when a subscription is coming up for renewal.

![](https://tminus365.com/wp-content/uploads/2022/09/pic1-1.png)

![](https://tminus365.com/wp-content/uploads/2022/09/pic2-2.png)

You can get creative here, I personally want to drive action into a ticket so we **can track time and document communications.** Here are some other ideas you can think of:

* Generating a Sales Order so reps can review with customer
* Generating a Teams Message
* Generating seat Approval Notices to Customers for upcoming renewals (via email, Teams, etc)

Example in Teams:

![](https://tminus365.com/wp-content/uploads/2022/09/pic6.png)

There are also more advanced solutions you can implement as well that I have implemented that require a bit more work:

* Populating Available Counts vs Consumed Counts for the licenses into the Ticket (MS Graph API, what I did in the screenshot above)
* Populating Assigned Users (MS Graph API)
* Automatically adjusting the licensing at renewal (Meaning we leverage the Pax8 API and Graph API to reduce seat counts from Available Counts minus Consumed Counts automatically)

Ultimately, I am looking to reduce liability and make this process as touchless as possible.

### Prerequisites

* Pax8 API Client ID and Secret
* Premium Power Platform License
  * (Both of the above I outline in my previous post on [Leveraging the Pax8 API](https://tminus365.com/leveraging-the-pax8-api-in-power-automate/))
* Custom Connector for PSA (like what I [show here](https://tminus365.com/creating-syncro-as-a-custom-connector-in-power-automate/) with Synco)

### The Steps

There are many steps in Power Automate to take. For the complete list, check out my video at the bottom of the page. Here is a summary of what I am doing:

1\. Set up reoccurrence to happen daily

![](https://tminus365.com/wp-content/uploads/2022/09/pic7.png)

2\. Set the date you want to be notified. You can use a couple of expressions in Power Automate to get the current date and then add days. This allows you to get notices of upcoming renewal dates when we loop through out Pax8 subscriptions

The formula: formatDateTime(addDays(utcNow(),\<Insert Number of Days to Add>), ‘yyyy-MM-dd’)

![](https://tminus365.com/wp-content/uploads/2022/09/pic8.png)

3\. Get ClientID and Secret for Pax8 API from Azure Key Vault connector. (Showed this in my [previous article](https://tminus365.com/leveraging-the-pax8-api-in-power-automate/))

![](https://tminus365.com/wp-content/uploads/2022/09/pic9.png)

4\. Use the Secrets to create an HTTP request to get an Access token. (connector is HTTP). Parse the Access Token with the using the Pax8 API docs to generate the schema

![](https://tminus365.com/wp-content/uploads/2022/09/pic10.png)

5\. Leverage the access token to call the Subscriptions endpoint. Here we are making this call to get the total pages that return. We will use this to loop through all pages. We are doing this because the Pax8 API uses pagination. Leverage their docs again to Generate the schema for the Parse JSON action.&#x20;

![](https://tminus365.com/wp-content/uploads/2022/09/pic11.png)

6\. Use the Variable connector to create variables for Total Pages and Current Page. This is what we will use to loop through all pages. Decrement the Total Page variable by one since the Pax8 API always returns a blank page on the final page.&#x20;

![](https://tminus365.com/wp-content/uploads/2022/09/pic12.png)

7\. Create two more variables for the CustomerName and Product Name. Make them both strings and leave their values blank. We will dynamically define them later in the flow.&#x20;

![](https://tminus365.com/wp-content/uploads/2022/09/pic13.png)

8\. Next we will use the **Do Until** Control to loop through out pages.&#x20;

![](https://tminus365.com/wp-content/uploads/2022/09/pic14.png)

9\. We will make another HTTP request to get the subscriptions but setting the query parameter for pages to the current page variable since we will be looping through each page. Use the following for the Parse JSON schema:

![](https://tminus365.com/wp-content/uploads/2022/09/pic15.png)

```
{
    "type": "object",
    "properties": {
        "content": {
            "type": "array",
            "items": {
                "type": "object",
                "properties": {
                    "id": {
                        "type": "string"
                    },
                    "companyId": {
                        "type": "string"
                    },
                    "productId": {
                        "type": "string"
                    },
                    "quantity": {
                        "type": [
                            "integer",
                            "number"
                        ]
                    },
                    "startDate": {
                        "type": "string"
                    },
                    "createdDate": {
                        "type": "string"
                    },
                    "billingStart": {
                        "type": "string"
                    },
                    "status": {
                        "type": "string"
                    },
                    "price": {
                        "type": [
                            "integer",
                            "number"
                        ]
                    },
                    "billingTerm": {
                        "type": "string"
                    },
                    "commitment": {
                        "type": "object",
                        "properties": {
                            "id": {
                                "type": "string"
                            },
                            "term": {
                                "type": "string"
                            },
                            "endDate": {
                                "type": "string"
                            }
                        }
                    },
                    "endDate": {
                        "type": "string"
                    }
                },
                "required": [
                    "id",
                    "companyId",
                    "productId",
                    "quantity",
                    "startDate",
                    "createdDate",
                    "billingStart",
                    "status",
                    "price",
                    "billingTerm"
                ]
            }
        },
        "page": {
            "type": "object",
            "properties": {
                "size": {
                    "type": "integer"
                },
                "totalElements": {
                    "type": "integer"
                },
                "totalPages": {
                    "type": "integer"
                },
                "number": {
                    "type": "integer"
                }
            }
        }
    }
}
```

10\. Next we will add an **Apply to Each** Control and use the dynamic **content** coming in from the parse we just did on the Company HTTP request. We will then add a **Condition** Control in which we will populate the **endDate** that is equal to outputs (from out **Get Date** compose operation earlier in the flow). \*Note\* If you see two dynamic endDates, choose the first one. Here we are basically saying we want to find a subscription record renewal date (aka the endDate) that is equal to the date we defined earlier. If no for this condition will be set to blank since we do not need other actions to occur if no match is found.&#x20;

![](https://tminus365.com/wp-content/uploads/2022/09/pic16.png)

11\. In the If yes section of the condition, we will make a couple more HTTP request both for the company record and product record. Here we are dynamically populating the record IDs from the subscription record. We are then using Parse JSON on both to get the content.&#x20;

![](https://tminus365.com/wp-content/uploads/2022/09/pic17.png)

12\. We use the set variable action under the Variable controls to set our Product Name and Company Name values that we initialized earlier in the flow.

![](https://tminus365.com/wp-content/uploads/2022/09/pic18.png)

13\. Next, we are using our Custom Connector with Syncro to leverage their search endpoint. In it we will populate the CustomerName Variable. We will then parse the json again. Leverage the schema I provide below:

![](https://tminus365.com/wp-content/uploads/2022/09/pic19.png)

```
{
    "type": "object",
    "properties": {
        "quick_result": {},
        "results": {
            "type": "array",
            "items": {
                "type": "object",
                "properties": {
                    "table": {
                        "type": "object",
                        "properties": {
                            "_id": {
                                "type": "integer"
                            },
                            "_type": {
                                "type": "string"
                            },
                            "_index": {
                                "type": "string"
                            },
                            "_source": {
                                "type": "object",
                                "properties": {
                                    "table": {
                                        "type": "object",
                                        "properties": {
                                            "firstname": {
                                                "type": "string"
                                            },
                                            "lastname": {
                                                "type": "string"
                                            },
                                            "email": {
                                                "type": "string"
                                            },
                                            "business_name": {
                                                "type": "string"
                                            },
                                            "phones": {
                                                "type": "array"
                                            }
                                        }
                                    }
                                }
                            }
                        }
                    }
                },
                "required": [
                    "table"
                ]
            }
        },
        "error": {}
    }
}
```

14\. We create another Condition action and we determine if our search came back with a value or not. For this, we use the native expression empty(), and we populate it with the dynamic value of the search **results**

![](https://tminus365.com/wp-content/uploads/2022/09/pic21.png)

15\. If the value is empty, I chose to post about it in Teams using the message connector. If it does find a value (i.e. If No), we are using the **Scope** connector to enforce a try catch block. (Using two Scope actions)

![](https://tminus365.com/wp-content/uploads/2022/09/pic20.png)

16\. In the Try block, we are first creating a Compose operation like we did for the Get Date earlier. Here we are defining an expression using the following formula:

outputs(‘Parse\_Search’)\[‘body’]\[‘results’]\[0]\[‘table’]\[‘\_id’]

We are using this formula to traverse the array that is returned as part of our Search endpoint with Syncro in order to get our customer Id(we will need this to create the Ticket)

![](https://tminus365.com/wp-content/uploads/2022/09/pic22.png)

The reason why (the array we are traversing)

![](https://tminus365.com/wp-content/uploads/2022/09/pic4-3.png)

17\. Finally we are using the custom connector to create a ticket. We are using the output we got from the previous step to define the customer ID. We are using the expression utcNot() for the startAt variable. Lastly, we are dynamically populating values that are coming from variables and JSON outputs above. Keep in mind, the entries available to me here are coming from what I created when I set up the custom connector.&#x20;

![](https://tminus365.com/wp-content/uploads/2022/09/pic23.png)

18\. You can decide what to put into the second Scope (Catch) block. Think of this like error handling if the API request fails. You may want to create another notice in Teams or something of the like. Make sure you configure the settings as follows:

![](https://tminus365.com/wp-content/uploads/2022/09/pic24.png)

![](https://tminus365.com/wp-content/uploads/2022/09/pic26.png)

### The Full Tutorial

Questions Post any questions about this to the video!
