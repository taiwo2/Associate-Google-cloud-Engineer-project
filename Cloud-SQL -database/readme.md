## Implementing Cloud SQL
          ##Setup
For each lab, you get a new Google Cloud project and set of resources for a fixed time at no cost.

Sign in to Qwiklabs using an incognito window.

Note the lab's access time (for example, 1:15:00), and make sure you can finish within that time.
There is no pause feature. You can restart if needed, but you have to start at the beginning.

When ready, click Start lab.

Note your lab credentials (Username and Password). You will use them to sign in to the Google Cloud Console.

Click Open Google Console.

Click Use another account and copy/paste credentials for this lab into the prompts.
If you use other credentials, you'll receive errors or incur charges.

Accept the terms and skip the recovery resource page.

## Task 1. Create a Cloud SQL database
In this task, you configure a SQL server according to Google Cloud best practices and create a Private IP connection.

On the Navigation menu (Navigation menu icon), click SQL.
Click Create instance.
Click Choose MySQL.
Specify the following, and leave the remaining settings as their defaults:
![setup](./setup.png)

Provision the right amount of vCPU and memory. To choose a **Machine Type**, click the dropdown menu, and then explore your options.