# Exercise 5 (optional) - Learn about Business Content integration and access SAP Build Work Zone from a mobile device

In this exercise, you will learn how business content from an SAP system can be integrated into SAP Build Work Zone. Finally, you will download the native SAP Mobile Start app to your own smartphone and open your SAP Build Work Zone site there.

> [!NOTE]
> Business content can be integrated in different ways, for example by creating UI integration cards that consume content from an OData service in an SAP system by making use of the connectivity services of SAP Business Technology Platform. Another option of integrating business content is called **`Content Federation`**. This federation scenario consists of a content exposure step where an administrator selects which content should be made available in SAP Build Work Zone (which is done on the content provider side, e.g. in an SAP S/4HANA system), and a content consumption step (done in SAP Build Work Zone). The exposure usually happens at role level and the exposure scope contains all content entities assigned to the selected roles, such as groups, catalogs, pages, and spaces.
>
> It is important to understand that the apps are not replicated or transported to SAP BTP, but the exposure provides meta data to allow SAP Build Work Zone to launch the applications that continue to run in the provider system.


# Exercise 5.1 Explore the administration environment for Business Content integration

After completing this exercise, you’ll be familiar with the administration of business content in SAP Build Work Zone. You already used this environment, when you were creating an app for your UI integration card in exercise 2. So let us go back there.

1. Click the user avatar in the upper right corner and select **Administration Console**.
2. In the menu on the left, select **External Integrations** > **Business Content**, then click the **Content Manager** button.
   
---

## What is the Content Manager?
The Content Manager is the tool you use to manage the business content items for your subaccount: apps, catalogs, groups, roles, spaces and pages, and shell plugins). It lets you:
- Create different content entities, e.g. apps, spaces, pages, roles.
- Open content entities for editing
- Search for content entities
- Import and export content entities

3. Navigate to the Content Explorer by clicking the **Content Explorer** button.

---

## What is the Content Explorer?
The Content Explorer displays the available content providers and allows administrators to inspect the content items provided by them, such as apps and shell plugins, and add them to your subaccount.

In general, it is recommended to automatically add all content items to the subaccount, when you add a new content
provider, but you might also choose to pick and choose only specific roles to be available using the Content Explorer.

4. Click the **S/4HANA** tile to open the Content Provider and see the exposed roles.
   
5. Click any of the roles to navigate into it and see the assigned apps and on the Spaces tab also the assigned space.

6. Click the Channel Manager icon on the left to open the Channel Manager.

---

## What is the Channel Manager?
Administrators use the Channel Manager to define, edit, and get updates from remote content providers. When a new subaccount is configured, the *HTML5 Apps* content channel is available by default. It enables administrators to easily integrate apps deployed on SAP BTP to Work Zone. The Channel Manager lets you:
- Define new content channels based on SAP BTP destinations
- Configure settings for content channels
- Update a content channel manually. 

Instead of the manual option, it is possible to set up automatic updates so that the content of the provider in the Channel Manager is updated automatically every time there are changes to the exposed content of the provider.

---

# Exercise 5.2 Access SAP Build Work Zone on a mobile device

