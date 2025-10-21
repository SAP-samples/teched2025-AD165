# Exercise 2 - Add a UI integration card to your workspace

In this exercise, you will learn what are UI integration cards, you will modify a sample card, connect it with real data, download the card bundle, upload it to Work Zone, enable the card access via administration activities and finally add it to a workspage in your workspace.

> [!NOTE]
> Integration cards present a  means to expose application content to the end user in a unified way. A card is a design pattern that displays the most concise pieces of information in a limited-space container. Similar to a tile, it helps users structure their work in an intuitive and dynamic way while presenting more data at first sight than a tile usually does. 💡 Think of UI integration cards are mini-apps that show key info directly on Work Zone pages — you’ll create one and add it to your workspace so that it's visible to all it's members.

# Exercise 2.1 Explore the UI Cards in Card Explorer

After completing this exercise, you’ll be familiar with the **UI Card Explorer** and understand the basic anatomy of a simple **List** card (what each manifest section does).

---

## What is the Card Explorer?
The Card Explorer is an interactive playground for **UI Integration Cards**. It lets you:
- Preview different **card types** and **features**.
- Inspect and edit the card’s **`manifest.json`** side-by-side.
- See how **data**, **actions**, **configuration**, and **filters** change a card.
- Copy snippets or **download** a working sample for your own use.

> **Tip:** Everything you see in the preview is driven by the `manifest.json`. You’ll learn which parts of the manifest control which parts of the UI. 

![UI Cards Explorer website](./images/02_01_0010.png)  
_The “Explore” tab showing: left navigation (Card Types & Card Features), center preview, right manifest panel._

> [!NOTE]
> All steps below in this exercise 2.1 refer to this screenshot

---

## Steps

1. Right click on the link below and **Open the link in a new tab**. This will open the [Card Explorer](https://sapui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html) with **_Explore_.** tab selected.

	Go to:  [https://sapui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/list](https://sapui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/list)
   
   The page has three main areas:  
   - **Left navigation:** _Card Types_ (e.g., **List**, Object, Table, Analytical, Calendar, Timeline, WebPage, Component, Adaptive) and _Card Features_ (Data, Actions, Configuration, Filters, etc.).  
   - **Center:** a live **Preview** of the selected card.  
   - **Right:** the card’s **`manifest.json`** editor.

2. **Skim the Card Types (what you can build).**  
   - **List** – list of items (title/description/info), optional actions & pagination.  
   - **Object** – attribute/value groups.  
   - **Table** – tabular data.  
   - **Analytical** – KPIs/charts (often with a Numeric Header).  
   - **Calendar**, **Timeline**, **WebPage**, **Component**, **Adaptive** (MS Adaptive Cards).  
   These map to the `sap.card/type` in the manifest.

3. **Open _Card Types ▸ List_.**  
   Review how the **List** card renders in the preview, then open the **manifest** on the right.

4. **Understand the manifest anatomy (what each part is for).**  
   A card is defined by a **JSON manifest** with a few key namespaces:

   - **`sap.app`** → app/card metadata & identity  
     - `id`: A unique identifier (e.g., `com.example.cards.samplelist`)  
     - `type`: Must be `"card"` for UI Integration Cards  
     - `title`, `shortTitle`, and `applicationVersion.version`

   - **`sap.card`** → the card itself. Common subsections:  
     - **`type`** – one of: List/Table/Object/Analytical/Timeline/WebPage/AdaptiveCard/Calendar/Component/...  
     - **`header`** – title, subtitle, icon, optional status or numeric header.  
     - **`data`** *(optional)* – where the card gets data: a REST `request` (`url`, `method`, `headers`, `parameters`) and a `path` for binding. Usually, accessed via BTP destinations.
     - **`content`** – how to render the UI. For **List**, define the `item` template: `title`, `description`, `info`, and (optionally) `actions` and `maxItems`.  
     - **`footer`** *(optional)* – components like a `paginator`.  
     - **`configuration`** *(optional)* – **parameters**, **destinations**, **filters**, and other host-configurable settings.  
     - **`actions`** *(optional)* – interactive behaviors like `Navigation` or `Submit`. For **List**, row-level interactions usually go under `content.item.actions`.

5. **Peek at _Card Features_ to see “how it’s done.”**  
   - **Configuration**: how to declare `parameters`, `destinations`, `filters`, Markdown support, etc. (manifest → `sap.card/configuration`).  
   - **Data**: how to set up a `request` (URL/method/headers/parameters) and bind to a `path`.  
   - **Filters**: how to define end-user filters under `configuration` and bind them to your data.  
   - **Actions**: how to make headers or list items clickable; the host handles events like `Navigation` or `Submit`.

> **Takeaway:** The Explorer lets you test card **types** and inspect the **manifest** that drives them—especially `sap.card/type`, `header`, `data`, `content`, `footer`, `configuration`, and `actions`. These are the only pieces you need to understand before adapting a List card in the next step.

---

### Minimal “List” card anatomy (reference)
<details>
<summary>sample UI card JSON</summary>

```json
{
  "sap.app": {
    "id": "com.example.cards.samplelist",
    "type": "card",
    "title": "Sample List Card",
    "applicationVersion": { "version": "1.0.0" }
  },
  "sap.card": {
    "type": "List",
    "header": {
      "title": "Orders",
      "subtitle": "Recent",
      "icon": { "src": "sap-icon://product" }
    },
    "data": {
      "request": {
        "url": "https://example.com/api/orders",
        "method": "GET",
        "headers": { "Accept": "application/json" }
      },
      "path": "/items"
    },
    "content": {
      "item": {
        "title": "{OrderName}",
        "description": "{Customer}",
        "info": "{Status}",
        "actions": [
          { "type": "Navigation", "parameters": { "url": "{Link}" } }
        ]
      },
      "maxItems": 5
    },
    "footer": {
      "paginator": { "pageSize": 5 }
    },
    "configuration": {
      "parameters": { "region": { "value": "EMEA" } }
    }
  }
}
```
</details>

---

## Exercise 2.2 Select an advanced card and adapt it to your needs

After completing these steps you will have modified a sample card from Card Explorer and downloaded the card bundle to your local computer, which will be used in subsequent exercises. 

1. Esure that you are already in **Explore** tab in [Card Explorer](https://sapui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/list).
   
![Explore UI Cards](/exercises/ex2/images/02_03_0010.png)
<br/>

2. For this exercise we will start from an existing List Card that fetches data from Nothwind oData service and modify it. Hence, in the menu on the left, select the *Card Features* **Data** and ensure that the default **Basic Data Request** is selected in the drop-down as shown in the screenshot below.
   
<br> ![Select Card Type](/exercises/ex2/images/02_04_0010.png)
<br>

3. To adapt the card, you can adjust its *`manifest.json`* file on the right.

> [!IMPORTANT]
> Please make sure to replace ### with your participant number. For example participant number 1 results in AD165-001

   <br>In the `sap.app` section on the top:
   <br> - Modify the card's *`id`* into `com.sap.teched.ad165.###` to make it unique and easier to identify later

> [!CAUTION]
> Please do not use "-" in the id, only alphanumeric characters and "." 
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



## Exercise 2.3 Create an app on SAP Build Work Zone using your downloaded card

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
   

## Exercise 2.4 Make the new card available to all Work Zone users

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
