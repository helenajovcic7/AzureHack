---
lab:
    title: '07 - Plan and Monitor Azure'
    module: 'App services'
---

# Lab 07 - Plan and Monitor Azure

## Challenge scenario

We will now do some more practical excercises. 
First, our management would like to know, how much would all the resources, that we have deployed, actually cost. 
Then we will make our lifes easier by using documentation and ARM templates
Last, but not least, we will set some foundational monitoring


The solutions will not be provided - you should have enough experience by now to explore Azure Portal on your own. In case you do have trouble, there are some hints available, but you can also ask your facilitator for help.

## Objectives

In this lab, you will:

+ Create a detailed cost estimate
+ Explore Azure architecture center and ARM templates library. You will deploy a template from the libraty
+ Use Azure Monitor


## Challenges

### Challenge 1 - First, cost

Our management has a task - We need to do a cost estimate

1. Navigate to https://azure.microsoft.com/en-us/pricing/calculator/
1. Sign in to the page
1. Create a new Estimate
1. Add all the services we have created up until now, with correct sizes. Try to remember all different components
1. Export the cost estimate



<details>
  <summary markdown="span">Hints</summary>

    3 Virtual machines
    4 Disks
    Virtual Networks
    IP Addresses

</details>
<br/><br/>


### Challenge 2 - Azure Monitor

1. Navigate to Azure monitor
1. Find Activity Log
1. Go to Metrics, and filter to your virtual machines



<details>
  <summary markdown="span">Hints</summary>


</details>
<br/><br/>

### Challenge 3 - Cleanup

1. Delete all resources in the subscription - easiest is to delete both Production and Test resource groups
