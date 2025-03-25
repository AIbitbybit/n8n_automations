# n8n Workflow Automations

This repository contains workflow automations built with n8n, focused on providing AI-powered customer support solutions.

Copy paste the JSON into n8n for better viewing.

## Workflows

### Chat Support System

The `chat_support.json` workflow creates an AI-powered customer support system that:

- Receives incoming chat messages from users
- Uses OpenAI's GPT-4o to analyze message sentiment (positive/neutral or negative)
- Routes messages based on sentiment analysis:
  - For negative sentiment: Escalates to a human agent via Slack
  - For neutral/positive sentiment: Connects to a RAG (Retrieval Augmented Generation) API to provide document-based answers
- Provides real-time responses back to users with relevant information or support status

#### Key Features

- **Sentiment Analysis**: Automatically categorizes incoming messages as neutral/positive or negative
- **Human Escalation**: Negative messages are routed to a dedicated Slack channel where agents can be assigned
- **Knowledge Base Integration**: Connects to a RAG API to retrieve document-based answers for standard queries
- **Agent Assignment**: Tracks which agent is assigned to a case and communicates this to the user
- **Response Handling**: Manages both automated and human responses through a unified system

#### Technical Components

- **Chat Trigger Node**: Entry point for incoming messages
- **AI Agent**: Uses OpenAI GPT-4o to analyze message sentiment
- **Switch Node**: Routes the flow based on sentiment analysis results
- **HTTP Request Node**: Connects to the RAG API (running at host.docker.internal:8000)
- **Slack Integration**: Sends messages to the support-escalations channel for agent assignment
- **Memory System**: Maintains chat context for more coherent responses

#### Setup Requirements

- n8n instance with OpenAI API credentials configured
- Slack workspace with OAuth2 authentication
- RAG API service running on port 8000

## Installation

1. Clone this repository
2. Copy the workflows to your n8n instance
3. Configure the required credentials:
   - OpenAI API key
   - Slack OAuth2 credentials
4. Start the RAG API service on port 8000
5. Test the workflow by sending a message through the chat interface

## Usage

1. Deploy your n8n instance using the included docker-compose.yml
2. Import the workflows from the workflows directory
3. Configure the necessary credentials
4. Activate the workflows

For more detailed implementation guides, see the documentation within each workflow.
