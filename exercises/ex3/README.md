# Exercise 3 - Create a submission wizard for AI ideas

In this exercise, you will create a new page **Use Case Repository** in your **AI Center of Excellence** workspace and a **Guided Experience** that lets users curate and submit AI use-case ideas in step by step AI-guided flow. 

> [!NOTE]
> Guided experiences are designed to simplify multi-step business processes and complex workflows by breaking them down into manageable and intuitive steps. Each step can be enriched with various types of content, including videos, documents, forms, tasks, UI cards, and apps to provide users with all the necessary information to complete each step. Steps can be classified as optional or mandatory, ensuring critical tasks are completed while allowing flexibility for other actions. Users don't need to worry about finishing all the steps at once as the progress is saved within Work Zone, enabling them to resume from where they left off.  

---

## 3.1 Create a new workpage in your workspace

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

---

### Exercise 3.1.1 Add a workpage from workspace menu

1. On the right side of the **workspace menu** which you would find in the content section of the workspace (below the workspace banner image), click the + icon to add a new tab to the navigation bar.
<br>![Add menu entry](/exercises/ex3/images/03_01_0010.png)

3. You should see a pop-up with all options that you can add to the Workspace - **Workpage**, **Feed Update**, **Members**, **Content**, etc. The **Workpage** option allow you to add a freestyle workpage which you can design as per your purpose; all other options are pre-defined page from Work Zone. In this case, the new menu entry should lead users to a a new custom designed **Workpage**, so click on the **Workpage** tile.
<p align="center"><img src="/exercises/ex3/images/03_01_0020.png" width="600"/></p>

5. In the pop-up, keep **New Page**, select folder **Workpages** to store your new page, enter **Use Case Repository** as **Tab Name**, and click **Add**.
<p align="center"><img src="/exercises/ex3/images/03_01_0030.png" width="600"/></p>

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
<p align="center"><img src="/exercises/ex3/images/03_01_0060.png" width="600"/></p>

> [!TIP]
> If the response is not well formatted with large title and bullet points, you can retry to make AI respond as per the prompt.

5. The generated text should now be in the Page, With the rich text formatting. You can further edit the text by adding your own content or format it differently using the hovering text format menu which appears when you select a part of the text, as shown in the image below.
<br>![text in page](/exercises/ex3/images/03_01_0070.png)

6. You can edit the text further use AI assistance using the last **AI Assistance** button on the hovering text format menu. As an option, you select the last line and ask AI to make it a bit more casual. 
<br>![text format options](/exercises/ex3/images/03_01_0080.png)

7. It should again load the prompt window, but this time you don't have to define the prompt as it already creates the prompt based on the AI assistance option you selected. Select Accept
<br>![text format options](/exercises/ex3/images/03_01_0090.png)

You have now complete this exercise of creating the Welcome explanatory text for the new workpage. Press on the publish button to persist this text widget in the work page.
<br>![publish text generation](/exercises/ex3/images/03_01_0100.png)

---

## Exercise 3.2 Build a wizard based on a guided process from SAP Build Process Automation

In this exercise you will create a **Guided Experience** using pre-created **Guided Process** in **SAP Build Process Automation**.

---

### Exercise 3.2.1 Understand Guided Experiences

> [!TIP]
> This exercise is more for learning and knowledge. You can skip this section since you don't have to take any action in this section.

<details>
  <summary><b>Reading content on Guided Experience and Guided Process</b></summary>
<br>
   
**Guided Experiences** in SAP Build Work Zone are **step-by-step**, **self-service journeys** that package the right content and tools—videos, documents, apps, and UI Integration Cards—into clear stages and steps. They support mandatory/optional steps, **save progress** so users can resume later, and can run multiple instances in parallel or be restarted when needed—making complex processes like onboarding, benefits enrollment, or solution rollouts simpler, consistent, and measurable. In short: they reduce change-management overhead and help users complete work correctly the first time.  

When you design the flow as a **Guided Process** in SAP Build Process Automation (SBPA), you visually model stages, steps, forms, decisions, approvals, and automations, then publish that process to Work Zone as the blueprint for your Guided Experience. This gives you **governance** (versioning, change control), **reuse across workspaces**, and faster rollout—because updates to the process can be redeployed without rebuilding the Work Zone UI.

