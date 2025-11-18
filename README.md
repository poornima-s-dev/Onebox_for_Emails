A feature-rich email management system with real-time email synchronization, AI-powered categorization, Slack notifications, suggested replies, and searchable storage using Elasticsearch.

Backend Features

Real-Time Email Synchronization

Sync multiple IMAP accounts (minimum 2).

Fetch last 30 days of emails.

Use persistent IMAP connections (IDLE mode) for real-time updates.

Searchable Storage with Elasticsearch

Store emails in a locally hosted Elasticsearch instance (via Docker).

Implement indexing for fast search.

Filter emails by folder and account.

AI-Based Email Categorization

Categorizes emails into: Interested, Meeting Booked, Not Interested, Spam, Out of Office.

Slack & Webhook Integration

Sends Slack notifications for new Interested emails.

Triggers webhooks for external automation.

AI-Powered Suggested Replies

Stores product and outreach agenda in a vector database.

Uses RAG (Retrieval-Augmented Generation) with LLMs for reply suggestions.

Frontend Interface

Display emails with folder/account filters.

Show AI-based email categorization.

Tech Stack

Node.js with Express

TypeScript

Dotenv

LangChain + Chroma

IMAP (imapflow)

Elasticsearch via Docker

OpenAI/Gemini API

Slack Webhooks

Mailparser

