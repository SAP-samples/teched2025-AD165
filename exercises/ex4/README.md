# Exercise 4 - Experience SAP Build Work Zone and your workspace as an end user

In this exercise, you will submit an AI use case using the wizard you just created. You will also use SAP Build Work Zone AI capabilities to generate texts more easily, summarize a blog post, and interact with Joule. 


## <a id="ai-feed"></a> Exercise 4.1 Use generative AI to create a status update

AI integration in SAP Build Work Zone can help users and administrators to work more efficiently. Let's see how text generation can support users in writing texts. 

After completing these steps you will have sent a status update to all users.

1. Navigate back to the **Overview** page of your AI Center of Excellence workspace.
2. Scroll down to the feed widget where workspace users can share an update with other members and click the **Generate text with AI** icon to get some help with writing your feed.
   
<p align="center"><img src="./images/04_01_0010.png" width="90%" /></p>

3. Enter a prompt of your choice into the Ask AI field, e.g. "Write a status message that you are happy to be part of this AI community" or another prompt about SAP TechEd and click the **Send** icon.
   
<p align="center"><img src="./images/04_01_0020.png" width="90%" /></p>

4. Read the generated text and decide if that is what you would like to post (maybe after some adjustments). In this case, click **Accept**. Otherwise, you can either click **Retry** which will make AI generate a new text from the same prompt, or **Discard** which will remove the prompt, so you can start again from scratch.

<p align="center"><img src="./images/04_01_0030.png" width="70%" /></p>

5. Once you accept a text, it is added to the input field. You can now further edit it or simply click the **Share** button.

<p align="center"><img src="./images/04_01_0040.png" width="90%" /></p>

6. You can also use text generation when commenting. Choose one of the entries in the feed and click the **Comment** button. Create and post a comment using text generation in the same way as the status update.

<p align="center"><img src="./images/04_01_0050.png" width="90%" /></p>
<br>

## <a id="ai-summarization"></a> Exercise 4.2 Use text summarization to quickly grasp the content of a blog post

After completing these steps you will have created a summary of a blog post with the help of AI. To try this functionality, we created another workspace with some sample blog posts for you. You can simply find them via the search.

1. In the search window in the Work Zone shell enter the search term Joule and change the search scope to **Content**, so you do not only search in the current workspace, but in Work Zone content overall.
   
<p align="center"><img src="./images/04_02_0010.png" width="90%" /></p>

2. Click on one of the blog posts in the search result, e.g. the **Build, Deploy, and Extend AI Agents with Joule Studio** blog post. The blog post is opened in the Public workspace where it is stored.

<p align="center"><img src="./images/04_02_0020.png" width="90%" /></p>
  
3. Click the **Summarize** button to receive an AI generated summary of the blog post contents.

<p align="center"><img src="./images/04_02_0030.png" width="90%" /></p>

4. Read the summary.
   
<p align="center"><img src="./images/04_02_0040.png" width="90%" /></p>


## <a id="ai-doc-grounding"></a> Exercise 4.3 Experience document grounding in SAP Joule

Document Grounding is the process of making a LLM refer to specific documents to generate more accurate and relevant responses. This way you can feed Joule with specific documents of your company (like internal policies, reports and documents), so that Joule can give more accurate and relevant answers.

1. 


## <a id="run-wizard"></a> Exercise 2.4 Use the Guided Experience to submit an AI Use Case

After completing these steps you will have submitted an AI Use case using the wizard you created in exercise 3.

1. In the **Persona and Problem Description** step, click **Add widget**.
<br>![Add widget](/exercises/ex4/images/02_04_0010.png)

2. Select the **Cards** tile and choose card **Refine Problem Statement**.
3. You do not need to make any additional settings, just click **Save**.

> **&#9432;** SAP UI Integration cards can easily be created and made available for usage in SAP Build Work Zone with SAP Business Application Studio.

4. Now move on to the next step. Click **Review Matching Proposals**. In this step, the users should check if their proposal is really a new idea or if something very similar or identical has already been submitted or maybe even implemented. To support this step, we created a card that uses AI to identify such duplicate ideas.

5. Add the card  **Matching Solutions** in the same way as before.

> Don't worry about the error message about an undefined problem statement. This will not happen during runtime, as the first step was defined as a mandatory step, so users cannot reach this step without having entered a description of the problem.

6. Move on to step **Define the AI based solution** and add the **Refined solution** card to is as before. This card also uses generative AI to suggest a solution that could then be adapted by the user.

7. Navigate to step **Review and Publish Idea** and add the **Publish idea** card to it.
8. Navigate to the last step of this stage **Done**. No need to do anything here, as it has already been populated.
   


## Summary

You've now added a **Use case repository** page to your workspace that contains a wizard that guides users throught he process of submitting an idea for an AI use case at ACME Corp, defining the MVP, and initiating the implementation. In the next exercise, you will experience your workspace from a user perspective.

Continue to - [Exercise 5 - Excercise 5 ](../ex5/README.md)
