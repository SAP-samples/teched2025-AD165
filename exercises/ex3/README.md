# Exercise 3 - Create a submission wizard for AI ideas

In this exercise, you will create a new page **Use Case Repository** in your **AI Center of Excellence** workspace and a **Guided Experience** that lets users curate and submit AI use-case ideas in step by step AI-guided flow. 

> [!NOTE]
> Guided experiences are designed to simplify multi-step business processes and complex workflows by breaking them down into manageable and intuitive steps. Each step can be enriched with various types of content, including videos, documents, forms, tasks, UI cards, and apps to provide users with all the necessary information to complete each step. Steps can be classified as optional or mandatory, ensuring critical tasks are completed while allowing flexibility for other actions. Users don't need to worry about finishing all the steps at once as the progress is saved within Work Zone, enabling them to resume from where they left off.  

---

## <a id="create-page"></a> 3.1 Create a new workpage in your workspace

#### What is a Workpage (in a Workspace)?

A **workpage** is a content page inside an SAP Build Work Zone **workspace**. Each workpage appears as a **tab** in the workspace’s navigation and can be **reordered**, arranged in a hierarchy of pages, initiated for translation or even access-cotrolled to specific users of the workspace. Workpages are like webpages within websites where you assemble information, widgets, and guidance for your users.

**How a workpage is structured**
- **Sections**: A workpage is composed of vertical **sections** you can add, reorder, duplicate, or remove.
- **Grid layout**: Each section uses a **responsive grid** (e.g., 1–3 columns). You can switch layouts at any time to change how content flows.
- **Widgets & Apps**: Inside each section you place **widgets** (Text, Images, Rotating Banner, Links, etc.), **UI Integration Cards**, and **embedded apps**. These are your building blocks.
- **Responsive behavior**: On smaller screens, columns **stack** automatically and content adapts to available width, keeping the page readable on laptops, tablets, and phones.
- **Design freedom**: Combine multiple sections (e.g., a hero section with a Rotating Banner, a two-column section with Text + Card, and a single-column section with a Wizard) to guide users through tasks.

**Why use a workpage for the Use Case Repository?**  
It gives you a single, structured tab where users can: read a short intro, add specific **cards** around Idea Submission (like existing idea list), and complete a **wizard** (Guided Experience) — all in one place for specific purpose of managing ideas within the AI Center Of Excellence.

### Exercise 3.1.1 Add a workpage from workspace menu

1. On the right side of the **workspace menu** which you would find in the content section of the workspace (below the workspace banner image), click the + icon to add a new tab to the navigation bar.
<br>![Add menu entry](/exercises/ex3/images/03_01_0010.png)
2. The new menu entry should lead users to a workpage, so click the **Workpage** tile.
<br>![Workpage tile](/exercises/ex3/images/03_01_0020.png)
3. In the pop-up, keep **New Page**, select folder **Workpages** to store your new page, enter **Use Case Repository** as *Tab Name*, and click **Add**.
<br>![Create Page](/exercises/ex3/images/03_01_0030.png)

The new page is created and you can now start populating it with content. 

---

### Exercise 3.1.2 Add your card to the page

Before you add the wizard, you add a welcoming text widget to explain what the use case repository is about and your card to the page.

1. In the middle of the page, click **Add**. This way a freestyle section with one cell is created. You could also click the dropdown link and select **Freestyle** there.
<br>![Add section](/exercises/ex3/images/02_01_0040.png)
2. Hover the new section and click the **Add Content** button that appears.
3. Select the **Text** widget from the widget gallery.
4. Use text generation ??? to create a welcome text for this page. You might use the prompt
```
Write a welcome text for a use case repository page where users can submit AI use cases and see the ideas of others
```
5. To add your card next to the welcome text, add another column to the section in the same way as on the Welcome page.
6. Click **Add Content**.
7. In the pop-up, select **Cards**.
8. Then select the card you created. You can find it by searching for your user number.

### Exercise 3.1.3 (optional) Add a rotating banner to the page 

After completing these steps you will have added a widget that describes the steps necessary to submit an AI use case in a nice visual way.

