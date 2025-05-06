# Agent for HR Service

This solution streamlines HR service workflows with an AI-powered assistant that delivers instant answers, automates record updates, and provides intelligent support, saving time and elevating the employee experience.

<br/>

<div align="center">
  
[**SOLUTION OVERVIEW**](#solution-overview)  \| [**QUICK DEPLOY**](#quick-deploy)  \| [**BUSINESS USE CASE**](#business-use-case)  \| [**SUPPORTING DOCUMENTATION**](#supporting-documentation)

</div>
<br/>

<h2><img src="./Deployment/Images/solution-overview.png" width="48" />
Solution overview
</h2>

The Agent for HR Service is designed to assist employees with various HR-related tasks. It provides instant answers, seamless record updates, and automated support, improving efficiency, compliance, and transparency by streamlining HR service workflows. 

This accelerator leverages Copilot Studio, Power Platform, and Microsoft Teams. It also interfaces with Dataverse and integrates the 3rd party business workflow management program, ServiceNow. 

The Agent enables employees to propose a relocation, compare benefits and compensation in different cities, and track the approval process. Upon completion of the relocation process, the company's records are updated and an automation is triggered wherein the Agent for HR Service will reach out for the employee's feedback, all using natural language inside of Microsoft Teams. 

**Note:** This accelerator is not intended to be a production ready solution. The components can be extended through customization and configuration as desired to create a production ready solution. All components packaged have been done through an unmanaged solution, which allows users to be able to customize and extend the components post-deployment. 

### Solution architecture

![Architecture](./Deployment/Images/architecture.png)

### How to customize

This solution is designed to be easily customizable. All configuration and customizations to this solution will be done in Power Platform, Copilot Studio, and with content and data stored in 3rd party platform ServiceNow.

**Additional opportunities for extension**

There are a variety of opportunities to extend the functionality of this accelerator. Some of these include:

 * Augmenting the sequence of steps involved in the relocation process, to match organizational practices
 * Catering for additional HR-related processes beyond relocations
 * Adapting or augmenting approval logic to match organizational practices
 * Integrating with additional systems of record for HR-related data and content
 * Integrating eSignature capabilities for document acceptance
    * An example of eSignature integration can be seen in the [Agent for Contract Processing Solution Accelerator](https://github.com/microsoft/Agent-for-Contract-Processing-Solution-Accelerator)

### Additional resources

This accelerator focuses on harnessing the following key capabilities:

* [Generative AI in Copilot Studio](https://learn.microsoft.com/en-us/microsoft-copilot-studio/advanced-generative-actions)
* [Adaptive Cards in Copilot Studio](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/adaptive-cards-overview)
* [Publishing Copilot agent in Microsoft Teams](https://learn.microsoft.com/en-us/microsoft-copilot-studio/publication-add-bot-to-microsoft-teams)
* [Capturing digital approvals using Approvals in Microsoft Teams](https://learn.microsoft.com/en-us/power-automate/teams/native-approvals-in-teams)
* [Update tables in Dataverse](https://learn.microsoft.com/en-us/training/modules/get-started-with-powerapps-common-data-service/)
* [Using ServiceNow for cloud data integration](https://learn.microsoft.com/en-us/connectors/service-now/)

Additional details on how these capabilities are leveraged in this accelerator can be found here:

* [Autonomous Agent Capabilities](./Deployment/Differentiators/DIFFERENTIATORS.md#autonomous)
* [Proactive Engagement and Response Routing](./Deployment/Differentiators/DIFFERENTIATORS.md#proactive_engagement)
* [Integration to HR System (ServiceNow)](./Deployment/Differentiators/DIFFERENTIATORS.md#hr_integration)
* [Approval Tracking](./Deployment/Differentiators/DIFFERENTIATORS.md#approvals)
* [Document Manipulation](./Deployment/Differentiators/DIFFERENTIATORS.md#document_manipulation)
* [Dynamically-Generated Adaptive Cards in Topics](./Deployment/Differentiators/DIFFERENTIATORS.md#adaptive_cards)
* [Use of Custom Entities and Slot Filling](./Deployment/Differentiators/DIFFERENTIATORS.md#slot_filling)

## Key features
<details open>
  <summary>Click to learn more about the key features this solution enables</summary>

  - **Find & summarize policy info** <br/>
  Locate existing HR policies, extract and summarize relevant details, empowering employees make informed decisions.
    
  - **Extend and integrate employee data** <br/>
  Seamlessly integrate with third-party platforms such as ServiceNow to access and update information such as employee data and knowledge base, where it is stored.
  
  - **Enable autonomous HR support** <br/>
  Automate HR processes and approvals, to reduce manual effort and improve efficiency.
  
  - **Generate HR documents** <br/>
  Dynamically generate structured HR documents from related data sources and templates, ensuring compliance and consistency.
  
  - **Capture employee satisfaction** <br/>
  Features description goes here.​

  - **Features name** <br/>
  Leverage employee feedback over time, generating insights to drive proactive HR improvements.
     
</details>

<br /><br />
<h2><img src="./Deployment/Images/quick-deploy.png" width="48" />
Quick deploy
</h2>

Please click this [**Link to Deployment Guide**](Deployment/README.md) for instructions on how to deploy and set up the solution accelerator.

[**Usage Guidance**](Deployment/Data/USAGE_GUIDANCE.md) has been provided to assist you in executing the steps required to see the included capabilities of this accelerator in action.

<br/>

### Prerequisites and Costs - Do not have content

To deploy this solution accelerator, ensure you have access to the following

- [Microsoft Power Platform license](https://learn.microsoft.com/en-us/power-platform/admin/pricing-billing-skus) with Dataverse enabled and System Administrator access.
- [Copilot Studio license](https://learn.microsoft.com/en-us/microsoft-copilot-studio/billing-licensing).
- End users having Dataverse access.
- [ServiceNow license](https://www.servicenow.com/products/hr-service-delivery.html).
- Access to create a SharePoint site through appropriate [Microsoft 365 license](https://www.microsoft.com/en-us/Licensing/product-licensing/microsoft-365) .
- The [Teams Approvals app](https://learn.microsoft.com/en-us/microsoftteams/approval-admin) available for users
- Environment Variables solution installed in your Dataverse environment


<br/>

| Product | Description | Cost |
|---|---|---|
| [Microsoft Power platform](https://learn.microsoft.com/en-us/power-platform/) | Decription of how the product is used | [Pricing](https://www.microsoft.com/en-us/power-platform/pricing/) |
| [Microsoft copilot studio](https://learn.microsoft.com/en-us/microsoft-copilot-studio/) | Microsoft Copilot Studio is a graphical, low-code tool designed for building AI-driven agents and agent flows. | [Pricing](https://learn.microsoft.com/en-us/microsoft-copilot-studio/billing-licensing) |
| [ServiceNow](https://www.servicenow.com/products/hr-service-delivery.html) | ServiceNow's HR Service Delivery (HRSD) solution is designed to streamline and automate HR processes, enhancing the overall employee experience.  | [Pricing](https://www.servicenow.com/products/hr-service-delivery.html) |
| [Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/products-apps-services) | Microsoft 365 is a cloud-powered productivity platform that includes a suite of applications and services designed to enhance productivity and collaboration. | [Pricing](https://www.microsoft.com/en-us/microsoft-365/buy/compare-all-microsoft-365-products) |

<br/>

<br /><br />
<h2><img src="./Deployment/Images/business-scenario.png" width="48" />
Business Use Case
</h2>

Below is a sample landing page of the solution accelerator after it is deployed, set up, and ready to be used:

![Key Features](./Deployment/Images/landingpage.png)

Pier, an employee of Contoso, is looking to relocate to a new city. Pier initiates contact with the HR agent to understand the relocation process and its potential impacts. The agent provides information on relocation compensation and helps Pier assess the financial implications. The agent offers to initialize a relocation request. Pier submits a relocation request through the agent. The HR team reviews and approves the request. Pier receives a notification in the Teams channel about the approval. The agent generates necessary documents for the relocation process. After the relocation process is complete, Pier receives an autonomous satisfaction survey to provide feedback on the interaction with the HR agent and the overall process

**Highlights**
- Knowledge Retrieval: The agent retrieves relevant information and documents from various sources, including SharePoint and ServiceNow
- Action Execution: The agent performs actions such as initiating requests, generating documents, and sending notifications
- System Integration: The agent integrates with existing HR systems like Workday, SAP SuccessFactors, and ServiceNow to provide a seamless experience. The agent can be customized to handle various HR scenarios, such as onboarding, offboarding, talent development, and performance management 

Overall, the HR Agent helps Pier by providing instant answers, automating routine tasks, and ensuring seamless integration with existing HR systems, thereby enhancing efficiency and the overall employee experience.

### Business value
<details>
  <summary>Click to learn more about what value this solution provides</summary>

  - **Faster issue resolution** <br/>
  Higher first-contact resolution rates speed up problem solving and reduce repeated inquiries. This enhances employee trust in HR service systems and improves their overall support experience.
  
  - **Improved employee satisfaction** <br/>
  Employees feel more supported and confident in the HR system’s clear responses and helpful summaries, resulting in higher engagement, greater trust and positive feedback.
  
  - **Increased HR efficiency** <br/>
  HR teams spend less time on repetitive issues and escalations, freeing up time for strategic, high-impact work, streamlining operations and boosting the overall effectiveness of the self-service system. 
  
  - **Reduced operational costs** <br/>
  Fewer support tickets, manual workloads, and smarter resource allocation lead to direct cost savings, helping the business operate more efficiently and cut unnecessary expenses.
       
</details>

<br /><br />

<h2><img src="./Deployment/Images/readme/supporting-documentation.png" width="48" />
Supporting documentation
</h2>

1. [Microsoft Power Platform](https://learn.microsoft.com/en-us/power-platform/)
2. [Microsoft Copilot Studio](https://learn.microsoft.com/en-us/microsoft-copilot-studio/)

### Security guidelines

You may want to ensure that you configure any Copilot Studio actions, and any Connections used in Power automate flows, to use the authentication that is appropriate for your organization and scenario.

Depending on your desired security model, you may wish to select user authentication for actions rather than agent author authentication. For power automate flows, you may wish to configure connections to use the credentials of run-only users, or with a specific connection that you create.

Please note that this solution leverages a custom Dataverse table called 'Relocations' which stores metadata related to the status of employees. Creation of a security role to manage users and relocation table access for end users is recommended based on organizational best practices and needs.

Also note that this solution leverages a SharePoint site and document library for the storage of unsigned, signed, and template NDA Agreements. Ensure that the security settings for your site and library are managed in accordance with your organizational best practices and needs. See [Managing SharePoint Online Security](https://learn.microsoft.com/en-us/microsoft-365/community/sharepoint-security-a-team-effort) for more details.

See these resources for more details on setting up authentication:

* [Configure user authentication for actions](https://learn.microsoft.com/en-us/microsoft-copilot-studio/configure-enduser-authentication)
* [Manage owners and users in your flows with Power automate](https://learn.microsoft.com/en-us/sharepoint/dev/business-apps/power-automate/guidance/manage-list-flows)
* [Managing SharePoint Online Security](https://learn.microsoft.com/en-us/microsoft-365/community/sharepoint-security-a-team-effort)

<br/>

### Frequently asked questions

{🟨TODO: Remove this section if you don't have FAQs}

[Click here](./FAQs.md) to learn more about common questions about this solution.

<br/>

### Cross references
Check out similar solution accelerators
 
| Solution Accelerator | Description |
|---|---|
| [Agent for Contact processing](https://github.com/microsoft/Agent-for-Contract-Processing-Solution-Accelerator) | The Agent for Contract Processing helps employees quickly create, find, manage and share contracts, saving time and resources by automating contract processing workflows. |
| [Agent for RFP response](https://github.com/microsoft/Conversation-Knowledge-Mining-Solution-Accelerator) | The Agent for RFP response processes RFP documents and leverages its knowledge base to create a draft proposal posted autonomously in Microsoft Teams. |


<br/>   


## Provide feedback

Have questions, find a bug, or want to request a feature? [Submit a new issue](https://github.com/microsoft/agent-for-hr-service-solution-accelerator/issues/new/choose) on this repo and we'll connect.

<br/>

## Responsible AI Transparency FAQ
Please refer to [Transparency FAQ](./TRANSPARENCY_FAQ.md) for responsible AI transparency details of this solution accelerator.

<br/>

# Disclaimers

To the extent that the Software includes components or code used in or derived from Microsoft products or services, including without limitation Microsoft Azure Services (collectively, “Microsoft Products and Services”), you must also comply with the Product Terms applicable to such Microsoft Products and Services. You acknowledge and agree that the license governing the Software does not grant you a license or other right to use Microsoft Products and Services. Nothing in the license or this ReadMe file will serve to supersede, amend, terminate or modify any terms in the Product Terms for any Microsoft Products and Services. 

You must also comply with all domestic and international export laws and regulations that apply to the Software, which include restrictions on destinations, end users, and end use. For further information on export restrictions, visit https://aka.ms/exporting. 

You acknowledge that the Software and Microsoft Products and Services (1) are not designed, intended or made available as a medical device(s), and (2) are not designed or intended to be a substitute for professional medical advice, diagnosis, treatment, or judgment and should not be used to replace or as a substitute for professional medical advice, diagnosis, treatment, or judgment. Customer is solely responsible for displaying and/or obtaining appropriate consents, warnings, disclaimers, and acknowledgements to end users of Customer’s implementation of the Online Services. 

You acknowledge the Software is not subject to SOC 1 and SOC 2 compliance audits. No Microsoft technology, nor any of its component technologies, including the Software, is intended or made available as a substitute for the professional advice, opinion, or judgement of a certified financial services professional. Do not use the Software to replace, substitute, or provide professional financial advice or judgment.  

BY ACCESSING OR USING THE SOFTWARE, YOU ACKNOWLEDGE THAT THE SOFTWARE IS NOT DESIGNED OR INTENDED TO SUPPORT ANY USE IN WHICH A SERVICE INTERRUPTION, DEFECT, ERROR, OR OTHER FAILURE OF THE SOFTWARE COULD RESULT IN THE DEATH OR SERIOUS BODILY INJURY OF ANY PERSON OR IN PHYSICAL OR ENVIRONMENTAL DAMAGE (COLLECTIVELY, “HIGH-RISK USE”), AND THAT YOU WILL ENSURE THAT, IN THE EVENT OF ANY INTERRUPTION, DEFECT, ERROR, OR OTHER FAILURE OF THE SOFTWARE, THE SAFETY OF PEOPLE, PROPERTY, AND THE ENVIRONMENT ARE NOT REDUCED BELOW A LEVEL THAT IS REASONABLY, APPROPRIATE, AND LEGAL, WHETHER IN GENERAL OR IN A SPECIFIC INDUSTRY. BY ACCESSING THE SOFTWARE, YOU FURTHER ACKNOWLEDGE THAT YOUR HIGH-RISK USE OF THE SOFTWARE IS AT YOUR OWN RISK.
