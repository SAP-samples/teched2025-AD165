# Exercise 4 - Experience SAP Build Work Zone and your workspace as an end user

In this exercise, you will submit an AI use case using the wizard you just created. You will also use SAP Build Work Zone AI capabilities to generate texts more easily, summarize a blog post, and interact with Joule. 

> **&#9432;** Comment


## <a id="ai-feed"></a> Exercise 4.1 Use generative AI to create a status update

After completing these steps you will have sent a status update to all users.

1. Navigate back to the Home page of SAP Build Work Zone by clicking Home in the Work Zone menu.
<br>![Go to Home](/exercises/ex3/images/03_01_0010.png)
2. On the right side of the Home page beneath the banner, there is a feed widget where users with the required permission can share an update with the whole company. 
<br>![Workpage tile](/exercises/ex3/images/03_01_0020.png)
3. Click the **Generate text with AI** icon to get some help with writing your feed.
<br>![Create Page](/exercises/ex3/images/03_01_0030.png)

4. Enter a prompt of your choice into the Ask AI field, e.g. "write a short announcement that SAP TechEd has started in Berlin and virtually and there are amazing sessions to be followed online" and click the **Send** icon. 
<br>![Add section](/exercises/ex2/images/02_01_0040.png)
5. Read the generated text and decide if that is what you would like to post (maybe after some adjustments). In this case, click **Accept**. Otherwise, you can either click **Retry** which will make AI generate a new text from the same prompt, or **Discard** which will remove the prompt, so you can start again from scratch.
6. Once you accept a text, it is added to the input field. You can now further edit it or simply click the **Share** button.
7. You can also use text generation when commenting. Choose one of the entries in the feed and click the **Comment** button. Create a comment using text generation in the same way as the status update.


## <a id="ai-summarization"></a> Exercise 4.2 Use text summarization to quickly grasp the content of a blog post

After completing these steps you will have created a summary of a blog post with the help of AI.

1. Click on the **Build, Deploy, and Extend AI Agents with Joule Studio** blog post in the Feed. If you cannot see it there, you could also just search for it by typing **Joule Studio** into the search window and clicking on the blog post or knowledge base entry in the search results list. 
  
2. After the blog post opens, click the **Summarize** button.
3. Read the summary.
   

## <a id="ai-doc-grounding"></a> Exercise 4.3 Experience document grounding in SAP Joule

Document Grounding is the process of making a LLM refer to specific documents to generate more accurate and relevant responses. This way you can feed Joule with specific documents of your company (like internal policies, reports and documents), so that Joule can give more accurate and relevant answers.

1. 


## <a id="run-wizard"></a> Exercise 2.4 Use the Guided Experience to submit an AI Use Case

After completing these steps you will have submitted an AI Use case using the wizard you created in exercise 3.

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
   

## <a id="mobile-start"></a> Exercise 2.5 Experience SAP Build Work Zone on a mobile device

1.	In the same way as before, fill the steps of this stage as well. First, add the card **Define MVP Scope** to the step with the same name.
2.	Next, add the card **Implementation Plan** to the second step.
3.	Finally, add the card **Initiate MVP** to the step **Initiate MVP implementation**.

Now, you are done. The wizard is completely configured. You might of course add further cards or widgets to the different steps, for example to provide the users with additional help and information like how-to videos and instructions.

6.	Click **Publish** to make your new page available to workspace users. Permissions??? In the pop-up, click **Publish** again.
<br>![](/exercises/ex2/images/02_02_0010.png)

## Summary

You've now added a **Use case repository** page to your workspace that contains a wizard that guides users throught he process of submitting an idea for an AI use case at ACME Corp, defining the MVP, and initiating the implementation. In the next exercise, you will experience your workspace from a user perspective.

Continue to - [Exercise 3 - Excercise 3 ](../ex3/README.md)
