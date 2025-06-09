# AI Chat Scheduler Agent

## Objective  
Design and deploy an AI agent within n8n that listens for incoming chat messages, looks up user data in a Google Sheets database, schedules an event in Google Calendar, and sends an automated confirmation email.

## Skills Learned  
- **Agent Workflow Design**: Orchestrated an intelligent response loop using n8n's AI Agent and decision-making capabilities.  
- **Database Query Integration**: Used Google Sheets as a structured backend to retrieve contact and context-specific data.  
- **AI Prompting with Memory**: Implemented memory persistence to enhance the contextual continuity of the AI agent across chat interactions.  
- **Automated Scheduling**: Seamlessly connected the AI agent to Google Calendar for automated event creation based on extracted intents.  
- **Email Automation**: Configured dynamic email generation and delivery through Gmail based on event data.

## Tools Used  
- **n8n**: Low-code workflow automation platform for building the orchestration logic.  
- **AI Agent (n8n built-in)**: Central logic engine powered by OpenRouter-compatible LLMs with memory, tool use, and message handling.  
- **GPT 4.1 Mini (OpenRouter)**: Lightweight LLM for efficient and cost-effective task reasoning.  
- **Simple Memory**: Memory module to retain user interaction history and improve multi-turn conversation accuracy.  
- **Google Sheets**: Used as a contacts database to look up names, emails, and context.  
- **Google Calendar**: API integration to create new calendar events from interpreted intents.  
- **Gmail**: Sends a confirmation email with meeting details to the contact.

## Steps 

![image](https://github.com/user-attachments/assets/ae222c3d-d9e8-4a21-adb2-d11160adaac7)

1. **Trigger Chat Listener**: Start workflow when a chat message is received by the agent (via n8n chat input).  
2. **Initialize AI Agent**: Agent receives the message, uses GPT 4.1 Mini as the chat model, and accesses memory for context.  
3. **Query Contacts Database**: AI Agent queries Google Sheets to look up user information (e.g., email address).

![image](https://github.com/user-attachments/assets/a2587d62-3384-4ca7-add9-0e4231dc3e50)

5. **Create Event**: If the intent is to schedule something, the AI Agent uses Google Calendar to book a meeting.

![image](https://github.com/user-attachments/assets/26938111-b7ad-429e-ae8f-0fa70e473fb6)

7. **Send Confirmation Email**: Once the event is created, the agent sends a confirmation email via Gmail to the user. The "Your Name" can be replaced based on prompting the AI Agent before sending the email to know who is sending this.

![image](https://github.com/user-attachments/assets/0f65232c-0348-49b7-a553-9e6274ebc104)

9. **Maintain Context**: Memory updates are preserved to improve follow-up interactions with the same user.
