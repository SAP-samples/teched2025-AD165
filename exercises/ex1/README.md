# Exercise 1 - Build your Center of Excellence workspace

In this exercise, we will create a public workspace from a template that you first upload to your SAP Build Work Zone tenant. As you will be working in a shared environment, it is important that you give all objects you create easily identifiable names, e.g. containing your 3-digit user ID which you can also find on your desktop.


## Exercise 1.1 Open the SAP Build Lobby and navigate to SAP Build Work Zone

1. To launch SAP Build Work Zone, go to the [Build Lobby](https://ad165-m3ep4xn0.eu10.build.cloud.sap/lobby) and login with the user that is available on your desk and password **Acce$$teched25**.
<br>![Build Lobby](/exercises/ex1/images/01_01_0010.png)

3. to be completed

4. <br>![(/exercises/ex1/images/01_01_0010.png)

5.	Insert this line of code.
```abap
response->set_text( |Hello World! | ). 
```



## Exercise 1.2 Create a workspace from your template

After completing these steps you will have created a Center of Excellence workspace and made some initial settings. This step does not need to be done by an administrator, but according to your preferences, you might allow every user or only a specific group of key users to create workspaces to share knowledge and collaborate with colleagues.

1.	In the menu bar, navigate to *Workspaces > New Workspace*.
<br>![New workspace](/exercises/ex1/images/01_03_0010.png)

2.	Click the left tile to create a public workspace.
<br>![Public workspace](/exercises/ex1/images/01_04_0010.png)

3. Enter name: **AI Center of Excellence** and a description of your choice.
4. Select the Center of Excellence abc workspace template that you just uploaded. [GB] ??????
6. Remove the checkmark next to *Allow users to join this workspace* and click **Next**. You could also skip the more advanced settings of the next pages at this time by clicking *Finish* right away, but let us have a short look at the options.
<br>![Workspace creation wizard](/exercises/ex1/images/01_05_0010.png)

7. You can leave the *Member Participation* settings as is. Simply click **Next**.
<br>![Member settings](/exercises/ex1/images/01_06_0010.png)   

8. On the *Non-Member Participation* page, set *Collaboration Level* to **None: All collaboration tools and member details are hidden** and click **Finish**.
<br>![Non-member settings](/exercises/ex1/images/01_07_0010.png)


## Exercise 1.3 Edit your workspace header

After completing these steps you will have designed a beautiful entry page for your AI Center of Excellence workspace. 

The workspace has been created and you automatically navigate to it. You can now start editing it, but before you do this, you should download some images and files you can use during the exercise.

2. Right-click the link [exercises/ex1/samples](https://github.com/SAP-samples/teched2025-AD165/tree/main/exercises/ex1/samples) and open the folder in a new browser tab.
3. Click the content.zip file and use the download button to download the zip file to your local computer.
4. Extract the zip file into a folder of your choice.

#### Exercise 1.3.1 Exchanging the cover photo

As a first step, you will change the cover photo to something that fits the purpose of the workspace.

1. Click **Edit Cover Photo**, then select **Upload Photo** from the dropdown list.
<br>![Edit Cover Photo](/exercises/ex1/images/01_03_0030.png)   

2. Select the AI_Banner.jpg from the folder to which you extracted the image files.
<br>![Select AI_Banner](/exercises/ex1/images/01_03_0040.png)   

3. If you want, you can zoom into the image by using the slider. Select a beautiful display window by dragging the image up and down or left and right. Then click **Save**.
<br>![Zoom reposition & Save](/exercises/ex1/images/01_03_0050.png)


#### Exercise 1.3.2 Change the avatar of the workspace

You will now change the avatar of the workspace, so you can recognize it more easily in the list of workspaces.

1. Hover the little image next to the workspace titel, then click the **Upload workspace avatar** icon that appears.
<br>![Upload avatar](/exercises/ex1/images/01_03_0060.png)

2. Upload any image from the images folder.
3. Then deselect **Autofit** to be able to zoom and adjust the display window.
<br>![Autofit](/exercises/ex1/images/01_03_0070.png)

5. Zoom into the uploaded image and select a nice detail by dragging the image to the right position.
6. Click **Save changes**.
<br>![Zoom reposition & Save](/exercises/ex1/images/01_03_0080.png)


## Exercise 1.4 Edit the overview page of your workspace

After completing these steps you will have designed a beautiful entry page for your AI Center of Excellence workspace. 
<br><br>
#### Exercise 1.4.1   Add some images to the overview page

1. First, open the workpage editor by clicking the pencil icon on the right of the screen.
<br>![Go to workpage editor](/exercises/ex1/images/01_04_0010.png)

2. Hover the workpage to see the structure according to which the widgets on the page are arranged. You can see that there are several sections in this page. Some of the sections have several (up to 8) columns which themselves can hold several cells.
<br>![Hover structure](/exercises/ex1/images/01_04_0020.png)

4. In the first step, you will add a banner image to the upmost section of the workpage. To do this, you can either drag and drop the banner.png onto the **Drop an image here to upload it** are or click **Or click here to upload an image** and select the banner.png for upload.
<br>![Hover structure](/exercises/ex1/images/01_04_0030.png)

5. Now, change some properties of the section to make it collapsible, so users can save some space on the screen if they want. Move the mouse a bit up till you see the grey frame of the section and click the **Edit section settings** icon [settings icon](/exercises/ex1/images/01_04_0040.png).
<br>![Edit cell settings](/exercises/ex1/images/01_04_0050.png)

6. Change **Padding Bottom (px)** to 20 and set all switches to *On*, so the section is collapsible and open by default and to extend the background to full width. Add **#21275B** as background color. Then click **Save**.
<br>![Change cell settings](/exercises/ex1/images/01_04_0060.png)

7. Now open the cell settings for editing by clicking the **Edit cell settings** icon [settings icon](/exercises/ex1/images/01_04_0040.png).
<br>![Change cell settings](/exercises/ex1/images/01_04_0070.png)

8. Turn **Background** on to get a white frame around the image and click **Save**.
<br>![Background ON](/exercises/ex1/images/01_04_0080.png)

9. Add the image vertical.jpg between the *Welcome* and *How to get started* text widgets in the same way.
<br>![Added Image](/exercises/ex1/images/01_04_0090.png)


<br><br>
#### Exercise 1.4.2   Remove an unneeded section

You do not need the next section, so you are now going to delete it.
Hover the section till you see the grey section frame and select the **Delete section** icon.
<br>![Delete section](/exercises/ex1/images/01_04_100.png)

<br><br>
#### Exercise 1.4.3   Edit the News section

1. In the **News** section, change the title to **Current News**.
<br>![Delete section](/exercises/ex1/images/01_04_110.png)

2. In the leftmost text widget, you will now change the text to announce some AI related news. You can use the text generation capability of SAP Build Work Zone to help you generate a text quickly. 
<br>![Delete section](/exercises/ex1/images/01_04_120.png)

3. Enter a prompt, e.g. Share some exciting news about AI usage at ACME Corp.

Wait for the text to be generated, then accept or discard (to enter a new prompt) or retry with the same prompt and finally share the news.

<br><br>
#### Exercise 1.4.4   Add a Feed widget to the page

1. Hover the **News** section again until an **Add section** button appears below it. Click the button and select **Freestyle** in the pop-up window.
<br>![Add section](/exercises/ex1/images/01_04_122.png)

2. Click the **Add Content** button in the new section.
<br>![Add section](/exercises/ex1/images/01_04_124.png)
  
3. Select the **Feed** widget.
<br>![Add section](/exercises/ex1/images/01_04_122.png)

4. In the Feed widget properties, select **Workspace Status Only** in the *Filter By* field. Change the *Widget Title* to **Workspace Feed**. Then click **Save**.
<br>![Widget properties](/exercises/ex1/images/01_04_126.png)

<br><br>
#### Exercise 1.4.5   Exchange the video

You would like to exchange the video for an AI related one. 

1. Hover the video and click the **Edit widget** icon [settings icon](/exercises/ex1/images/01_04_0040.png).

2. Paste the following URL into the input field beneath **Paste URL**: 
```
https://www.youtube.com/embed/A77g1LKqjFg?si=GVW6OK9tdWip_7n6
```

Then click **Save**.
<br>![Paste URL](/exercises/ex1/images/01_04_130.png)


<br><br>
#### Exercise 1.4.6   Move a widget to a new cell

You would like to move the two elements (text and pink cell) to the right of the video.

1. Hover the section with the video until you see a plus sign to the right of the video. Click the plus icon to add another column to the section.
<br>![Add column](/exercises/ex1/images/01_04_140.png)

2. Drag and drop the content from the left column to the new column. The empty column on the left is automatically deleted.
<br>![Move content](/exercises/ex1/images/01_04_150.png)

<br><br>
#### Exercise 1.4.7  Publish the workpage

1. To make your changes available to users accessing the workspace, click **Publish** on top of the page.
<br>![Publish](/exercises/ex1/images/01_04_160.png)
2. In the publishing pop-up, keep all settings and click **Publish** again. Your changes are now visible to all users of the workspace
<br>![Result Workpage Editing](/exercises/ex1/images/01_04_170.png)



## Exercise 1.5  Add a discussion topic to the Forum
DO with Text Generation

## Summary

You've now created a first version of a Center of Excellence workspace for AI topics based on a template. Now you can enhance it with a guided experience in Exercise 2.



Continue to - [Exercise 2 - Add a Guided Experience to your workspace](../ex2/README.md)

