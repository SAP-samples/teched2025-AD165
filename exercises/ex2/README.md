# Exercise 2 - Add a simple UI integration card for usage in your workspace

In this exercise, you will download a simple static UI integration card and make it available in Work Zone, so you can add it to a workpage in the next exercise. In the optional exercise 5, you can learn how to create more complex UI integration cards that consume real business data.

> **&#9432;** Integration cards present a new means to expose application content to the end user in a unified way. A card is a design pattern that displays the most concise pieces of information in a limited-space container. Similar to a tile, it helps users structure their work in an intuitive and dynamic way while presenting more data at first sight than a tile usually does. 


## Exercise 2.1 Select a sample card and adapt it to your needs

After completing these steps you will have downloaded a sample static card from [sapui5.hana.ondemand.com](https://sapui5.hana.ondemand.com). This website provides you with a lot of information, samples, and resources to support you in developing web apps with SAPUI5. 

1. Navigate to the [Card Explorer
](https://sapui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html)that gathers all information about UI integration cards and navigate to the **Explore** tab. Here you can test various card types with sample data and download them. 
<br>![Explore UI Cards](/exercises/ex2/images/02_01_0010.png)
2. In the menu on the left, select the *Declarative Card Type* **Analytical**. Then use the Dropdown on the top of the window to select the **Popover Extension Actions** card.
<br>![Select Card Type](/exercises/ex2/images/02_01_0020.png)
4. To adapt the card to the use case of an AI Use case repository, let us adjust its *manifest.json* file to change the static data displayed on the card.
In the coding on the left, change the header title in the sap.card section to **Status of AI Projects**. You can see the change immediately on the card preview.
<br>![Change title](/exercises/ex2/images/02_01_0030.png)
5. Now you can change the meaning of the three colors to different statuses. Scroll down to the content - data part of the sap.card section and simply change the three store names. Change *24-Seven* to **Live**, change *A&A* to **Implementation**, and change *Alexei's Specialities* to **Definition**.
<br>![Change title](/exercises/ex2/images/02_01_0030.png)

The "data" section starting in lines 52 till 73 should look like this now:
````
			"data": {
				"json": {
					"milk": [
						{
							"id": "1",
							"storeName": "Live",
							"revenue": 345292.06
						},
						{
							"id": "2",
							"storeName": "Implementation",
							"revenue": 1564235.29
						},
						{
							"id": "3",
							"storeName": "Definition",
							"revenue": 1085567.22
						}
					]
				},
				"path": "/milk"
			},
````


4. You could do some more changes, e.g. adjust the URL where the user would navigate when clicking on the sections of the chart, but to keep it simple, just download the card now.
   To do this, click the **Download** button in the upper right corner and select **Bundle as card.zip**. This will download a zip to your computer.
<br>![Download card](/exercises/ex2/images/02_01_0040.png)


## Exercise 2.2 Create an app on SAP Build Work Zone using your downloaded card

After completing these steps you will have added the card to SAP Build Work Zone.

1. Go back to the tab with Work Zone still open. If you closed it, you can access it [here](https://ad165-m3ep4xn0.workzone.cfapps.eu10.hana.ondemand.com/site#workzone-home&/home).
2. Now you need to navigate to the Administration environment. Click the User icon on the top right and select **Administration Console**.
3. In the menu on the left, open **External Integrations** > ** Business Content** and click the **Content Manager** button. This takes you to the Content Manager where you can manage your business content. In this table you can find all business content entities (like apps, pages, spaces, roles etc.) that have been made available from various sources. In the fourth column for example, you see the Content Channel via which the content was created. Besides local content, some roles from SAP S/4HANA have been integrated with their assigned apps, spaces, and pages
4. Move the *Text placement* to the **Top Left**
5. Then click the **+Slide** button on the upper left side of the *Rotating Banner Widget* pop-up.
6. Upload the **answer.jpg** image to the rotating banner and enter **Step 2** as *Title* and **Answer the questions with your best knowledge** as *Description*. Select *Text placement* as **Top Left** again.
7. Finally, add another slide in the same way, upload the **IT.jpg** image to the rotating banner and enter **Step 3** as *Title* and **Wait for IT to approve / come back at your idea and see it represented down below** as *Description*.
8. Now click **Save**.
   

## Exercise 2.3 Create a wizard based on a Guided Process from SAP Build Process Automation

After completing these steps you will have created the skeleton for your wizard with some pre-defined stages and steps.

1. Hover the section that you just filled with content and click the **Add section** button below it to add the wizard. Select **Wizard** in the pop-up.

> **&#9432;** You can either create a wizard from scratch by defining stages and steps manually or you can model a complex multi-step process as a *Guided Process* in SAP Build Process Automation and use it as a basis for your wizard. This accelerates the entire process from building to rolling out the experience for production.

2. Select the **IdeaMgmtGuidedProcess** that has been preconfigured in SAP Build Process Automation.
3. Select *Display Option* **Embedded in Workpage**.
4. As you would like to allow users to submit additional ideas while waiting for approval of already submitted ones, check both checkboxes for **Allow wizard to be used multiple times** and **Run the wizard multiple times in parallel**.

Below, you can see a preview of the Stages and Steps that will be part of the new wizard and of the wizard cover.

5. Click **Save** to create the wizard.


## Exercise 2.4 Edit steps in stage Idea Generation & Refinement

After completing these steps you will have assigned widgets to allow users to execute all steps in the first stage.

1. In the **Persona and Problem Description** step, click **Add widget**.
<br>![Add widget](/exercises/ex2/images/02_04_0010.png)

2. Select the **Cards** tile and choose card **Refine Problem Statement**.
3. You do not need to make any additional settings, just click **Save**.

> **&#9432;** SAP UI Integration cards can easily be created and made available for usage in SAP Build Work Zone with SAP Business Application Studio.

4. Now move on to the next step. Click **Review Matching Proposals**. In this step, the users should check if their proposal is really a new idea or if something very similar or identical has already been submitted or maybe even implemented. To support this step, we created a card that uses AI to identify such duplicate ideas.

5. Add the card  **Matching Solutions** in the same way as before.

> Don't worry about the error message about an undefined problem statement. This will not happen during runtime, as the first step was defined as a mandatory step, so users cannot reach this step without having entered a description of the problem.

6. Move on to step **Define the AI based solution** and add the **Refined solution** card to is as before. This card also uses generative AI to suggest a solution that could then be adapted by the user.

7. Navigate to step **Review and Publish Idea** and add the **Publish idea** card to it.
8. Navigate to the last step of this stage **Done**. No need to do anything here, as it has already been populated.
   

## Exercise 2.5 Edit steps in stage Idea to Implementation

After completing these steps you will have completed and published the full guided experience wizard.

1.	In the same way as before, fill the steps of this stage as well. First, add the card **Define MVP Scope** to the step with the same name.
2.	Next, add the card **Implementation Plan** to the second step.
3.	Finally, add the card **Initiate MVP** to the step **Initiate MVP implementation**.

Now, you are done. The wizard is completely configured. You might of course add further cards or widgets to the different steps, for example to provide the users with additional help and information like how-to videos and instructions.

6.	Click **Publish** to make your new page available to workspace users. Permissions??? In the pop-up, click **Publish** again.
<br>![](/exercises/ex2/images/02_02_0010.png)

## Summary

You've now added a **Use case repository** page to your workspace that contains a wizard that guides users throught he process of submitting an idea for an AI use case at ACME Corp, defining the MVP, and initiating the implementation. In the next exercise, you will experience your workspace from a user perspective.

Continue to - [Exercise 3 - Excercise 3 ](../ex3/README.md)
