<table width=100% border=>
<tr><td colspan=2><img src="images/spacer.png"></td></tr>
<tr><td colspan=2><h1>EXERCISE SAP Cloud Platform Onboarding - Getting Started in SCP</h1></td></tr>
<tr><td><h3>SAP Partner Workshop</h3></td><td><h1><img src="images/clock.png"> &nbsp;90 min</h1></td></tr>
</table>


## Description
This course provides an introduction to working with the SAP Cloud Platform. We will begin with an understanding of the structure of accounts within the cloud platform, and walk through creating accounts, subaccounts, organizations and spaces.  Finally, we will create a project to model and build a simple application and UI to be deployed. 

For more information about SAP Cloud Platform in general, you might visit:

* SAP Cloud Platform website where you will find useful information and links to various design, sales, learning and support resources
 <https://cloudplatform.sap.com/index.html>
* SAP Help portal for Cloud Platform
<http://help.sap.com/cp>
* openSAP course on SCP concepts  <https://open.sap.com/courses/cp1-3>

In this exercise, you’ll learn how to...

* Create Trial Account
* Create a Project
* Model some Data
* Work with OData
* Create a UI
* Deploy a Sample Application


## Target group

* Developers
* People interested in Developing in SAP Cloud Platform

## Goal

The goal of this exercise is to understand the structure of the SAP Cloud Platform accounts and begin working with SCP by developing a simple example application. 

## Outcomes

