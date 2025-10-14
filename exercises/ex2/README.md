# Exercise 2 - Exercise 2 Create a submission wizard for AI ideas

In this exercise, you will create a new page Use Case Repository and a wizard (also known as Guided Experience) that supports users in submitting their ideas for AI use cases in ACME Corp. 

> **&#9432;** Wizards allow administrators or key users to simplify complex workflows and processes by guiding their users through tasks in a clear and sequential way. Each wizard consists of one or more stages; each stage is composed of one or more steps.


## Exercise 2.1 Create a new page in your workspace

After completing these steps you will have created a new page that will host a Use Case Repository and allow users to submit use case ideas.

1. On the right side of the menu, click the + icon to add a new tab to the navigation bar.
<br>![Add menu entry](/exercises/ex2/images/02_01_0010.png)
2. The new menu entry should lead users to a workpage, so click the **Workpage** tile.
<br>![Workpage tile](/exercises/ex2/images/02_01_0020.png)
3. In the pop-up, keep **New Page**, select folder **Workpages** to store your new page, enter **Use Case Repository** as *Tab Name*, and click **Add**.
<br>![Create Page](/exercises/ex2/images/02_01_0030.png)

The new page is created and you can now start populating it with content. Before you add, the wizard, add a text widget to explain what the use case repository is about.

4. In the middle of the page, click **Add**. This way a freestyle section with one cell is created. You could also click the dropdown link and select **Freestyle** there.
<br>![Add section](/exercises/ex2/images/02_01_0040.png)
5. Hover the new section and click the **Add Content** button that appears.
6. Select the **Text** widget from the widget gallery.
7. Use text generation to create a welcome text for this page. You might use the prompt
```
Write a welcome text for a use case repository page where users can submit AI use cases and see the ideas of others
```
8. Edit the text to your liking, e.g. enlarge the title and make it bold.

## Exercise 2.2 Add a rotating banner to the page 

After completing these steps you will have added a widget that describes the steps necessary to submit an AI use case in a nice visual way.

1. Add a second column to the section as you did it on the *Welcome* page before and add a **Rotating Banner** widget to this column.
2. Upload the **start.jpg** image to the rotating banner and enter **Step 1** as *Title* and **Start the Use Case submission process below** as *Description*. Feel free to adjust the image zoom or display window.
3. Move the *Text placement* to the **Top Left**
4. Then click the **+Slide** button on the upper left side of the *Rotating Banner Widget* pop-up.
5. Upload the **answer.jpg** image to the rotating banner and enter **Step 2** as *Title* and **Answer the questions with your best knowledge** as *Description*. Select *Text placement* as **Top Left** again.
6. Finally, add another slide in the same way, upload the **IT.jpg** image to the rotating banner and enter **Step 3** as *Title* and **Wait for IT to approve / come back at your idea and see it represented down below** as *Description*.
7. Now click **Save**.
   

## Exercise 2.3 Create a wizard based on a Guided Process from SAP Build Process Automation

After completing these steps you will have created the skeleton for your wizard with some pre-defined stages and steps.

1. Hover the section that you just filled with content and click the **Add section** button below it to add the wizard. Select **Wizard** in the pop-up.

2. 


## Exercise 2.3 Create a wizard based on a Guided Process from SAP Build Process Automation

After completing these steps you will have created the skeleton for your wizard with some pre-defined stages and steps.

1. In your workspace, navigate to the page Use-Case Repository
<br>![](/exercises/ex2/images/02_01_0010.png)

2.	Insert this line of code.
```abap
response->set_text( |Hello ABAP World! | ). 
```



## Exercise 2.2 Sub Exercise 2 Description

After completing these steps you will have...

1.	Enter this code.
```abap
DATA(lt_params) = request->get_form_fields(  ).
READ TABLE lt_params REFERENCE INTO DATA(lr_params) WITH KEY name = 'cmd'.
  IF sy-subrc = 0.
    response->set_status( i_code = 200
                     i_reason = 'Everything is fine').
    RETURN.
  ENDIF.

```

2.	Click here.
<br>![](/exercises/ex2/images/02_02_0010.png)

## Summary

You've now ...

Continue to - [Exercise 3 - Excercise 3 ](../ex3/README.md)
