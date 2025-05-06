## How long does this take to deploy? 

Standard deployment can take anywhere from 30-45 minutes, assuming all prerequisites are already in place, but may vary depending on the specific configurations within the environment used. 
 
## What regions are supported? 

Most regions are supported but always check the specific product page and deployment guide for detailed information. 

## What is on the roadmap for enhancements? 

There’s no roadmap for enhancements planned for this accelerator. 

## What security standards does Microsoft follow in its Solution Accelerators? 

Our Solution Accelerators adhere to rigorous security standards, integrating AI principles like transparency, accountability, fairness, inclusiveness, reliability & safety, and privacy & security. We conduct responsible AI impact assessments, privacy and security reviews, and red teaming to manage risks. Our Gold Standard Accelerator recipe ensures trust through high-quality materials, quick deployment with one-click automation, and a well-defined lifecycle. 

## Where can I go to learn more about other Solution Accelerators? 

You can find more information about our suite of Solution Accelerators by visiting our landing page on GitHub: Microsoft Solution Accelerators 

## What type of data is supported? 

**ServiceNow:** 

Employee Information

*Key Fields*

* Full Name: Pier Thill 
* Current Office Location: Contoso-Redmond 
* Future Office Location: Contoso-NewYork 
* Employment Type: Full-time 
* Job Title: Business Analyst  
* HR representative: Carol Bouchard 

Benefits policies by Office Location (5 ServiceNow KB articles)

* Each article contains a high-level list of benefits available in a given office*
* Benefits vary slightly by office location*

FAQ (ServiceNow KB article)

* Single article with description of the relocation process for Contoso

**SharePoint:**

* Relocation Request Initiation Letter (Documents) Structure and non-dynamic content manually  
* Template dynamic fields, and where we will source them  
     *Offer Date* - Date of Power Automate execution
     *Anticipated Start Date* - Gathered from Henry during interaction 
     *Candidate Current Office Location* - Pulled from ServiceNow; hero location: Contoso-Redmond
     *Full Name* - Pulled from ServiceNow
     *Job Title* - Pulled from ServiceNow 
     *Destination Location* - Gathered from employee during interaction 
     *Salary Guidance* - Cost of living salary adjustment. Dynamically created based on a lookup and calculation, taking into account origin and destination; Example: “-10% to -6%”

**Dataverse:**

Relocation (Table) 

*Key Fields*
* User (user record)  
* Relocating from (string)  
* Relocating to (string)  
* Salary Guidance (string) - Example: “+5% to +9%”  
* Date of Relocation (date) 
* Reason 
* Personal/Business  
* Survey Sent (boolean)  
* Survey Completed (boolean)  
* Process Rating (choice)  
* Agent Rating (choice)  
* Rating Comments (multiline string)  
* Status / Status Reason - Active: Requested / Approved / Accepted  / Relocated . Inactive: Completed  / Rejected / Cancelled 

## How can I provide feedback or report an issue/bug? 

All bugs should be filed via the respective public GitHub repository's Issues tab. This allows our team to track and address issues efficiently. 

## Who can I contact to learn more about this Solution Accelerator? 

If you have questions or want to learn more about this Solution Accelerator, please contact your Microsoft account representative. 