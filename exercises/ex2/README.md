# Exercise 2 - Add a UI integration card to your workspace

In this exercise, you will learn what are UI integration cards, you will modify a sample card, connect it with real data, download the card bundle, upload it to Work Zone, enable the card access via administration activities and make it available in Work Zone, so you can add it to a workpage in the next exercise.

> [!NOTE]
> Integration cards present a new means to expose application content to the end user in a unified way. A card is a design pattern that displays the most concise pieces of information in a limited-space container. Similar to a tile, it helps users structure their work in an intuitive and dynamic way while presenting more data at first sight than a tile usually does.


## Exercise 2.1 Select an advanced card and adapt it to your needs

After completing these steps you will have downloaded an advanced card from [sapui5.hana.ondemand.com](https://sapui5.hana.ondemand.com). This website provides you with a lot of information, samples, and resources to support you in developing web apps with SAPUI5. 

1. Navigate to the [Card Explorer
](https://sapui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html)that gathers all information about UI integration cards and navigate to the **Explore** tab. Here you can test various card types with sample data and download them. 
<br>![Explore UI Cards](/exercises/ex2/images/02_03_0010.png)
2. In the menu on the left, select the *Card Features* **Data**
<br>![Select Card Type](/exercises/ex2/images/02_04_0010.png)

3. To adapt the card, you can adjust its *`manifest.json`* file on the right.

> [!IMPORTANT]
> Pleaase Make sure to replace ### with your participant number. For example participant number 1 results in AD165-001

   <br>In the `sap.app` section on the top:
   <br> - Modify the card's *`id`* into `com.sap.teched.ad165.###` to make it unique and easier to identify later

> [!CAUTION]
> Please do not use "-" in the id, only Alphanumeric characters and "." 
> <br>In addition, please note that the version property is mandatory. Do not change it, as without it the card will not be accepted by Work Zone.
   
   <br> - Change the *`title`* and *`shortTitle`* properties into `Standard AI Agents List Card by AD165-###`
   <br> - Change the *`subTitle`* into `Delivered by SAP`
   <br> - Change the *`info`* into `Custom Card for Teched Hands-On`
   <br> - Change the *`description`* into `Delivered by SAP`

The `sap.app` section starting in lines 3 should look like this now:

````json
	"sap.app": {
		"id": "com.sap.teched.ad165.###",
		"type": "card",
		"title": "Standard AI Agents List Card by AD165-###",
		"subTitle": "Delivered by SAP",
		"applicationVersion": {
			"version": "1.0.0"
		},
		"shortTitle": "Standard AI Agents List Card by AD165-###",
		"info": "Custom Card for Teched Hands-On",
		"description": "Delivered by SAP",
		"tags": {
			"keywords": [
				"Data",
				"Card",
				"Sample"
			]
		}
	},
````

4. Next, you change the `header` part in the `sap.card` section.
   <br> - Change the *`title`* property into `Standard SAP AI Agents`
   <br> - Change the *`subtitle`* property into `List Card by AD165-###`
   <br> - Change the *`icon`* property into SAP AI icon by using the src of `"sap-icon://ai"` (or, simply replace "product" with "ai")
   
The `sap.card` `header` section starting in lines 24 should look like this now:

````json
	"header": {
		"title": "Standard SAP AI Agents",
		"subtitle": "List Card by AD165-045",
		"icon": {
			"src": "sap-icon://ai"
		}
	},
````

5. Next, you change the `content` `data` part in the `sap.card` section.
   <br> - Change the *`url`* property to `https://simplenodebackend-chipper-kob-zy.cfapps.eu10-004.hana.ondemand.com/IdeaManagementDB/api/v1/list`
   <br> - Change the *`method`*  property to `POST`
   <br> - Add a *`headers`* to the *`request`* property with the value `"headers": {"Content-Type": "application/json"},`
   <br> - Override the "$format": "json" proprty under `request` `parameters` and replace it with a parameter named `"collectionName":"SAPAIAgents"`
   <br> - Remove the `"value"` from the `path` property and leave it only with `/`

The `data` section starting in lines 32 should look like this now:

````json
		"content": {
			"data": {
				"request": {
					"url": "https://simplenodebackend-chipper-kob-zy.cfapps.eu10-004.hana.ondemand.com/IdeaManagementDB/api/v1/list",
					"method": "POST",
					"headers": {"Content-Type": "application/json"},
					"parameters": {
						 "collectionName":"SAPAIAgents"
					}
				},
				"path": "/"
			},
		},
````
   
> [!TIP]
> You can see the change immediately on the card preview. 
   
6. Next, you should bound the `items` section
   <br> - First, remove the last proprty `"highlight"` as it is not necessary 
   <br> - Change the `title` property into `"{ProblemStatement}",`
   <br> - Change the `description` property into `"{RefinedSolution}"`

The `item` section starting in line 43 should look like this now:

````json
		"item": {
				"title": "{ProblemStatement}",
				"description": "{RefinedSolution}"
		},
````
   
7. Add a pagination to be able to see all existing ideas
   <br> - After the `Content` section add `,"footer": { "paginator": {"pageSize": 5} }` 

The "footer" section starting in line 49 should look like this now:
````json
		"footer": {
		    "paginator": {
    			"pageSize": 5
		    }
	    }				
````

> [!TIP]
> You can see the change immediately on the card preview. click on `Show More` to see all ideas exist 
 

8. Add Actions to the items, so each raw item will be clickable
   <br> - After the `description` property add `,` and then add `"actions": [ { "type": "Navigation", "enabled": "{= ${IdeaLinks}}", "parameters": { "url": "{IdeaLinks}" } } ]`

The "item" section starting in line 43 should look like this now:
````json
		"item": {
				"title": "{RefinedSolution}",
				"description": "{ProblemStatement}",
				"actions": [
					{
						"type": "Navigation",
						"enabled": "{= ${IdeaLinks}}",
						"parameters": {
							"url": "{IdeaLinks}"
						}
					}
				]
			},			
````

> [!TIP]
> You can see the change immediately on the card preview. click on any line in the list to see that the action is working and leads to a URL of the discovery center of SAP. 


9. Download the Card you've created. Click on the Download button on the top right and download Bundle as card.zip
<br>![Download Cards zip](/exercises/ex2/images/02_10_0010.png)



## Exercise 2.2 Create an app on SAP Build Work Zone using your downloaded card

After completing these steps you will have added the card to SAP Build Work Zone.

1. Go back to the tab with Work Zone still open. If you closed it, you can access it [here](https://ad165-m3ep4xn0.workzone.cfapps.eu10.hana.ondemand.com/site#workzone-home&/home).
2. Now you need to navigate to the Administration environment. Click the User icon on the top right and select **Administration Console**.
3. In the menu on the left, open **External Integrations** > ** Business Content** and click the **Content Manager** button. The Content Manager opens in a new browser tab.

> [!NOTE]
> In the Content Manager administrators can manage business content. The table contains all business content entities (like apps, pages, spaces, roles etc.) that have been made available from various sources. In the fourth column for example, you see the Content Channel via which the content was provided. Besides local content, some roles from SAP S/4HANA have been integrated with their assigned apps, spaces, and pages. You can use the filter to only display a specific content entity type like apps.

6. A card is one visualization type of an app, so you will now create an app. Click the **Create** button and select **App** from the dropdown.
7. Click **Visualization** to go directly to the Visualization tab.
8. In the field *Visualization Type* select **UI Integration Card**. Then click the **Upload Card** button.
9. Select the zip file you just downloaded from your *Downloads* folder. 

11. Click **Save**. 
   

## Exercise 2.3 Make the new card available to all Work Zone users

After completing these steps you will have made the card available for usage in SAP Build Work Zone.

1. Go back to the Content Manager by clicking **Content Manager** in the breadcrumb.

> [!NOTE]
> To make apps available to users, they need to be assigned to at least one of the user's roles. You will now assign the app to the Everyone role which is assigned to all users by default.

2. Click the **Everyone** role in the content table to open it.
3. Click the **Edit** button to switch to editing mode.
4. Locate your app in the list of apps. If you do not see it immediately, you can search for your user number to find it more easily. Then switch the **Assignment Status** to **On**. 
5. Click **Save**.

To allow end users to put the card on a page, you also need to enable it.

6. Go back to the browser tab with the Administration Console still open. You can also close the tab with the Content Manager as it is not needed any more.
7. In the menu, open **UI Integrations** > **Cards**.
8. Enter your user number into the Search field to find your card. Then turn the switch to **On** to enable it for end user usage.

## Summary

You've now added a **UI integration card** page to Work Zone so that you can use it during page design. your workspace that contains a wizard that guides users throught he process of submitting an idea for an AI use case at ACME Corp, defining the MVP, and initiating the implementation. In the next exercise, you will add a workpage to the workspace you created in exercise 1 and build a wizard that guides users throught he process of submitting an idea for an AI use case.
Continue to - [Exercise 3 - Excercise 3 ](../ex3/README.md)
