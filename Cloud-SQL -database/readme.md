## Implementing Cloud SQL
![setup](./implementation.png)

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

Provision the right amount of vCPU and memory. To choose a **Machine Type**, click the dropdown menu, and then explore your options.
For this lab, select standard from the dropdown menu, and then select 1 vCPU, 3.75 GB. <br>

Next, expand the Storage section and then choose Storage type and Storage capacity. <br>
Expand the Connections section. <br>

Select Private IP.  <br>

In the Network dropdown, select default.  <br>

Click the Set up Connection button that appears.  <br>

In the panel to the right, click Enable API, click Use an automatically allocated IP range, click Continue, and then click Create Connection.  <br>

Click Create Instance at the bottom of the page to create the database instance.  <br>
![instance](./createinstance.png) <br>
## Configure a proxy on a virtual machine

When your application does not reside in the same VPC connected network and region as your Cloud SQL instance, use a proxy to secure its external connection.<br>
In order to configure the proxy, you need the Cloud SQL instance connection name. <br>

On the Navigation menu (Navigation menu icon) click Compute Engine. <br>

Click SSH next to wordpress-proxy. <br>

Download the Cloud SQL Proxy and make it executable: <br>
      ##wget https://dl.google.com/cloudsql/cloud_sql_proxy.linux.amd64 -O cloud_sql_proxy && chmod +x cloud_sql_proxy

In order to start the proxy, you need the connection name of the Cloud SQL instance. Keep your SSH window open and return to the Cloud Console. <br>

On the Navigation menu (Navigation menu icon), click SQL. <br>

Click on the wordpress-db instance and wait for a green checkmark next to its name, which indicates that it is operational (this could take a couple of minutes). <br>

Note the Instance connection name; it will be used later and referred to as [SQL_CONNECTION_NAME]. <br>

In addition, for the application to work, you need to create a table. Click Databases. <br>

Click Create database, type wordpress, which is the name the application expects, and then click Create. <br>

Return to the SSH window and save the connection name in an environment variable, replacing [SQL_CONNECTION_NAME] with the unique name you copied in a previous step: <br>

    ##export SQL_CONNECTION=[SQL_CONNECTION_NAME]
To verify that the environment variable is set, run:

    ##echo $SQL_CONNECTION
The connection name should be printed out.

To activate the proxy connection to your Cloud SQL database and send the process to the background, run the following command:
    ##./cloud_sql_proxy -instances=$SQL_CONNECTION=tcp:3306 &