# OneBox for Emails

A feature-rich email management system with real-time email sync, AI categorization, Slack notifications, suggested replies, and searchable storage using Elasticsearch.

## Backend Features

1. **Real-Time Email Sync**  
   - Sync multiple IMAP accounts (min 2)  
   - Fetch last 30 days of emails  
   - Use persistent IMAP connections (IDLE mode)

2. **Searchable Storage with Elasticsearch**  
   - Store emails locally with Docker  
   - Index emails for fast search  
   - Filter by folder & account

3. **AI-Based Email Categorization**  
   - Labels: Interested, Meeting Booked, Not Interested, Spam, Out of Office

4. **Slack & Webhook Integration**  
   - Slack notifications for Interested emails  
   - Trigger webhooks for automation

5. **AI-Powered Suggested Replies**  
   - Store product & agenda in vector database  
   - Use RAG with LLM for reply suggestions

6. **Frontend Interface**  
   - Display emails  
   - Filter by folder/account  
   - Show AI categorization

## Tech Stack

Node.js, TypeScript, Express, Dotenv, LangChain + Chroma, IMAP (`imapflow`), Elasticsearch, OpenAI/Gemini API, Slack Webhooks, Mailparser

## Folder Structure

```
backend/
 ├─ src/
 │  ├─ controllers/
 │  ├─ routes/
 │  ├─ imap/
 │  ├─ services/
 │  └─ utils/
 └─ index.ts
.env
package.json
tsconfig.json
docker-compose.yml
```

## Environment Setup (.env)

```
GEMINI_API_KEY='Your Gemini API key'
SlackWebhook_URL='Your Slack webhook URL'
INTERESTED_WEBHOOK_URL='Webhook URL for Interested emails'
```

## Running Locally

### Prerequisites
- Node.js v18+  
- Docker Desktop  
- IMAP-enabled Gmail with App password  
- Postman (optional)

### Steps
1. Clone repo:
```
git clone https://github.com/poornima-s-dev/Onebox_for_Emails.git
cd OneBox_Assignment
```
2. Install dependencies:
```
npm install
```
3. Run Elasticsearch:
```
docker-compose pull
docker-compose up
```
4. Start server:
```
npm run dev
```

## API Endpoints

### Add IMAP Account
```
POST /api/accounts
```
Body:
```json
{
  "email": "your@gmail.com",
  "password": "your_app_password",
  "host": "imap.gmail.com",
  "port": 993,
  "secure": true
}
```

### Suggest AI Reply
```
POST /api/reply/suggest
```
Body:
```json
{
  "subject": "Let's schedule an interview",
  "body": "You've been shortlisted. Please share your availability.",
  "email": "hr@example.com"
}
```

## Common Issues
- Gmail IMAP login: use App password & 2FA  
- Elasticsearch: ensure Docker is running & port 9200 is free  
- Categorization: check Gemini API key

## Demo
[OneBox Demo](https://drive.google.com/file/d/1sYBR3JsdO_wWkNVQtHjTiYtnaACnDuri/view?usp=sharing)

## Credits
- Project structure & error handling assisted by ChatGPT  
- References: Slack Webhooks, Chroma & VectorDB, LangChain
