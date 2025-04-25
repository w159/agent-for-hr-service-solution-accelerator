# Usage Guidance

To see the key capabilities of this accelerator in action after completing the installation, follow the execution step guidance included below.

Note that the steps follow a sequence conducted by the persona of **Pier**, a Business Analyst at Contoso.

Pier is planning to relocate to New York City, for personal reasons. Before taking the next step, he wants to quickly understand the relocation process, including any potential changes to his compensation and benefits. 

## Usage Note
The Adaptive Card shown at the start (or restart) of a conversation offers three clickable options. The first two options offer guidance on HR-related topics. But the third button contains the label "How can I relocate to another office?" which Pier can click <u>or</u> write a similar inquiry. 

## Execution steps for Customer <> AI Agent interaction:
Acting as Pier, go to Microsoft Teams, and engage in a chat with the Agent for HR Service. 

* **AI Agent**: Welcome to your HR Self Service Assistant. Here are the options I can assist you with today. How do I submit an expense report? When is the next payday? How can I relocate to another office? 
* **Pier**: Types "What are the steps to relocate to another Contoso office?" <u>or</u> Clicks on **How can I relocate to another office?** (click this option from the Adaptive Card)
* **AI Agent:** To relocate to another Contoso office, follow these steps: 
    - Assess Benefits and Compensation: Review the differences in benefits and compensation packages for the office you are considering. For example, Contoso-Redmond offers a 5% retirement plan contribution, while Contoso-Dublin offers 4% and Contoso-Guangzhou offers 2%.
    - Submit Relocation Request: Initiate a relocation requet through the HR Self-Service portal. Provide necessary details such as your current office location, and any specific requirements or preferences. 
     - Approval Process: Your relocation request will go through an approval process. HR will review your request and may require additional information or documentation. 
    - Prepare for Relocation: Once approved, prepare for your move. This may include arranging travel accomodation, and understanding the local benefits and services available at your new office location. 
    - Feedback Submission: After relocating, you will be prompted to submit feedback through the Post Relocation Survey. This helps HR gather insights and improve the relocation process. 
These steps ensure a smooth transition to your new Contoso office.
* **Pier**: How would my compensation change if I move to New York?
* **AI Agent:** I see you currently work out of our Contoso-Redmond office and the Contoso-NewYork office, your salary would be likely to be adjusted by +1% to +5%. 
Certainly. Here are the differences in benefits between employees in the Contoso-Redmond office and employees in the Contoso-NewYork office:
    - Retirement Plan Contributions:
        - Contoso-Redmond: 5% of your salary
        - Contoso-NewYork: 8% of your salary
    - Fitness Perks Benefit:
        - Contoso-Redmond: Up to $1200 USD per year
        - Contoso-NewYork: Access to Contoso legal advisory services for a variety of issue types
    - Both offices offer Tier 1 Health Insurance Coverage and a 50% discount on any merchandise from the Contoso company store. Would you like to proceed with initiating a request to relocate to the Contoso-NewYork based on this guidance?
* **Pier**: Yes
* **AI Agent**: What is your planned date of relocation?
* **Pier**: in two months
* **AI Agent**: Are you moving for business or personal reasons? (Agent displays two buttons, "Business" and "Personal")
* **Pier**: Selects "Personal" (His reply appears in the chat)
* **AI Agent**: Great! Based on the location details you have provided, as well as the existing locatio information on your HR profile, here are the details and potential changes to your pay. Would you like to make adjustments to any specific aspect of your proposed relocation, or proceed to begin the approval process?
* <i>Note: The Agent displays a card entitled "Relocation Summary" which summarizes the information gathered thus far from the conversation, including Current Office, New Office, Moving Date, and Salary Adjustment Range. The card contains two buttons, "Discard" and "Proceed"</i>
* **Pier**: Selects "Proceed" button
* <i>Note: The card displays an informational footer "Your response was sent to the app"</i>
* **AI Agent**: An approval request has been sent to your HR representative. You will be notified when the status of the relocation request has been updated.
* <i>Note: When this happens, the HR representative will receive a Teams Notification from the Approvals app. If your permissions were set correctly, the notification will appear on your own PC screen, next to the ongoing chat. You should also be able to view and take action on the approval by navigating to the Approvals app (and ensuring you are viewing approvals for the appropriate Dataverse environment), or via an email message.</i> 

