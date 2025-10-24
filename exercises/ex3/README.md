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

3. You should see a pop-up with all options that you can add to the Workspace - **Workpage**, **Feed Update**, **Members**, **Content**, etc. The **Workpage** option allow you to add a freestyle workpage which you can design as per your purpose; all other options are pre-defined page from Work Zone. In this case, the new menu entry should lead users to a a new custom designed **Workpage**, so click on the **Workpage** tile.
<br>![Workpage tile](/exercises/ex3/images/03_01_0020.png)

5. In the pop-up, keep **New Page**, select folder **Workpages** to store your new page, enter **Use Case Repository** as **Tab Name**, and click **Add**.
<br>![Create Page](/exercises/ex3/images/03_01_0030.png)

The new page is created and you should see an empty **Workpage** in edit mode, where you start populating content.
<br>![Add section](/exercises/ex3/images/03_01_0035.png)

---

### Exercise 3.1.2 Add content to the page

Before you add the **Guiided Experience** wizard to the page, you add an text block to explain what the use case repository is about.

1. In the middle of the page, click **Add**. This way a freestyle section with one cell is created. You could also click the dropdown link and select **Freestyle** there.
<br>![Add section](/exercises/ex3/images/03_01_0040.png)

2. You will now create a text message for the users with AI Assistance. Inside the section, click the dropdown on the **Add** button.
<br>![Add text with AI](/exercises/ex3/images/03_01_0050.png)
   
3. This will open a **Generate Text** pop-up which allows you to enter aAI  prompt. Type in the following text - 
```
Write a welcome text for a "Use Case Repository" workpage within the "AI Center of Excellence" Work Zone workspace. 
In this workpage users can submit AI use cases and see the ideas of other users.
Write in encouraging tone to use the Guided Experience wizard flow below in the page to capture their Ideas with the help and curate them with the help of embedded AI Assistance in each step.
Generate in a markdown format with a Bold and large Title and content that is well formatter in bullet points and rich text formatting.
```
Click on the blue **Send** icon button.
   
4. AI should respond with the **Generated Text**. You can review the text and decide to **Retry** with the same prompt or **Discard** the text completely to modify your Prompt and try fresh. For now, you can Click on **Accept** since you will have oppotunity to edit it further with AI Assistance.
<br>![generate text](/exercises/ex3/images/03_01_0060.png)

> [!TIP]
> If the response is not well formatted with large title and bullet points, you can retry to make AI respond as per the prompt.

5. The generated text should now be in the Page, With the rich text formatting. You can further edit the text by adding your own content or format it differently using the hovering text format menu which appears when you select a part of the text, as shown in the image below.
<br>![text in page](/exercises/ex3/images/03_01_0070.png)

6. You can edit the text further use AI assistance using the last **AI Assistance** button on the hovering text format menu. As an option, you select the last line and ask AI to make it a bit more casual. 
<br>![text format options](/exercises/ex3/images/03_01_0080.png)

7. It should again load the prompt window, but this time you don't have to define the prompt as it already creates the prompt based on the AI assistance option you selected. Select Accept
<br>![text format options](/exercises/ex3/images/03_01_0090.png)

You have now complete this exercise of creating the Welcome explanatory text for the new workpage. Stay in the edit mode for the next exercise.

<!-- ### Exercise 3.1.3 (optional) Add a rotating banner to the page 

After completing these steps you will have added a widget that describes the steps necessary to submit an AI use case in a nice visual way.

1. Click **Add Content** below your text widget and add a **Rotating Banner** widget to the same section.
2. Upload the **start.jpg** image to the rotating banner and enter **Step 1** as *Title* and **Start the Use Case submission process below** as *Description*. Feel free to adjust the image zoom or display window.
3. Move the *Text placement* to the **Top Left**
4. Then click the **+Slide** button on the upper left side of the *Rotating Banner Widget* pop-up.
5. Upload the **answer.jpg** image to the rotating banner and enter **Step 2** as *Title* and **Answer the questions with your best knowledge** as *Description*. Select *Text placement* as **Top Left** again.
6. Finally, add another slide in the same way, upload the **IT.jpg** image to the rotating banner and enter **Step 3** as *Title* and **Wait for IT to approve / come back at your idea and see it represented down below** as *Description*.
7. Now click **Save**.
-->   

## <a id="create-wizard">Exercise 3.2 Build a wizard based on a guided process from SAP Build Process Automation

After completing these steps you will have created the skeleton for your wizard with some pre-defined stages and steps.

### Exercise 3.2.1 Add a wizard to your page

In this exercise you will create a **[Guided Experience](https://community.sap.com/t5/technology-blog-posts-by-sap/guided-experiences-powered-by-sap-build/ba-p/13898694)** using pre-created **Guided Process** in **SAP Build Process Automation**.

#### So what are Guided Experiences?


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
