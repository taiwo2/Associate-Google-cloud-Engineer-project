## Implementing Cloud SQL
##Setup
For each lab, you get a new Google Cloud project and set of resources for a fixed time at no cost.

Sign in to Qwiklabs using an incognito window.

When ready, click Start lab.

Note your lab credentials (Username and Password). You will use them to sign in to the Google Cloud Console.

Click Open Google Console.

Click Use another account and copy/paste credentials for this lab into the prompts.
If you use other credentials, you'll receive errors or incur charges.

Accept the terms and skip the recovery resource page.

## Task 1. Create a Cloud SQL database
In this task, you configure a SQL server according to Google Cloud best practices and create a Private IP connection.

On the Navigation menu (Navigation menu icon), click **SQL**.<br>
Click Create instance.<br>
Click Choose MySQL.<br>
Specify the following, and leave the remaining settings as their defaults:<br>
![setup](./setup.png) <br>

##Provision the right amount of vCPU and memory. To choose a **Machine Type**, click the dropdown menu, and then explore your options.
For this lab, select standard from the dropdown menu, and then select 1 vCPU, 3.75 GB. <br>

Next, expand the Storage section and then choose Storage type and Storage capacity. <br>
Expand the Connections section. <br>

Select Private IP. 

In the Network dropdown, select default.

Click the Set up Connection button that appears.

In the panel to the right, click Enable API, click Use an automatically allocated IP range, click Continue, and then click Create Connection.

Click Create Instance at the bottom of the page to create the database instance.##