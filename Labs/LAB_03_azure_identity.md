---
lab:
    title: '03 - Identities and governance'
    module: 'Azure Core'
---

# Lab 01 - Managing Azure?
# Student lab manual

## Challenge scenario

You will learn fundamentals of Azure administration capabilities - Users, Role Based Access Control

## Objectives

In this lab, you will:

+ Create a new Azure Active Directory tennant
+ Create a new AD User
+ Assign permission to the new user
+ Create a custom role
+ Create an AD group



## Challenges



<details>
  <summary>Create a new Azure Active Directory</summary>

#### Task 1: Create a new Azure Active Directory


1. Sign in to the [**Azure portal**](http://portal.azure.com).

1. In the Azure portal, search for and select **Azure Active Directory**:
1. Select **Manage tennants** and clikc Create:
1. Select Azure Active Directory and click Next: Configuration
1. Select a globaly unique name for your domain (note - it cannot be changed later!). The name will be <yourname>.onmicrosoft.com

    ![image](../Images/03_01.png)

</details>

<details>
  <summary>Switch between directories</summary>

#### Switch between directories

1. Click on the wheels icon top right

  ![image](../Images/03_01.png)

</details>





<details>
  <summary>Create a new user "firstuser" in the new directory and assign him "Groups Administrator" permission</summary>

#### Task 2: Create a new user "firstuser" in the new directory and assign him contributor permission

1. In the Azure portal, search for and select **Azure Active Directory**:
1. Make sure the right directory is created
1. Click Users in the left menu, New user, Create new user
1. Type the following values

    |Name|Value|
    |---|---|
    |User principal name| firstuser |
    |Display name| First User |

    ![image](../Images/03_01.png)

1. Click Next: Properties (you can fill optional infor)
1. Click Next: Asignments
1. Add Role and search for "Groups Administrator" and click select
1. Review + Create
1. alternatively, you can add group after the user is created via Assigned roles


    ![image](../Images/03_01.png)

  Note that we cannot add any Azure permission, since the thew Active Directory does not contain any subscriptions

</details>



<details>
  <summary>Add the new user as a reader to your Azure subscription</summary>

### Task 3: Add the new user as a reader to your Azure subscription

1. Switch back to your original directory
1. Go to Subscriptions and choose your subscription
1. In the left menu, and click next

    ![image](../Images/03_01.png)

1. Click select Members and search for firstuser@<yourdomain>.onmicrosoft.com. Dobule click to select
1. Review + Assign



</details>


<details>
  <summary>Login to Azure portal with the new user</summary>

### Task 4: Login to Azure portal with the new user<

1. Open an in private window
1. Navigate to portal.azure.com
1. Login (and change password if needed)
1. Switch directory to the directory with the subscription
1. View the subscription
1. Close the browser

</details>

<details>
  <summary>Create a group called "allguests" for all **guest** users in your tenant and add "firstuser"</summary>

1. In the Azure portal, search for and select **Azure Active Directory**
1. Select Groups, New Group

    ![image](../Images/03_01.png)

1. Select allguests group and select Members in left menu
1. Select Add Members and find firstuser

    ![image](../Images/03_01.png)

</details>

<details>
  <summary>Optional - add your private hotmail or gmail as a reader and add them to the allguests group</summary>



</details>





<details>
  <summary>Move the storage account you created before to "Production" resource group </summary>

1. In the Azure portal, search for and select **Storage accounts**
1. Select your storage account
1. Click Move and Move to another resource group

    ![image](../Images/02_05.png)

1. Select **Production** and click next and observe a failed validation

    ![image](../Images/02_06.png)

</details>

