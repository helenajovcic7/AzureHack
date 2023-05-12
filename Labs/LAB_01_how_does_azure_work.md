---
lab:
    title: '01 - How does Azure work?'
    module: 'Azure Core'
---

# Lab 01 - How does Azure work?
# Student lab manual

## Challenge scenario

You will learn fundamentals of Azure administration capabilities - login to portal, create and manage resource groups and create and manage resources. 

## Objectives

In this lab, you will:

+ Create resource groups and deploy resources to resource groups
+ Use resource tags
+ Restrict deployment and deletion
+ Work with cost limits



## Challenges


<details>
  <summary>Create 2 resource groups - Production (West Europe) and Test (North Europe)</summary>

#### Task 1: Create resource groups

In this task, you will use the Azure portal to create resource groups and create a disk in the resource group.

1. Sign in to the [**Azure portal**](http://portal.azure.com).

1. In the Azure portal, search for and select **Resource groups**, click **+ Create**:

1. Type resource group name ("Production") and select Region West Europe

1. Click **Review + Create** and then click **Create**.

    >**Note**: Wait until the resource group is created. This should take less than a minute.

1. Repeat for "Test" and deploy to North Europe

</details>

<details>
  <summary>Tag a resource group with a tag Department "IT"</summary>

#### Task 2: Tag resource group

1. Open the resource group
1. Click Tags in the left menu
1. Type the following values

    |Name|Value|
    |---|---|
    |Department| IT |

1. Click Apply

</details>

<details>
  <summary>Add a Storage account named "myfirststorageaccount" to Test resource group in North Europe</summary>

### Task 3: Create a storage account in Test resource group

1. In the Azure portal, search for and select **Storage accounts**, click **+ Create**. Add the following settings

    |Setting|Value|
    |---|---|
    |Resource group| **tTst** |
    |Storage account name| **myfirststorageaccount** |
    |Region| **North Europe** |
    |Redindancy| **Localy redundant storage** |

1. Note that storage accounts have to be globally unique. Pick a new unique name

1. Click **Review + Create** and then click **Create**.

</details>

<details>
  <summary>Create a policy to only allow West Europe  and North Europe and appy to your resource groups</summary>


</details>

<details>
  <summary>Create a resource lock to disable deletion of Production resource group</summary>


</details>






#### Task 2: Move resources between resource groups 

In this task, we will move the disk resource you created in the previous task to a new resource group. 

1. Search for and select **Resource groups**. 

1. On the **Resource groups** blade, click the entry representing the **az104-03a-rg1** resource group you created in the previous task.

1. From the **Overview** blade of the resource group, in the list of resource group resources, select the entry representing the newly created disk, click **Move** in the toolbar, and, in the drop-down list, select **Move to another resource group**.

    >**Note**: This method allows you to move multiple resources at the same time. 

1. Below the **Resource group** text box, click **Create new** then type **az104-03a-rg2** in the text box. On the Review tab, select the checkbox **I understand that tools and scripts associated with moved resources will not work until I update them to use new resource IDs**, and click **Move**.

    >**Note**: Do not wait for the move to complete but instead proceed to the next task. The move might take about 10 minutes. You can determine that the operation was completed by monitoring activity log entries of the source or target resource group. Revisit this step once you complete the next task.

#### Task 3: Implement resource locks

In this task, you will apply a resource lock to an Azure resource group containing a disk resource.

1. In the Azure portal, search for and select **Disks**, click **+ Create** and specify the following settings:

    |Setting|Value|
    |---|---|
    |Subscription| the name of the subscription you are using in this lab |
    |Resource Group| click **create new** resource group and name it **az104-03a-rg3** |
    |Disk name| **az104-03a-disk2** |
    |Region| the name of the Azure region where you created the other resource groups in this lab |
    |Availability zone| **None** |
    |Source type| **None** |

1. Set the disk type and size to **Standard HDD** and **32 GiB**, respectively.

1. Click **Review + Create** and then click **Create**.

1. Click **Go to resource**.

1. On the Overview page of the Disk, click the name of the resource group, **az104-03a-rg3**.

1. On the **az104-03a-rg3** resource group blade, click **Locks** then **+ Add** and specify the following settings:

    |Setting|Value|
    |---|---|
    |Lock name| **az104-03a-delete-lock** |
    |Lock type| **Delete** |
    
1. Click **OK**    

1. On the **az104-03a-rg3** resource group blade, click **Overview**, in the list of resource group resources, select the entry representing the disk you created earlier in this task, and click **Delete** in the toolbar. 

1. When prompted **Do you want to delete all the selected resources?**, in the **Confirm delete** text box, type **yes** and click **Delete**.

1. You should see an error message, notifying about the failed delete operation. 

    >**Note**: As the error message states, this is expected due to the delete lock applied on the resource group level.

1. Navigate back to the list of resources of the **az104-03a-rg3** resource group and click the entry representing the **az104-03a-disk2** resource. 

1. On the **az104-03a-disk2** blade, in the **Settings** section, click **Size + performance**, set the disk type and size to **Premium SSD** and **64 GiB**, respectively, and click **Save** to apply the change. Verify that the change was successful.

    >**Note**: This is expected, since the resource group-level lock applies to delete operations only. 

#### Clean up resources

   >**Note**: Do not delete resources you deployed in this lab. You will be using them in the next lab of this module. Remove only the resource lock you created in this lab.

1. Navigate to the **az104-03a-rg3** resource group blade, display its **Locks** blade, and remove the lock **az104-03a-delete-lock** by clicking the **Delete** link on the right-hand side of the **Delete** lock entry.

#### Review

