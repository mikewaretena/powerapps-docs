<properties
    pageTitle="PowerApps: Automate tasks by creating Logic Flows"
    description="Create Logic Flows to automatically perform one or more actions, such as sending mail, when one or more conditions are met, such as someone adding a row to a SharePoint list."
    services="powerapps"
    documentationCenter="na"
    authors="AFTOwen"
    manager="dwrede"
    editor=""
    tags=""
 />
<tags
    ms.service="powerapps"
    ms.devlang="na"
    ms.topic="get-started-article"
    ms.tgt_pltfrm="na"
    ms.workload="na"
    ms.date="11/02/2015"
    ms.author="anneta"/>

# Create Logic Flows in PowerApps#
Create a logic flow to perform a task automatically when a condition triggers an action. For example, create a logic flow that notifies you by mail as soon as someone adds a row to a SharePoint list. In this scenario, adding a row is the trigger, and sending mail is the action.

**Prerequisites**

- An account, such as Dropbox, OneDrive, or SharePoint, for storing files in the cloud
- An Office 365 account (from which you can send email)
- Chrome browser

## Create a trigger

1. In Chrome, open [powerapps.com](), and then click **Create a flow**.

    ![Click Logic on the right](./media/get-started-powerflow/landingpage.png)

3. Click **Create from blank**.

    ![Create Logic from blank](./media/get-started-powerflow/gallery.png)

4. In the text box that says **How would you like to start?**, type **SharePoint**.

1. In the list of actions, click **SharePoint Online - When a new item is created**

    ![Sharepoint triggers](./media/get-started-powerflow/add-sp-data.png)

5. If you haven't already connected your SharePoint Online account to PowerApps, click **Sign in to SharePoint Online**, and then provide your credentials.

6. In the **SITE URL** box, type or paste the URL of the SharePoint site that contains the list you want to use.

  **Important:** Include only the site URL, not the full path of the list.

  ![Enter site](./media/get-started-powerflow/enter-site.png)

1. Under **LIST NAME**, click the down arrow to show the names of all lists in the site you specified.

  **Note:** If **Could not retrieve values** appears, correct your site URL.

8.  Click the name of a list, name your PowerFlow in the box near the bottom of the screen, and then click **Done**.

    ![Click the done button](./media/get-started-powerflow/done2.png)

## Create the action ##
In this procedure, you'll add an action to send email in your logic and then you'll test that action. By following these steps, you'll learn the basics of actions and how to pass parameters between steps in your logic to make it work the way you want.

1. In the list of your logic, click the edit icon, which looks like a pencil, next to the logic that you created in the previous procedure.

2. Click the "+" button, and then click **Add action**

    ![Add action](./media/get-started-powerflow/addaction.png)

2. In the box that shows **What would you like to do next?**, type or paste **send email**, and then click **Office365 - Send Email**.

  ![List of actions](./media/get-started-powerflow/send_email.png)

1. If prompted, provide your Office 365 credentials.

4. In the form that appears, type a subject in the **Subject** box and your email address in the **To** box.

    ![The list of parameters](./media/get-started-powerflow/listfields2.png)

5. In the **Body** box, type or paste **Item added to a list:**, and then click a parameter (such as **Title**) to add a placeholder for it to your message.

  **Note:** The available parameters reflect the column headings of whatever list you specify.

    ![Token added to the field](./media/get-started-powerflow/message-token2.png)

4. Type the end of your message, including any other parameters you want to include, and then click **Done** at the bottom of the screen.

    The list of your logic reflects your changes.

## Test your Logic ##

1. On the main page for the SharePoint Online list, click **new item**.

    ![Adding a row](./media/get-started-powerflow/addrow.png)

3. Specify data in each field, and then click **Save**.

    Within a minute, an email notifies you of the changes.

## Next Steps ##

- [Add steps](advanced-parameters-powerflow.md), such as different ways to be notified, to your logic.