1. [Create an Account in SCP Trial landscape](#linkcode1)
2. [Create a Development Project](#linkcode2)
3. [Do some Data Modeling](#linkcode3)
4. [Work with OData](#linkcode4)
5. [Create a Simple UI](#linkcode5)
6. [Deploy the Application](#linkcode6)
 

### <a name="linkcode1"></a> Create an Account in SCP Trial landscape
In this first exercise, we will look at creating a trial account in SAP Cloud Platform.  We will use this account for most of the exercises in this lab so that everyone should be able to follow along.


##### Step 1a - Register for a new Trial Cloud Account
1.  If you do *not* already have an account in SCP, please visit the SAP Cloud Platform portal <https://cloudplatform.sap.com/try.html> and click on the "**Sign up for your free account**" link
2.  Fill in the information on the form, check the box that you have read the Terms & Conditions, then click **Submit** 
3. Once submitted, you will receive an email to the address you provided in the registration. Click the **Click to Activate your Account** button 
![](images/picture1.png)

OR

##### Step 1b - Log On to your Trial Account
1. If you already have a SCP Trial account, you can go to your saved link, or use SAP Cloud Platform portal <https://cloudplatform.sap.com/try.html> and click "**Log On**"

Next, you should see your SCP Trial Account Cockpit
![](images/picture2.png)

##### Step 2 -- Review the NEO Environment
1. From the cockpit, select the NEO environment by clicking on the NEO tile. ![](images/picture3.png)
2. This shows us all the elements of the NEO environment. If we click on **Services** on the left hand menu, we can see all the Services available in the Trial system. If we scroll down, we can see the SAP Wed IDE Full-Stack service which we would need for any development in our cloud landscape. And we see that it is already Enabled for use.
![](images/picture5.png)

##### Step 3 -- Review the Cloud Foundry Environment
1. Let's go back to our Cockpit Home by clicking from the breadcrumb trail at the top, or by clicking the Overview link on the left hand menu. 
2. On the Cloud Foundry tile, you will notice that you have options as to where your Cloud Foundry account can be hosted -- Microsoft Azure, Amazon Web Services (AWS) or Google Cloud. We will see that in a minute.
![](images/picture4.png)
*NOTE:  If you do not see the Cloud Foundry Trial tile, you may need to Log Out and make sure to click the activation link in the email, then Log On again.*

##### Step 4 -- Set Up the Cloud Foundry environment

1. Let's select the Cloud Foundry environment by clicking to open that tile. The first thing we need to do is select the **Region** we wish to use. Let's select the **Europe (Frankfurt)** for **AWS** because it has most of the services we will be needing for this course.
![](images/picture6.png)
2. The system will now create a subaccount for you called "trial" and may also create an Organization and Space. If not, we can do that manually.
![](images/picture7.png)
3. On the Subaccounts screen, click on the newly created **trial** subaccount, and we can click the button to **Enable Cloud Foundry**
![](images/picture8.png)
4. For our Organization name, we highly recommend that you use the same name as your subdomain, which is not the default.  Let's simplify it to be our P number followed by the word trial. Click **Create**.
![](images/picture9.png)
5. Now we see our Cloud Foundry Organization is created, with the same name as the subdomain of the subaccount.
![](images/picture10.png) 
6. The next thing we'll want to do is set up our Space within that CF Organization. To do that, we click on **Spaces** on the left hand menu, then click the button **New Space**
![](images/picture11.png) 
7. We will need to give it a name, let's call it **dev** and accept the default roles of Space Manager and Space Developer, then click **Save** 

![](images/picture12.png) 

##### Step 5 -- Enable Services for our 'dev' space
1. When the space is first created, we see that there is no quota assigned to it, and if we **open that space** by clicking on the tile, we can look at the Services available. Choose the **Services** link in the left hand menu, and select the **Service Marketplace** option to see the list of services available. There are not many by default.
![](images/picture13.png) 
2. To add more services, we need to go back to our Cloud Foundry subaccount. The easiest way to do this is to use the breadcrumb trail at the top, and click **Home**
![](images/picture14.png)
3. Here we see our list of subaccounts. If we click on the **Entitlements** link on the left hand menu, we are presented with the various services that are avaialble, and we can click the **Edit** button to modify the assignment for any given service.
![](images/picture15.png)
4. Let's use the **+** sign to assign all four units to the **Application Runtime** service.
![](images/picture16.png) 


##### Step 6 -- [Optional] Add other Service and create Instance
5. Optionally, you could use this Entitlements screen to activate other services, such as machine learning.
6. To **Save** these updates, scroll to the top of the page and click Save.
7. To see those services were added to our Space, you can go back to **SubAccounts > Spaces** to select our **dev** space, then use menu to see **Services > Service Marketplace** and see any added services, such as *ml-foundation-trial-beta* are now in the list.1. If we click to open the details for SAP Leonardo Machine Learning (ml-foundation-trial-beta) service tile, 
![](images/picture18.png)  
2. We can now create an instance of that service by clicking the **Instances** option on the left hand menu.
3. Click **New Instance** button, click Next because we already chose the service Plan, click Next because we don't have any parameters to set, click Next because we don't have an application to assign, and finally give your instance a name, such as **ml** for machine learning, then click Finish.  We will cover this more in the Machine Learning topic. 


### <a name="linkcode2"></a> Create a Project

In this section we will take a look at the WebIDE Full Stack development tool. This tool allows use to work with backend, the data model, the middleware and frontend development for our cloud applications. We will take advantage of both open source and SAP technologies. For this exercise, we will continue working in our SCP Trial account established earlier in this exercise.

##### Step 1 -  Open the WebIDE FullStack service
For this exercise, we will continue working in our SCP Trial account established earlier in this exercise. our first step is to configure the WebIDE FullStack service for our development space.  
1. To do this, we need to go back to our **Home** and this time choose to **open the Neo environment** tile.
![](images/picture3.png)
2. Next we can go to our Services from the left hand menu, and scroll down to find the **SAP Web IDE Full-Stack** service tile, and click to open.
![](images/picture5.png)
3.  Once the service details open, scroll down to find the **Go to Service** link under the "Take Action" section. Click to launch the service.

##### Step 2 -- Configure for Cloud Foundry
Once we open the Web IDE tool, we will need to do a small amount of configuration.  
1. First, let's **open the preferences section** by clicking the gear icon on the left hand menu, then choose the **Cloud Foundry** option under Workspace Preferences.
![](images/picture19.png)
2. Next we will need to give it an API Endpoint to our Cloud Foundry trial account. If you chose Europe (Frankfurt), then you can select the
*https://api.cf.eu10.hana.ondemand.com* option.
![](images/picture20.png). 
NOTE: to double check you are using the corrent endpoint, you can go to your SCP Cockpit, open your subaccount for Trial in the Cloud Foundry environment, and see the API Endpoint listed for the Organization you created earlier.
![](images/picture21.png)
3. You will need to Log On to the CF environment using the SAP Cloud Platform credentials (email/pw used to set up Trial Account).
![](images/picture22.png)
4. You can then see the Organization and Space you set up earlier should be auto-filled. Click **Save**
![](images/picture23.png)

**NOTE:  Videos mention that you need to install the Builder application.  This is no longer required.**

##### Step 3 -- Core Data Services Extensions

Next, we want to enable some additional tools for working with applications in the SAP Cloud Platform.

1. Let's check a few things...From the WebIDE tool, click on the **Core Data Services** link under *Preferences* menu. then click on the **Extensions** option in the *Workspace Prefences* group. 
2. Using the filter, you can search for "Tools" and then scroll down to find the **SAP Cloud Platform Business Application Develeopment Tools** tile. Make sure it is turned **ON**.
![](images/picture24.png)
3. Using the filter again, let's search for 'hana' to the find the **SAP HANA Database Developlment Tools** and click to turn it **ON** and click to **SAVE** that change. *NOTE: we will actually be using the Database Explorer tool, but it comes with the Database Development tool set, so we will just turn on that one.*
![](images/picture25.png)
4. Because we have made changes to our toolset, we will need to Refresh the Web IDE browser. Click **Refresh**.
![](images/picture26.png)
5. We now see we have additional items in our menu, including the options for Database Explorer.
![](images/picture27.png) 

##### Step 4 -- Create a Project using a Template
For our exercise, we will be creating an application with a HANA data model that uses an OData service to connect to our UI.  For that, we can take advantage of the Application Programming Model from SCP.

1. Go to Home in Web IDE, and select the **New Project from Template** tile under *Create Project*.
![](images/picture28.png) 
2. Scroll down and select the **SAP Cloud Platform Business Application** tile. 
![](images/picture29.png) 
3. *NOTE: If you do not see this tile, go up to the top and make sure that you have Cloud Foundry selected for your environment.*
![](images/picture30.png) 
4. After selecting the template, click **Next** and give the project a name. We'll use ***project1*** and click ***Next**
![](images/picture31.png) 
5. Next, we will need to confirm our Service model and our Database model. As a default, we will use the JAVA service and the SAP HANA database. We can use the drop down to choose the database version, or as we see later on we can set this in our code. *NOTE: for the trial version, 2.0.0.0 supports this exercise at this time.*  
6. We will also include the sample files in our project. Let's change the JAVA package to match our project, calling it ***project1***. Click **Next** and then **Finish** to create the project.
![](images/picture32.png) 
7. After a time, we will see that it has created a whole framework of files for us, including the subfolders for the JAVA service (srv) where we will create our OData service, and for the SAP HANA database (db) where we will do our data modeling.
![](images/picture33.png) 
8.  In fact, it has created a Multitarget Application as we see the mta.yaml file, which contains our modules for the Java service and our DB.
![](images/picture34.png) 
9. One more thing we need to check is that we are using the correct version of the SAP HANA database. To do this, we need to take a look at some **Hidden files**, by **clicking the Eye icon** from the tool bar
![](images/picture35.png)
10. We want to open the **.hdiconfig** file in the *>db>src>* folder.
11. To check our database version, we can edit the .hdiconfig to show the "plugin version" to be 2.0.0.0
![](images/picture36.png)
12. And we can click to **Save**, and then close the .hdiconfig file, and hide the hidden files again.
![](images/picture37.png)

Now we have created our project and the template has generated some cds files for us -- one for the db module, and one for the srv model. That allows us to do our entity modeling at the core service level using this sample code. That way, Web IDE Fullstack will actually generate the database and Odata service artifacts to make this process work, leaving us to concentrate on the entity level and not get caught up in the details of the artifacts themselves.


### <a name="linkcode3"></a> Data Modeling
In this next section of the exercise, we continue our look at full stack application development. For this exercise, we will take a look at how we can go about creating our data model for our sample application.

##### Step 1- Configure our Namespace
When we created our template in the earlier exercise, we accepted the sample set of code from the template. We updated to the correct version of the SAP HANA database, and now we need to update to reflect our actual model we are creating.

1. In the ***project1*** workspace, go to the database source (db>src) folder, and **open the 'data-model.cds'** file. 
2. On Row 1, we will want to change the namespace from the default to our *project1* and update the entity to be *Sales* with new parameters as key ID as Integer, *region* as String, and *amount* as Integer.
![](images/picture38.png). We won't save yet.
3. In the service folder, open the **cat-service.cds** file, and update the namespace to *project1* and change the service to use *entity Sales as projection on project1.Sales;*
![](images/picture39.png)
4.  Now we can save BOTH file updates by clicking the **Save All** icon.  ![](images/picture40.png) 
This tells Web IDE fullstack to create database specific and service specfic code for us. You should see the *"Build of 'project1' completed"* message in the upper right corner if all went well. ![](images/picture41.png)
5. For instance, we see a new folder under our db>src folder called "gen" that contains some elements. We see our project1.sales table with our 3 items for ID, region and amount in it.
![](images/picture42.png)
And we can see that there are now items populated in our srv>resources>edmx folder as well.
![](images/picture43.png)

##### Step 2 -- Build our Database Model
Now that we have generated the code we need, now we can build our model.

1. Right-Click on the ***db*** folder, choose **Build** and then **Build** again.
![](images/picture44.png)
2. After a few seconds, you should see that the Build completed successfully.
3. If we go back to our Cockpit, and look at our **Service Instances**, we see there is a new hdi container that has been set up for our *project1*.
![](images/picture45.png) 
4. To work with this new database, we can use the Database Explorer tool from the left hand menu in Web IDE. ![](images/picture46.png)
5. We will be prompted to add the database, click **Yes**, then **select** the new database for *project1* and click **OK**
![](images/picture47.png)
6. Now we see that it has opened our database in explorer and if we scroll down we find the 'project1.sales' Table we created earlier, and if we right-click on that item and choose **Open Data** we see the three items of ID, Region and Amount.![](images/picture48.png)
7. We can actually manually add some sample data here by clicking the **+** sign in the menu at the top of the table ![](images/picture49.png) and entering values in the fields, then clicking the **Save** icon. Go ahead and add a few rows of data, as seen here:
![](images/picture50.png)

In this section of the exercise we have seen how we can do some data modeling using the Web IDE tool to create our hdi container and create a Table. We then used the Database Explorer within Web IDE to populate some sample data into our table.

### <a name="linkcode4"></a> Work with OData
In this next section of the exercises, we continue our look at full stack application development. For this exercise, we will create an OData service to provide web-based access to our database table.

##### Step 1 - Run the Java module for the CatalogService
The setup required for the OData service has already been provided to us in our project. We updated the cat-service.cds file with our entity in the earlier section of this exercise. To review, you can open the project1/srv/cat-service.cds file from our project explorer.
![](images/picture51.png)

1. Now we need run that module to start the application. To do that, right-click on the /srv folder and choose **Run > Run as Java Application** 
2. Once it finishes running, we can find the URL to that application by opening up the Run Console window. 
![](images/picture52.png)
3. If we open that URL in a new window, it will show our application endpoint. If we click on that link to open it, we see the actual Odata service.
![](images/picture53.png)

##### Step 2 - Work with the OData service in json format

From here, we can append the URL to see various aspects of our OData service.

**/$metadata** to see the metadata for the service
![](images/picture54.png)

**/Sales/$count** to see the count of rows in our Sales table is 4 indicating the 4 rows of data we entered manually through Database Explorer earlier in this exercise.

**/Sales** will display all the data in that table (be careful if you have a lot of data in your table. We should only have 4 rows at this point.)  We see our entries for EMEA, NA, etc.
![](images/picture55.png)

**/Sales?$format=json** will switch the format to JSON which is easier to read. NOTE: you may need to install the 'jsonview' extension for your browser.
![](images/picture56.png)

We can now do some filtering or ordering of this data as well by appending more parameters to our URL.

**/Sales?$format=json&$top=2** would give us the top two items.

**/Sales?$format=json&$top=2&$orderby=amount** would give us the top 2 items in ascending order by default.
**/Sales?$format=json&$top=2&$orderby=amount desc** would give us the top 2 in descending order.

**/Sales?$format=json&$filter=region eq 'EMEA'** would just give us the results for EMEA region.

So you can see we have a full OData service available to us but we didnt have to write any code.  That was all done by the Application Programming Model in Web IDE. All we needed to do was to establish our entity of Sales and provide the fields for the table.



### <a name="linkcode5"></a> Create the UI
Now that we have our application and data model, the next step will be to build a User Interface.

##### Step 1 - Learn more about SAPUI5
To create a user interface for our database model and OData service, there are several frameworks available.  For most applications the choice would be html.  We will be using a modified version of HTML5 specific to SAP called SAPUI5.  To learn more about SAPUI5, you can visit <https://sapui5.hana.ondemand.com/>

##### Step 2 - Create our UI in our development project
We are going to create our UI through the Web IDE tool, but again we won't have to write any code. 

1. To start, we want to create a new html5 module for our project by right-clicking on the *project1* module and choosing **New>HTML5 Module** from the menu.
![](images/picture57.png)
2. Next we are shown a collection of pre-built templates to choose for our project. We will **Select CRUD Master-Detail Module** and click **Next**
![](images/picture58.png)
3. We can call our module ***ui*** and give it the title ***Sales Data*** and connect it to our namespace ***project1** then click **Next**
![](images/picture59.png)
4. Now we should see the services available in our current projects, and we can select the catalog service for our java service. **Select CatalogService** and click **Next**
![](images/picture60.png)
*Note: a current bug may show the catalog service multiple times. Just select the top item in the list*  
5. For the customization, we need to add some binding. If you click to enlarge the picture on the right, you can see the potential results with the various components listed. This can help you to choose the appropriate fields to select for the design. We will choose the following to start:

Field | Value
---- | -----
Object Collection | Sales
Object Collection ID | ID
Object Title | region
Object Numeric Value | amount 

6. After selecting these from the drop down menus for each item, click **Next** and then click **Finish**
7. Web IDE will then generate all the necesary code for our HTML5 UI in the new **/ui** folder of our project.
8. In fact, we can go ahead an Run that now by using the menu bar and selecting **Run > Run as Web Application**

![](images/picture61.png)

*Note: if you do not see the Run as Web Application option at first, try refreshing the Web IDE browswer*
9. We will need to designate where we want to run our application, so we will choose the **flp-sandbox.html** for the Fiori Launchpad Sandbox.
![](images/picture62.png)
10. You will need to **Log On** using your SAP Cloud Platform credentials
![](images/picture63.png)
11. You may receive a message that you need to disable your Pop-Up blocker in your browser to see the pop-up windows for the Fiori Launchpad. Go ahead and Allow pop-ups.
12. Next you should see the Fiori Launchpad with a tile indicating our Sales Data application.
![](images/picture64.png)
13. We can click to **open the tile** and we see our Master-Detail layout (from the template we chose) populated by the data (we entered in database explorer).
![](images/picture65.png)

##### Step 3 - Edit the UI
A couple of things to note here... 

1. The UI is responsive, so if we opened that same application on a mobile device, it would automatically re-format the master-detail to be a main page and subpage, rather than side-by-side values in the web browser.
2. If you click the **Edit** button in the bottom right of the UI, you can actually update values in the table.
3. If you click the **+** sign in the lower left of the UI, you can add additonal records to the table.

This is all possible as we chose the template that supports these CRUD (Create Read Update Delete) operations.

##### Step 4 - Customize the UI

To modify the look of this shell application we created from template, we can go back to the Web IDE and open the ***/ui*** folder. Here we find the folders that support the Model-Viewer-Controller approach of UI5. 
 
1. If we want to change the display of values, we would open the ***/view*** folder to modify one of the views.
![](images/picture66.png)

[Optional] For example, we could modify the Master.view.xml code to remove the currency formatting to eliminate the decimals in our UI.
![](images/picture68.png)

2. If we wanted to modify the functionality, we would open the ***/controller*** folder and modify the JavaScript code.
![](images/picture67.png)
3. If we want to modify the layout of our views, we can do that as well. For that, we can select our Master.view.xml view again and right-click to **Open in Layout Editor** from context menu.
![](images/picture69.png)
4. Here we have a Drag and Drop editor for our Master page of our UI, with all the various component controls available.
![](images/picture70.png)

You can modify and customize the UI through the Code Editor or through the Layout Editor, or any combination of the two -- giving you a very powerful toolset to create and customize your UI.

Finally, let's **Run** the application again using the Run button from the top menu to see any changes we may have made.
![](images/picture71.png)


### <a name="linkcode6"></a> Deploy our Application

As the last step of this introduction to developing in SAP Cloud Platform, we will want to deploy our application.

Up until now, we have seen our application automatically deployed to our Cloud Foundry space while we have been working in the WebIDE full stack. In the SCP Cockpit for our trial subaccount / dev space we can find our HANA Service Instance of our hdi container for our *'project1'* project and a couple of Applications listed (one for our Web IDE builder and one for our srv java service). 

Next we will want to actually take this project and deploy it.

##### Step 1 - Review the mta.yaml file

The mta.yaml file is very important. Here is where we find all the various aspects of our project (db, srv, ui). 

If you **open the mta.yaml** file, you can customize this by using the MTA Editor or the Code Editor found on the bottom part of the screen. We won't do that here, but take a look through the various settings controlled by the mta.yaml file. Once reviewed, go ahead and **close the mta.yaml** file.
![](images/picture72.png)

##### Step 2 - Build the project

To deploy the project, we want to build all the various components with all of our changes. 

1. To do this, simply select the ***project1*** project and right-click to select **Build > Build** from the context menu to build the whole project at once.
*NOTE: This may take a few minutes.*
2. Once complete, you should see the "Build of project1 was successful" message, and an archive of your project will be created.
![](images/picture73.png)
3. In fact, we now see a */mta_archives* folder in our project, and it contains the archive of our version 0.0.1 of our project.
![](images/picture74.png)
*Note: this structure differs slightly from than that shown in the video*
4. We have a couple of options to deploy this file.  We could download the .mtar file and deploy it into a Cloud Foundry space using the Command Line tool, or we can use Web IDE to deploy it directly from here.
5. Right-click on the .mtar file and choose **Deploy > Deploy to SAP Cloud Platform**
![](images/picture75.png)
6. We will need to provide our Cloud Foundry API Endpoint, our Organization and Space. For our simple example, we only have one CF org and space so once we enter the API endpoint, we will accept the default values. However, if you had more accounts available, you could be deploying from a NEO environment of Web IDE to any Cloud Foundry org and space in any supported region.
![](images/picture76.png)
Note: Remember the Cloud Foundry API Endpoint can be found in the SCP Cockpit on the Cloud Foundry sub-account details.
7. After a few minutes, you should receive the "deployed successfully" messages to indicate it has created the db service, the srv java service and the ui application.
![](images/picture77.png)

##### Step 3 -- Review the Application Components Created
Now that we have successfully deployed the application, let's go back to the Cockpit and take a look at what has happened.

1. If we open up our *'dev'* space,we can see under **Applications**, we see we now have applications for our *'project1-db'*, our *'project1-srv'* and our *'ui'*.
![](images/picture78.png)
2. If we look at our **Service Instances**, we should see our new hdi container *'project1-hdi-container'* for the project1, as well as a user authorization *'uaa_project1'* instance.
3. We can also notice with the *Referencing Applications* column here that all the linking and binding between applications has already been done for us.
![](images/picture79.png)

##### Step 4 -- Run the Application 
Now to run our Application, we can just click on the URL for the UI.

1. Go back to **Applications** and click on the **ui** application to open the details.
![](images/picture80.png)
2. On the Details page, we can **Click the URL** for our application to run it.
![](images/picture81.png)
3. We will need to **Log On** with our SCP credentials to get to our Fiori sandbox.
4. We see our Sales Data tile on the Fiori Launchpad again, but if we open it this time, we see the application but no data.  This is expected since the data we entered earlier was for the hdi container we were using during development. This is a new hdi container we have created during deployment.
![](images/picture82.png)
5. Once again, because this is a CRUD application, we could use the **+** sign on the lower left and manually add some data again, and click to **Save**.
![](images/picture83.png)

##### Step 5 -- Run the OData Service
We could also go directly to the OData service to review our application components.

1. Go back to the Cockpit and let's look at the service application. We can either open our *'dev'* space and go to **Applications** again and select it, or we can use the shortcut and click on the dropdown arrow *'v'* in the upper right portion of the breadcrumb trail to **Switch to Another Application** and select the **project1-srv** service application.
![](images/picture84.png)
2. On the Details page for the service application, we find the URL for this service. 
![](images/picture85.png)
4. If we **Click on the URL** we should be able to connect to the Odata service endpoint through our browser.
![](images/picture86.png)
5. Then **Click to open the OData service** and if you added data into this new hdi container, we can modify the URL by adding **/Sales/?$format=json** to see our Sales data in json format as we did before.
![](images/picture87.png)

Congratulations! You have completed this Introduction to Developing Applications in SAP Cloud Platform.
  

## Summary
In this series, we looked at developing an application using the Web IDE fullstack tool and took advantage of the Application Programming Model to auto-generate the code behind the components of our application.

* Created SAP Cloud Platform Trial account
* Created a Development Project in Web IDE fullstack
* Created a Data Model in a HANA database
* Created an OData service to connect to our database
* Created a UI for the application
* Deployed our application to a Fiori Launchpad sandbox
