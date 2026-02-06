# Recruitment Automation State Machine

A high-performance, automated recruitment funnel designed for agencies in fast-paced markets like Dubai. This system eliminates manual screening and ensures a response time of under 5 minutes for every lead.

## 🚀 Overview
The workflow functions as a **State Machine**, managing the candidate lifecycle from initial contact to interview booking. By integrating WhatsApp and Voice AI, the system qualifies leads in real-time and only involves human recruiters when a candidate is vetted and scheduled.

## 🛠 Tech Stack
* **n8n**: Core orchestration and logic engine.
* **Zoho CRM**: Central database for candidate management.
* **360dialog (WhatsApp Business API)**: Automated messaging and engagement.
* **OpenAI (GPT-4o)**: Intelligent chat screening and data extraction.
* **Retell AI**: Voice AI for automated qualification calls and English proficiency checks.
* **Cal.com**: Self-service interview scheduling.

## 📋 Features
* **Instant Lead Capture**: Webhooks for Facebook Lead Ads, LinkedIn, and email parsing for portals like Dubizzle.
* **Immediate Engagement**: Automated WhatsApp outreach triggered the moment a lead enters the system.
* **AI Chat Screening**: GPT-4o filters candidates based on specific criteria (experience, location, licenses).
* **Voice AI Verification**: Automated phone calls to confirm details and assess communication skills.
* **Automated Scheduling**: Qualified leads receive a Cal.com link to book their own interview.
* **CRM Synchronization**: Real-time status updates in Zoho CRM (e.g., Screening, Qualified, Interview Scheduled).
* **Retention Hooks**: Automated 24-hour reminders via WhatsApp to reduce interview no-shows.

## ⚙️ Setup Instructions

### 1. Environment Preparation
* **n8n**: Recommended Cloud instance or Self-Hosted via Docker (2GB RAM min).
* **SSL**: Must be enabled for webhook functionality (required for Facebook and 360dialog).

### 2. API Configuration
Configure the following credentials within your n8n instance:
* **Zoho CRM**: OAuth2 credentials via the Zoho API Console.
* **360dialog**: API Key from the 360dialog Hub.
* **OpenAI**: Secret Key from the OpenAI Platform.
* **Retell AI**: API Key and Agent ID for voice calls.
* **Cal.com**: API Key and Event Type ID.

### 3. Deployment
1. **Import Workflow**: Import the `Recruitment Automation State Machine.json` file into n8n.
2. **Configure Webhooks**: 
    * Set the Facebook Lead Ad callback.
    * Map the 360dialog inbound message webhook.
    * Set the Cal.com "Booking Created" webhook.
3. **Custom CRM Fields**: Ensure Zoho CRM includes these custom fields:
    * `AI_Screening_Status`
    * `Disqualification_Reason`
    * `Interview_Date`
    * `Voice_Call_Result`

## 📊 Key Metrics Tracked
* **Speed to Contact**: Goal of < 5 minutes.
* **Funnel Conversion**: Tracking rates from Applied → Screened → Booked.
* **Recruiter Efficiency**: Reduction in manual "chase" time by up to 80%.

---
*Built to transform recruitment from a manual chase into a 24/7 automated engine.*
