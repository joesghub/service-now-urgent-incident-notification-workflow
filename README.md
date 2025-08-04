# service-now-urgent-incident-notification-workflow

## System Overview
This is a multi-purpose Critical Priority Incident Workflow that alerts teams of newly created Critical Priority Incident tickets in their respective category. 

## Architecture Diagram
![Critical Priority Network Incident Workflow Diagram](https://raw.githubusercontent.com/joesghub/service-now-urgent-incident-notification-workflow/refs/heads/main/screenshots/Critical%20Priority%20Network%20Incident%20Workflow%20Diagram.png)

## Implementation Steps
I began by inspecting the current "Kura WL1 Flow" in WorkFlow Studio. The original flow was set to Trigger on Incidents created with the Urgency "2 - Medium" for any Assignment group selected.
![Original Workflow Trigger](https://github.com/joesghub/service-now-urgent-incident-notification-workflow/blob/main/screenshots/og%20Kura%20WL1%20Flow%20-%20Trigger.png?raw=true)
The action was set to send a notification. 
![Original Workflow Action](https://github.com/joesghub/service-now-urgent-incident-notification-workflow/blob/main/screenshots/og%20Kura%20WL1%20Flow%20-%20Action.png?raw=true)
I found the original notification record to understand what was suppossed to be going out to the assigned teams.
![Filtering Notification to Find the One Used in the Original Workflow](https://github.com/joesghub/service-now-urgent-incident-notification-workflow/blob/main/screenshots/filtering%20for%20Notifications.png?raw=true)
A random group was the current receipient. 
![Original Notification Recipients](https://github.com/joesghub/service-now-urgent-incident-notification-workflow/blob/main/screenshots/og%20Notification%20recipients.png?raw=true)
And the email format was lackluster. There wasn't more details about the ticket, just a message asking for the receipient to respond.
![Original Notification Template](https://github.com/joesghub/service-now-urgent-incident-notification-workflow/blob/main/screenshots/og%20Notification%20email%20template.png?raw=true)
With all of these features explored, I had a good idea of how to begin remediating the workflow. I set out to assign the correct recipients to the same notification record being used.
![Filtering Groups to Find the Network Ops Team](https://github.com/joesghub/service-now-urgent-incident-notification-workflow/blob/main/screenshots/filtering%20for%20groups.png?raw=true)
Once I determined the proper group, I confirmed the record was set to "Triggered" allowing the notification to be used in our workflow.
![New Notification Trigger](https://github.com/joesghub/service-now-urgent-incident-notification-workflow/blob/main/screenshots/new%20Notification%20same%20trigger.png?raw=true)
I assigned the Networking Operations group as the recipient.
![New Notification Recipients](https://github.com/joesghub/service-now-urgent-incident-notification-workflow/blob/main/screenshots/new%20Notif%20recipients.png?raw=true)
Based on other notification being sent out, I updated the email notification template and enhanced the message body with dynamic fields from the critical prioirity record.
![New Notification Template](https://github.com/joesghub/service-now-urgent-incident-notification-workflow/blob/main/screenshots/new%20Notif%20email%20temp.png?raw=true)
The trigger in my workflow now activated when incident tickets with Prioirity of "1 - Critical" and Category of "Network" were created. The priority is determined by the Imapct and Urgency values selected by the Caller submitting the ticket. 
![New Workflow Trigger](https://github.com/joesghub/service-now-urgent-incident-notification-workflow/blob/main/screenshots/new%20flow%20trigger.png?raw=true)
Now I was able to use the updated Notification record in my workflow action. 
![New Workflow Action](https://github.com/joesghub/service-now-urgent-incident-notification-workflow/blob/main/screenshots/new%20flow%20action.png?raw=true)
I created some test incidents.
![Test Incidents List](https://github.com/joesghub/service-now-urgent-incident-notification-workflow/blob/main/screenshots/test%20incident%20list.png?raw=true)
Like this scenario of drivers getting wrong directions submitted by Zane.
![Test Incident from List](https://github.com/joesghub/service-now-urgent-incident-notification-workflow/blob/main/screenshots/test%20incident%20four.png?raw=true)
You can see the expected notification email with its full formatting and dynamic values present!
![New Email Notification](https://github.com/joesghub/service-now-urgent-incident-notification-workflow/blob/main/screenshots/new%20notif%20email.png?raw=true)

## AI Scenario
**Hypothetical Scenario**
Your company operates globally across multiple time zones. Critical incidents often occur outside business hours when senior engineers aren't available. The current escalation process follows a rigid hierarchy that doesn't account for engineer expertise, current availability, or incident complexity, leading to prolonged resolution times.

**Explain how an AI agent could enhance your incident notification system to:**
- Intelligently route incidents based on engineer expertise and availability
- Learn from historical resolution patterns to improve future routing decisions
  - At Uber, we have gloabl teams that follow well establish corporate hierarchies. Our ServiceNow instance is aware of these relationships. An AI agent could learn/develop a "Chain of Command" workflow that raises escalations to Engineer managers who are in the same time zone as the incident and currently online/working. This would allow for better oversight of all tickets and reduce delays to resolution by giving managers notifications that a ticket has gone unassigned or unresolved for too long. In future iterations the AI agent would be trained on past resolved issues and their resolvers to map out an internal bespoke incident resolution rubric. The ruebric would allow the AI agent to make better ticket assignemnt decisions without the approval of a manager for each ticketed incident. 
- Consider time zones and current workloads when selecting responders
  - The agent would compare the potenial asignee's time zone to the time zone of the submitted ticket. It would also search for the amount of tickets currently assigned tot he pool of asignees. This way the agent could both assign the ticket to someone capable of solving the issue and ensure everyone has a manageable amount of tickets assigned. While searching it could even send notification about employees who seem to have too many active tickets currently assigned. 

  