If you are interested, you can read more about it in [Blog 1](https://community.sap.com/t5/technology-blogs-by-sap/what-s-new-with-sap-build-work-zone-guided-experiences/ba-p/13717701) and [Blog 2](https://community.sap.com/t5/technology-blog-posts-by-sap/guided-experiences-powered-by-sap-build/ba-p/13898694).

### Exercise 3.2.2 Understand the "Idea Management Guided Process" which is created for this exercise

Guided Process are created within [**SAP Build Process Automation**](https://www.sap.com/products/technology-platform/process-automation/features.html) which can be accessed via  SAP *Build Lobby*.
<br>![switch to edit mode](/exercises/ex3/images/03_02_0001.png)

In a **Process Automation** project in SAP Build Lobby, you can create **Guided Processes** which are used to define the flow (stages, steps, etc) of **Guided Experience**. Guided 
<br>![switch to edit mode](/exercises/ex3/images/03_02_0002.png)

One such **Guided Process** is already created in the same sub-account which you will use to create the **Guided Experience** in the subsequent expercise below. Let us see the details of this **Idea Management Guided Process** is setup. Guided Processes are setup in multiple **phases** and each phase have multiple **steps**.

In this case, there are 2 phases - 

Phase 1: **Idea Creation and Refinement** - this has 4 steps - to capture the problem space, match existing solutions and ideas, refining the solution and finally publishing the idea.
<br>![phase 1](/exercises/ex3/images/03_02_0003.png)

Phase 2: **Idea to Implementation** this has 3 steps - to define the initial implementation scope, plan the implementation steps and fianlly initiating the implementation bringing the idea towards realization.
<br>![phase 2](/exercises/ex3/images/03_02_0004.png)

This was brief glimpse of **Guided Process** to help you understand the subsequent exercises. 
</details>

### Exercise 3.2.3 Add a wizard to your workpage and select the pre-defined guided process

1. Ensure that you are in the newly created **Use Case Repository** workpage and you have switched into the edit mode. You may already be familiar with the edit-mode option from Exercise 1. To refresh, you can click on the pencil icon (as shown below) to get into the edit mode - where you can make changes to the workpage.

<br>![switch to edit mode](/exercises/ex3/images/03_02_0010.png)

2. Hover the section that you just filled with content and click the **Add section** button below. You should see 2 options in the pop-up **FreeStyle** and **Wizard**. Select **Wizard** to start creating the **Guided Experience**.   

<br>![add a section](/exercises/ex3/images/03_02_0020.png)

3. You should see the **Add Wizard** popup. Select the **Idea Management Guided Process** from the that has been preconfigured in SAP Build Process Automation - which we saw briefly in Exercise 3.2.2 above. You will observe that `Title` and `Description` fields are automatically set as defind in the Guided Process.

<br>![Select guided process](/exercises/ex3/images/03_02_0030.png)

4. Leave the *Display Option* to default - **Embedded in Workpage**.
 
5. As you would like to allow users to submit additional ideas in parallel to already active ones, check both checkboxes for **Allow wizard to be used multiple times** and **Run the wizard multiple times in parallel**.
<p align="center"><img src="/exercises/ex3/images/03_02_0040.png" width="700"/></p>

Below, you can see a preview of the Stages and Steps that will be part of this **Guided Experience** as fetched from the **Idea Management Guided Process**.

> [!NOTE]
> You can either create a wizard from scratch by defining stages and steps manually or you can model a complex multi-step process as a *Guided Process* in SAP Build Process Automation and use it as a basis for your wizard. When you select the *Guided Process* to fetch and auto-generate the stages and steps in the wizard, you cannot modify the stages and steps configuration in Work Zone. Such changes, if required, must be done in the *Guided Process* itself.

6. (Optional) Change the cover image of the Guided Experience.
   [right click on this link and save to local computer](/exercise/ex3/images/GuidedExperienceBackground.jpeg)

Once you have saved the image (default download location should C:\Users\<Your Username>\Downloads), you can click on the image icon the top-right of the Guided Experience preview as shown in the image below. 
<p align="center"><img src="/exercises/ex3/images/03_02_0050.png" width="700"/></p>

Navigate to the Downloads folder in your system and select the downloaded image from step 6. You should see a new background in the Guided Experience preview. This is how the Guided experience would look like to all users of this workspace after you save and submit the workpage changes.

8. Click **Save** to create the wizard.

### Exercise 3.2.4 Edit steps in stage Idea Creation & Refinement

For each In each of the steps below, 

you will be required to click on the **Add widget** button in the middle of the step UI.
<br>![Add widget](/exercises/ex3/images/03_04_0010.png)

And select the **cards** tile.
<p align="center"><img src="/exercises/ex3/images/03_04_0020.png" width="600"/></p>

1. In the first step, **Problem Description** step, click **Add widget**, go to **cards** tile and search for `Refine Problem`. You should see the **Refine Problem Statement**, select it to add as the step UI.
<p align="center"><img src="/exercises/ex3/images/03_04_0030.png" width="600"/></p>
   
You do not need to make any additional settings, just click **Save**.
<br>![save step UI](/exercises/ex3/images/03_04_0040.png)

> [!NOTE]
> You have already created a SAP UI Integration card in Exercise 2. Similarly, UI integration cards were already pre-created for ease of this **Guided Experience** exercise.
> While creating the Guided Experience, you will not be able to interact with the card, even though the cards are visible in the wizard steps. Once you sibmit the overall guided experience, the users will be able to interact with the step UIs when they initiate the wizard flow.

In this step, the user is asked to define the problem statement, who is affected by the problem and what would be the impact of the AI driven solution idea that he wants to capture through this wizard. This will help AI to find matching standard solution or ideas submitted by other users.

2. Now move on to the next step. Click **Review Matching Proposals** on the top wizard breadcrumb.
<br>![save step UI](/exercises/ex3/images/03_04_0050.png)

Following the step 1 instructions, add the widget --> card --> **Matching Solutions**.

> [!IMPORTANT]
> You will see an *error message* when you save the card configuration and add the card to the step, but you can ignore it.
> This is because, even while creating the **Guided Experience**, the card is rendered triggering it's actions. This card expects that a problem statement is defined in the previous step but that's not true during the wizard creation.
> You can click on **close** on the error message and continue. During actual usage of the guided experience, this error shouldn't come as the user can only come to the second step after completing the first step - which should already capture the required input to this card.
> <br>![save step UI](/exercises/ex3/images/03_04_0060.png)

In this step, the users should check if their proposal is really a new idea or if something very similar or identical has already been submitted or maybe even implemented. To support this step, we created a card that uses AI to identify such matching standard AI capabilities or other ideas submitted in the **AI Center Of Excellence workspace** through this wizard.

3. Now move on to the 3rd step **Refine Solution Proposal** by clicking on it in the top wizard breadcrumb. Similar to last 2 steps, add the widget --> card --> **Refined Solution**.
<br>![save step UI](/exercises/ex3/images/03_04_0070.png)

In this step, the users should refine the **Solution Proposal** with the help of AI which pre-generates the solution text for the user to make their respective changes.

4. Navigate to next and final step **Review and Publish Idea** and add the **Publish idea** card to it, similar to all the steps above. 
<br>![save step UI](/exercises/ex3/images/03_04_0080.png)
   
The last step of this stage is **Done** which is automatically generated at the end of every phase. No need to do anything here, as it has already been populated.
   

### Exercise 3.2.3 Edit steps in stage Idea to Implementation

1. Select the **Idea to Implementation** stage from the top level tab within the Guided Experience. You will see the steps of this stage as defined in the Guided Process - *Define BVP Scope*, *Implementation Plan* and *Initiate MVP Implementation*.
<br>![select 2nd stage](/exercises/ex3/images/03_04_0090.png)

2.	In the same way as before, fill the steps of this stage as well. First, for the step **Define MVP Scope** step, add the card with the same name.
<br>![add step 1 UI](/exercises/ex3/images/03_04_0100.png)

3.	Next, add the card **Implementation Plan** to the second step with the same name.
<br>![add step 2 UI](/exercises/ex3/images/03_04_0110.png)

4.	Finally, add the card **Initiate MVP** to the step **Initiate MVP implementation**.
<br>![add step 3 UI](/exercises/ex3/images/03_04_0120.png)

Like the previous stage, the last step of this stage is too **Done**. There is no action needed from your side as it's auto-generated and pre-configured.

Now, you are done with adding the step UIs for each step of the Guided Experience. 
You might of course add further cards or widgets to the different steps, for example to provide the users with additional help and information like how-to videos and instructions.

6.	Click **Publish** to make your new page available to workspace users. Permissions??? In the pop-up, click **Publish** to submit all changes in the workpage including the whole Guided Experience configuration and setup.
<br>![publish wizard](/exercises/ex3/images/03_04_0130.png)

optionally, you can add a feed update message, which will inform all users that you have added a Guided Experience to your workspace.
<br>![feed update](/exercises/ex3/images/03_04_0140.png)

---

## 3.3 (Optional) Add a UI card to view the submitted ideas

In Exercise 3.1, you have created the workpage **Use Case Repository** where employees of your organization can manage their AI specific ideas in the overall **AI Center of Excellence** workspace. 
Then in Exercise 3.2, You have added a **Guided Experience** to this new workpage which enables the employees to create new ideas and take it towards realization.
Now, you will add a UI card that shows all the AI based ideas / usecases that all employees have added and their respective status. You can interact with these ideas, vote or add comments on them.

1. Ensure that you are in the newly created **Use Case Repository** workpage and you have switched into the edit mode. Gettinginto edit mode is exactly same as Exercise 3.2.3 step 1 above. You use the pencil icon from the floating toolbar on the right-middle margin of the workpage.

2.  Create a new section at the bottom of the page. Hover over the **Wizard** section, that you created in Exercise 3.2, and click on the **Add Section** at the bottom-middle border of this section. Select **Freestyle** this time, since you will add a UI integration card in this section.
<br>![add card section](/exercises/ex3/images/03_03_0010.png)

3.  In the newly created section, click on the **add** button (or the **add content** within the drop-down of the add option).
<br>![add card section](/exercises/ex3/images/03_03_0020.png)

4.  Select the **cards** tile, search for **All Ideas** card, select the card listed there and in the next screen click **save** to add it to the section.
<br>![add card section](/exercises/ex3/images/03_03_0030.png)

5.  You would see the added card at the bottom of the workpage with some existing ideas (pre-created as examples) and as and when users will create new ideas (in Exercise 4), these ideas will start appearing in this UI card.
<br>![add card section](/exercises/ex3/images/03_03_0040.png)

---

## Summary

You've now added a **Use case repository** page to your workspace that contains a wizard that guides users throught he process of submitting an idea for an AI use cases sand a card that lists all the ideas and their respective status. In the next exercise, you will experience your workspace from a user perspective.

Continue to - [Exercise 4 - Experience SAP Build Work Zone and your workspace as an end user](../ex4/README.md)