You'll now take on the persona of the HR Representative. 
- Tap the notification.
  It will display a modal containing "Approval request details" titled "Relocation Request for Pier Thill". The emplyee's name, title, and all information the employee has acknowledged. 
- Scroll down.
  An enclosure, "View Employee Profile" allows optional access to additional details. The modal also has a space to add any comments. Three buttons are displayed, "More actions", "Initiate Relocation" and "Reject Request". 
- Click the "Initiate Relocation" button
After a "Submitting your response" spinner, the approval is documented in the Approvals application. This concludes the HR representative's actions.

You will now resume the Contoso employee's persona.

* <i>Note: Immediately, a real-time notification from the will appear on your PC screen, next to the ongoing chat, where the Approvals app reports "Final status: Completed"</i>
* **AI Agent**:  
Hi Pier, 
Congratulations! Location request has been approved by your manager and the HR representative. You'll find all your related documents below as well as in your email. Please review and confirm that all the details are accurate.
* <i>Note: An Adaptive card titled "Relocation Proposal Letter" is displayed. It reads "this document outlined the details of your relocation proposal", listing the location and move date. It displays three buttons called "View Proposal", "Cancel", and "Accept"</i>
* **Pier**: Select "View Proposal"
* <i>Note: Microsoft Word opens and displays a full-page letter addressed from Contoso HR to the employee. It has one section summarizing the proposed relocation, another sharing the position/title and reporting information; then concludes with a section on next steps for the employee.</i>
* **Pier**: Select "Accept"
* **AI Agent**: Your relocation request has been successfully confirmed! Below we have provided you with some additional onboarding and relocation support details. We're excited for your upcoming move!
* **Note** Agent displays a card titled "Next steps for your relocation" which links to some resources: Change of Address (links to update HR profile with your new address); Flexible Work @ Contoso (Employee Guide to provide clarity and guidance on flexible work hours); and Start your move (Explore tools and tips to make your move smooth and stress-free).
* **Pier**: Click on "Start your move"
* <i>Note: A notification message "Your response was sent to the app" appears</i> 

Behind the scenes, this action will update Dataverse to show that the move has been completed. 

This is helpful as it wakes up the Autonomous feature built into the solution. Regardless of its source, a change in Dataverse indicating the move has been completed will trigger an autonomous Post-Relocation Feedback Survey.

Selecting the "Start your move" button triggers it immediately, for the purposes of this demo.

<i>**Usage Note**: The autonomous triggering functionality relies on Generative AI-based orchestration to trigger the appropriate topic. It is possible, though unlikely, that the topic will not get triggered. If you have not received an invitation to complete a survey after roughly one minute, you can click "Start your move" again, to trigger the agent again.</i>

* **AI Agent**: Hi Pier,
It's been two weeks since your move to Contoso-NewYork, and we hope you're settling in well. We'd love to hear your thoughts on how the relocation process went. Could you take a minute to answer a few quick questions? Your feedback will help us iprove the experience for future employees. Let's get started" It presents two options, "Start Survey", "Maybe Later". 
* **Pier**: Select "Start Survey"
* **AI Agent**: Overall satisfaction: How would you rate your overall satisfaction with the relocation process? Five buttons appear: "Excellent", "Very Good", "Good", "Fairly Poor", and "Very Poor".
* **Pier**: Select "Very Good" (or other option).
* <i>Note: The selection appears in the chat conversation</i>
* **AI Agent**: HR Self Service Agent Accuracy: How would you rate the accuracy of the answers provided by the HR Self Service Agent? Five buttons appear: "Excellent", "Very Good", "Good", "Fairly Poor", and "Very Poor".
* **Pier**: Select "Very Good" (or other option).
* <i>Note: The selection appears in the chat conversation</i>
* **AI Agent**: What other feedback would you like to share about your experience?
* **Pier**: It was amazing to work with the agent! 
* **AI Agent**: Thank you for your feedback! Your insights will help us enhance the relocation process for future employees. 