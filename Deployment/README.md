# Prerequisites

* Power Platform environment with Dataverse enabled and System Administrator access
* Copilot Studio license
* End users having Dataverse access
* ServiceNow Instance (see below)
* Access to create a SharePoint site
* The [Teams Approvals](https://learn.microsoft.com/en-us/microsoftteams/approval-admin) app available for users
* Environment Variables solution installed in your Dataverse environment

# Deployment Guide

This document will comprise of step by step instructions on how to deploy this solution. At a very high level, it has three major setups involved:

1. ServiceNow Setup
2. SharePoint Site setup
3. Copilot Agent Setup

# Step 1: ServiceNow Setup

This accelerator features integration with ServiceNow, which is used as a source of knowledge, as well as a source of information on employees and office locations.

To enable the functionality of this accelerator, you will need a ServiceNow instance, and will need Administrator credentials for that instance. This accelerator has been tested with the **Yokohama** release of ServiceNow.

## Step 1.1: Ensure your ServiceNow usage compliance
Ensure that your intended usage of this accelerator is in compliance with your ServiceNow instance and license terms of use.

## Step 1.2: Enable the Knowledge API Plugin
The functionality in this accelerator that enables searching and summarizing of knowledge from the ServiceNow knowledgebase requires the **Knowledge API** plugin to be enabled.
 * Follow the instructions found [here](https://www.servicenow.com/docs/bundle/yokohama-platform-administration/page/administer/plugins/task/activate-plugin-pdi.html) to enable the **Knowledge API** plugin in your instance

# Step 2: SharePoint Setup

This will be a manual step as the Power Platform solution does not include a SharePoint site. This site is needed to store the relocation proposals which are created.

## Step 2.1: Create SharePoint site

1. Go to (https://(your tenant).sharepoint.com/) and click **'Create site'.**
2. Select **Team Site.**
3. Select **Standard Team** template.
4. Enter name as desired.
5. **Save the URL** of this SharePoint site which will be used later to update environment variables. This will be in the format of: https://(your tenant).sharepoint.com/sites/(site name).

## Step 2.2: Create SharePoint Document Library

1. Create a new [SharePoint document library](https://support.microsoft.com/en-us/office/create-a-document-library-in-sharepoint-306728fe-0325-4b28-b60d-f902e1d75939#ID0EBF=Modern) and name it as desired, for example, "RelocationProposals". This library will be used to store the template for Relocation Proposals, as well as populated proposals sent to employees.
2. Create two folders for **'Output' and 'Templates'.**
3. **Save the extension** of the library name to be later used to update an environment variable. This will be in the format of: **/(library name)/Output**
4. From the **Data folder in the repo**, download the **Template-Proposal.docx** template (or an alternate template you plan to use) and upload this in the **'Templates' folder in the SharePoint library created in Step 2.2.2**.


# Step 3: Copilot Agent Setup

## Step 3.1 Import the Zip solution

1. The zip file in the solutions folder contains all the components needed for provisioning the AI agent.
2. Import the zip file in the [PowerApps Maker Portal](https://make.powerapps.com) in the power platform environment provisioned earlier.
3. During import, click '**sign in'** for any connections that prompt to do so. **You will need to provide credentials for your ServiceNow instance to establish this connection. The credentials you provide must have sufficient privileges to read, create, and update Users, Knowledge Bases, Knowledge Articles, and Locations**
 * You will need to determine the optimal authentication method, based on your ServiceNow configuration and security strategy. If you elect to use Basic authentication while configuring your connection, you would need to provide:
    * **Your instance**: this would be the **prefix** of the URL of your instance (**<YourInstance>**.service-now.com)
    * **Your username**: the ServiceNow username of a user with sufficient privileges, as described above
    * **Your password**: the password associated with the username you provided
4. During import, you will be asked to populate three Environment variables. Populate them like so:
 * **ServiceNow Instance ID** should be populated with the unique identifier for your instance, which is also the domain name "prefix" of your instance URL (https://<This is your Instance ID>.service-now.com/)
 * **ServiceNow FAQ KB ID** and **ServiceNow Benefits KB ID** will be updated later on. **Leave the placeholder values as-is for solution import**.
5. Warnings may occur due to connector configurations that will be updated in subsequent steps. After importing has completed, click **Publish all customizations**, and wait for publishing to complete.

## Step 3.2 Update Power Automate flows

There are six Power Automate flows in this solution. Some of those will need to be updated as covered below. To see a list of all flows, navigate to **'Flows**' section in the [PowerApps Maker Portal](https://make.powerapps.com).

### Step 3.2.1 Initiate Relocation Request flow

1. Open the **Initiate Relocation Request** flow in **Edit mode**, then expand the Request Approved condition node, and click on the **'Populate a Microsoft Word Proposal'** action.
2. Update the **Location** value to the SharePoint site created in **step 2.1.**, the **Document Library** value set to the library you created in step **2.2**, and the **File** value set to the template file you retrieved and placed in the library. 
3. Click on the **Create file** action, and ensure the **Site Address** and **Folder Path** parameters are selected as your SharePoint site, and your Output directory you created earlier.
4. Click on the **Get file properties** action, and ensure the **Site Address** and **Library Name** parameters are selected as your SharePoint site, and your Document Library you created earlier.
5. **Save** the flow.

### Step 3.2.2 Ensure flows are turned on

Ensure all included flows are turned on. When viewing the list of flows included with the solution, the **Status** column will indicate whether each is On or Off. By selecting any flow, you will be able to turn it on by selecting **Turn On** in the top menu.

### Step 3.2.3 Automated population of ServiceNow data

**Note** Two options are available for populating ServiceNow Data
 * Option 1: Running a Power Automate flow to automate most data Population, as described here
 * Option 2: Manually populating each data element, as described later

Both are included such that users can understand the steps the Power Automate flow will take, and also to take any corrective action in case of issues or failures during the Power Automate data population.

By electing to automate data population with the Power Automate flow, the following changes will be made in your ServiceNow instance:
 * Two new **Knowledge Bases** will be created, named **FAQ** and **Benefits**
 * Five **Knowledge Articles** will be added to the Benefits knowledge base, and one article will be added to the FAQ knowledge base
 * Five **Locations** will be added, one for each of the fictional Contoso offices
 * If a **User** exists in ServiceNow with the same email address as the Entra ID that you are using to run this flow, that user will be updated to have Contoso-Redmond as their location
 * If a **User** does NOT exist in ServiceNow with the same email address as the Entra ID that you are using to run this flow, a new ServiceNow user will be created with the same email address, in the Contoso-Redmond location

 In addition, the Environment variables for **ServiceNow FAQ KB ID** and **ServiceNow Benefits KB ID** will be updated in Dataverse, based on the newly created knowledge bases.

**To automatically populate data in ServiceNow:**
1. Open the flow named **Set up ServiceNow Data**
2. Click the **Run** button
3. Monitor the flow to ensure it completes properly

 * Log into your ServiceNow instance, and ensure that all articles are published, by navigating to **All**, and filtering on **knowledge bases**, to select **Knowledge > Administration> Knowledge Bases**, then successively opening each of the articles in the FAQ and Benefits knowledge bases, and clicking **Publish**.
 * In the Power Automate Maker portal, navigate to the Environment Variables of your imported solution, and ensure that **ServiceNow Benefits KB ID** and **ServiceNow FAQ KB ID** have been updated with Sys IDs from ServiceNow, by clicking on each variable's name, to view the **Current Value**. If not, see section **4.5** for instructions on manually updating these values.

### Step 3.2.4 Managing authentication for actions and flows (optional)

You will want to ensure that you configure any Copilot Studio actions, and any Connections used in Power Automate flows, to use the authentication that is appropriate for your organization and scenario.

Depending on your desired security model, you may wish to select **User authentication** for actions rather than **Agent author authentication**. For Power Automate flows, you may wish to configure connections to use the credentials of run-only users, or with a specific connection that you create.

See these resources for more details on setting up authentication:

* [Configure user authentication for actions](https://learn.microsoft.com/en-us/microsoft-copilot-studio/configure-enduser-authentication)
* [Manage owners and users in your flows with Power Automate](https://learn.microsoft.com/en-us/sharepoint/dev/business-apps/power-automate/guidance/manage-list-flows)

## Step 3.3 Security roles

Please note that this solution leverages a custom Dataverse table called **Relocations** which stores metadata related to the status of the employee relocation. Creation of a security role to manage User and Relocation table access for end users is recommended, based on organizational best practices and needs.

## Step 3.4 Publish Copilot Agent to Microsoft Teams

1. Go to [Copilot Studio Portal](https://copilotstudio.microsoft.com).
2. Please Publish your Copilot Agent by clicking '**Publish**'. This will make the copilot agent ready to be used. If there is an authentication warning, that is expected per the use case.
3. Go to **Channels > Teams + Microsoft 365 > Add Channel.**
4. Please Publish your Copilot Agent by clicking '**Publish**'. This will make the copilot agent ready to be used in Teams.
5. Go to **Channels > Teams + Microsoft 365 >** **Availability Options > Copy Link**
6. Paste the link in a new window to access the agent in MS Teams.

# Step 4: ServiceNow Manual Data Population **(OPTIONAL)**

**Important Note** Populating your ServiceNow data manually is only needed if running the Power Automate flow described in **Step 3.2.3** failed, or you wish to manage the data manually.

## Step 4.1: Set up Knowledge Bases
1. In your ServiceNow environment, navigate to **All > Knowledge > Administration > Knowledge Bases**
  * Note that your quickest way to navigate may be to click **All** in the top menu, then enter **knowledge bases** as a filter
2. Use the New button to iteratively add two new knowledge bases. The names for the knowledge bases should be:
 * FAQ
 * Benefits

 As you create these knowledge base records, ensure you capture the **sys_id** value for each, as they will be needed later in the setup process. To retrieve the values, you can either:
  * retrieve the unique ID from the browser URL when viewing the knowledge base record in ServiceNow, or;
  * use the **REST API Explorer** (navigate to **All > System Web Services > REST > REST API Explorer**), and issue a **Retrieve records from table** request on the Knowledge Bases table, specifying the **sysparm_limit** value sufficiently high to view your knowledge bases in the results. The **sys_id** value for each of the knowledge bases should be retrievable from the response content. 

## Step 4.2: Set up Knowledge Articles
The HTML content for six knowledge articles that are used within this accelerator can be found in the [Data](./Data) directory. 

For each of these six articles, you may follow the documentation instructions found [here](https://www.servicenow.com/docs/bundle/yokohama-servicenow-platform/page/product/knowledge-management/task/create-knowledge-article.html) to create a new article for each.

The names for each file in the Data directory correspond to a recommended **Short Description** for the corresponding article that you add.

When specifying the Knowledge Base that each article should reside in, you should choose:
 * **FAQ** should be the knowledge base that you specify for the [Process Overview](./Data/An-overview-of-the-process-of-relocating-to-a-new-office-location.html) article
 * **Benefits** should be the knowledge base that you specify for the five **Benefits Summary** articles

Ensure that all articles are published.

## Step 4.3: Set up locations

1. In your ServiceNow environment, navigate to **All > Organization > Locations**
2. Use the New button to iteratively add five new locations. The names for the locations should be:
 * Contoso-NewYork
 * Contoso-Redmond
 * Contoso-Guangzhou
 * Contoso-Helsinki
 * Contoso-Dublin

Note that you may use different locations or naming conventions, but for optimal accelerator function, the list of location names added should correspond with a Closed-list Entity within the Copilot Studio agent (see later step)

## Step 4.4: Set up system user
In this accelerator, employee data is retrieved from several systems, with the unique attribute that links them together being the **Microsoft Entra ID email address** of the user.

Employees will access the agent via Microsoft Teams. The agent makes use of **Microsoft authentication** in the **Security** settings. This gives the agent access to the user's Entra ID via the **System.User.PrincipalName** variable.

This same identity is used to associate Relocation records in Dataverse to the same System User (via the Employee attribute, a Lookup on the User table).

And the Entra ID email address is assumed to be the same email address that users will have associated with their User record in ServiceNow.

As a result, for any Microsoft Entra ID users that you intend to test this accelerator with:
* ensure there is a corresponding ServiceNow User (**sys_user** table) record with the same email address used for the **email** attribute
* ensure that each of these users has the **Location** attribute set to one of the Locations created in the previous step

## Step 4.5: Update Environment Variables for Knowledge Bases

1. Navigate to the imported solution in the Power Platform Maker Portal
2. Select **Environment Variables** from within the solution tree
 * Click on **ServiceNow FAQ KB ID** and populate the **Current Value** with the sys_id value you retrieved for the **FAQ** knowledge base in step **4.1**, then Save.
 * Click on **ServiceNow Benefits KB ID** and populate the **Current Value** with the sys_id value you retrieved for the **Benefits** knowledge base in step **4.1**.

