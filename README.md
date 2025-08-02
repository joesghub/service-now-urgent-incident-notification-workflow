# service-now-urgent-incident-notification-workflow

## System Overview
*Description of the working incident notification system*

## Architecture Diagram
![Critical Priority Network Incident Workflow Diagram](https://raw.githubusercontent.com/joesghub/service-now-urgent-incident-notification-workflow/refs/heads/main/screenshots/Critical%20Priority%20Network%20Incident%20Workflow%20Diagram.png)

## Implementation Steps
I began by inspecting the current "Kura WL1 Flow" in WorkFlow Studio. The original flow was set to Trigger on Incidents created witht he Urgency "2 - Medium"
![Original Workflow Trigger](https://github.com/joesghub/service-now-urgent-incident-notification-workflow/blob/main/screenshots/og%20Kura%20WL1%20Flow%20-%20Trigger.png?raw=true)
![Original Workflow Action](https://github.com/joesghub/service-now-urgent-incident-notification-workflow/blob/main/screenshots/og%20Kura%20WL1%20Flow%20-%20Action.png?raw=true)
![Filtering Notification to Find the One Used in the Original Workflow](https://github.com/joesghub/service-now-urgent-incident-notification-workflow/blob/main/screenshots/filtering%20for%20Notifications.png?raw=true)
![Original Notification Recipients](https://github.com/joesghub/service-now-urgent-incident-notification-workflow/blob/main/screenshots/og%20Notification%20recipients.png?raw=true)
![Original Notification Template](https://github.com/joesghub/service-now-urgent-incident-notification-workflow/blob/main/screenshots/og%20Notification%20email%20template.png?raw=true)
![Filtering Groups to Find the Network Ops Team](https://github.com/joesghub/service-now-urgent-incident-notification-workflow/blob/main/screenshots/filtering%20for%20groups.png?raw=true)
![New Notification Trigger](https://github.com/joesghub/service-now-urgent-incident-notification-workflow/blob/main/screenshots/new%20Notification%20same%20trigger.png?raw=true)
![New Notification Recipients](https://github.com/joesghub/service-now-urgent-incident-notification-workflow/blob/main/screenshots/new%20Notif%20recipients.png?raw=true)
![New Notification Template](https://github.com/joesghub/service-now-urgent-incident-notification-workflow/blob/main/screenshots/new%20Notif%20email%20temp.png?raw=true)
![New Workflow Trigger](https://github.com/joesghub/service-now-urgent-incident-notification-workflow/blob/main/screenshots/new%20flow%20trigger.png?raw=true)
![New Workflow Action](https://github.com/joesghub/service-now-urgent-incident-notification-workflow/blob/main/screenshots/new%20flow%20action.png?raw=true)
![Test Incidents List](https://github.com/joesghub/service-now-urgent-incident-notification-workflow/blob/main/screenshots/test%20incident%20list.png?raw=true)
![Test Incident from List](https://github.com/joesghub/service-now-urgent-incident-notification-workflow/blob/main/screenshots/test%20incident%20four.png?raw=true)
![New Email Notification](https://github.com/joesghub/service-now-urgent-incident-notification-workflow/blob/main/screenshots/new%20notif%20email.png?raw=true)





## AI Scenario
**Hypothetical Scenario**
Your company operates globally across multiple time zones. Critical incidents often occur outside business hours when senior engineers aren't available. The current escalation process follows a rigid hierarchy that doesn't account for engineer expertise, current availability, or incident complexity, leading to prolonged resolution times.

**Explain how an AI agent could enhance your incident notification system to:**
- Intelligently route incidents based on engineer expertise and availability
  - Hello
- Consider time zones and current workloads when selecting responders
  - Yes
- Learn from historical resolution patterns to improve future routing decisions
  - Hi