1. Click **Add Content** below your text widget and add a **Rotating Banner** widget to the same section.
2. Upload the **start.jpg** image to the rotating banner and enter **Step 1** as *Title* and **Start the Use Case submission process below** as *Description*. Feel free to adjust the image zoom or display window.
3. Move the *Text placement* to the **Top Left**
4. Then click the **+Slide** button on the upper left side of the *Rotating Banner Widget* pop-up.
5. Upload the **answer.jpg** image to the rotating banner and enter **Step 2** as *Title* and **Answer the questions with your best knowledge** as *Description*. Select *Text placement* as **Top Left** again.
6. Finally, add another slide in the same way, upload the **IT.jpg** image to the rotating banner and enter **Step 3** as *Title* and **Wait for IT to approve / come back at your idea and see it represented down below** as *Description*.
7. Now click **Save**.
   

## <a id="create-wizard">Exercise 3.2 Build a wizard based on a guided process from SAP Build Process Automation

After completing these steps you will have created the skeleton for your wizard with some pre-defined stages and steps.

### Exercise 3.2.1 Add a wizard to your page

1. Hover the section that you just filled with content and click the **Add section** button below it to add the wizard. Select **Wizard** in the pop-up.

> [!NOTE]
> You can either create a wizard from scratch by defining stages and steps manually or you can model a complex multi-step process as a *Guided Process* in SAP Build Process Automation and use it as a basis for your wizard. This accelerates the entire process from building to rolling out the experience for production.

2. Select the **IdeaMgmtGuidedProcess** that has been preconfigured in SAP Build Process Automation.
3. Select *Display Option* **Embedded in Workpage**.
4. As you would like to allow users to submit additional ideas while waiting for approval of already submitted ones, check both checkboxes for **Allow wizard to be used multiple times** and **Run the wizard multiple times in parallel**.

Below, you can see a preview of the Stages and Steps that will be part of the new wizard and of the wizard cover.

5. Click **Save** to create the wizard.


### Exercise 3.2.2 Edit steps in stage Idea Generation & Refinement

After completing these steps you will have assigned widgets to allow users to execute all steps in the first stage.

1. In the **Persona and Problem Description** step, click **Add widget**.
<br>![Add widget](/exercises/ex3/images/02_04_0010.png)

2. Select the **Cards** tile and choose card **Refine Problem Statement**.
3. You do not need to make any additional settings, just click **Save**.

> [!NOTE]
> SAP UI Integration cards can easily be created and made available for usage in SAP Build Work Zone with SAP Business Application Studio.

4. Now move on to the next step. Click **Review Matching Proposals**. In this step, the users should check if their proposal is really a new idea or if something very similar or identical has already been submitted or maybe even implemented. To support this step, we created a card that uses AI to identify such duplicate ideas.

5. Add the card  **Matching Solutions** in the same way as before.

> Don't worry about the error message about an undefined problem statement. This will not happen during runtime, as the first step was defined as a mandatory step, so users cannot reach this step without having entered a description of the problem.

6. Move on to step **Define the AI based solution** and add the **Refined solution** card to is as before. This card also uses generative AI to suggest a solution that could then be adapted by the user.

7. Navigate to step **Review and Publish Idea** and add the **Publish idea** card to it.
8. Navigate to the last step of this stage **Done**. No need to do anything here, as it has already been populated.
   

### Exercise 3.2.3 Edit steps in stage Idea to Implementation

After completing these steps you will have completed and published the full guided experience wizard.

1.	In the same way as before, fill the steps of this stage as well. First, add the card **Define MVP Scope** to the step with the same name.
2.	Next, add the card **Implementation Plan** to the second step.
3.	Finally, add the card **Initiate MVP** to the step **Initiate MVP implementation**.

Now, you are done. The wizard is completely configured. You might of course add further cards or widgets to the different steps, for example to provide the users with additional help and information like how-to videos and instructions.

6.	Click **Publish** to make your new page available to workspace users. Permissions??? In the pop-up, click **Publish** again.
<br>![](/exercises/ex3/images/02_02_0010.png)

## Summary

You've now added a **Use case repository** page to your workspace that contains a wizard that guides users throught he process of submitting an idea for an AI use case at ACME Corp, defining the MVP, and initiating the implementation. In the next exercise, you will experience your workspace from a user perspective.

Continue to - [Exercise 4 - Experience SAP Build Work Zone and your workspace as an end user](../ex4/README.md)
