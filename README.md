# Auralis - AI WhatsApp Chatbot for AutoHall

Premium AI chatbot for an automotive dealership (Opel - AutoHall Tétouan), 
built as part of a DUT Computer Science (Artificial Intelligence) internship - EST Tétouan.

## 🎯 Objective

Automate customer relations on WhatsApp: answering vehicle-related questions, 
qualifying leads, booking appointments, and escalating to a human advisor when needed.

## 🧱 Tech Stack

- **n8n** — workflow orchestration (self-hosted via Docker + ngrok)
- **Google Gemini 2.5 Flash** — conversational AI model
- **WhatsApp Business API (Meta Cloud API)** — messaging channel
- **Google Sheets** — qualified lead storage

## ✨ Features

- Multilingual responses (Darija, French, Standard Arabic, English)
- Custom brand identity and tone ("Auralis" - obsidian & gold)
- Per-customer conversation memory (session keyed by WhatsApp phone number)
- Automatic lead qualification (Hot / Warm / Cold)
- Automatic capture of test drive / showroom visit requests
- Escalation to a human advisor for complex cases

## 🏗️ Architecture
WhatsApp Trigger → Text Extraction → AI Agent (Gemini 2.5 Flash)
├── Memory (Buffer Window, keyed by phone number)
└── Tool: Save Lead to Google Sheets
→ Respond with Text (WhatsApp)

## 🚀 Setup

1. Import `Whatsapp_Agent.template.json` into your n8n instance
2. Replace all `[PLACEHOLDER]` values with your own details (address, contacts, website)
3. Configure credentials:
   - WhatsApp Business API (Meta)
   - Google Sheets OAuth2
   - OpenRouter or Google Gemini API
4. Create a Google Sheet with columns: `Timestamp, Name, Phone, Model of Interest, Request Type, Budget, Urgency, Conversation Summary`
5. Publish the workflow and connect the WhatsApp webhook

## 📌 Notes

This project was built for educational purposes (DUT internship). 
Real credentials and data are not included in this repository.

## 👤 Author

Yakin — DUT Computer Science (AI) Student, EST Tétouan
