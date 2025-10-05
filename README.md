# customer_sentiment_alert_agent-n8n

# AI Agent Workflow for n8n

## Overview
This n8n workflow monitors social media, reviews, and forums for negative feedback, uses an LLM to generate suggested responses, sends email alerts to the team, and provides JSON output for frontend dashboards.

## Features
- **Monitor Feedback:** Collect tweets/posts with keywords like `problem`, `complaint`, `not working`, `frustrated`, etc.  
- **Sentiment Analysis:** Classify feedback as negative, positive, or neutral.  
- **Suggested Responses:** Generate LLM-based reply suggestions.  
- **Team Alerts:** Automatic emails for urgent negative feedback.  
- **Frontend Integration:** JSON response for dashboards or apps.  

## Workflow Diagram
trigger_node → Fetch Tweets/Reviews → LLM → Filter Negative Feedback → Set Node → Email Node 

## Setup
1. Import `ai-agent-workflow.json` into n8n.  
2. Configure credentials for LLM, Email SMTP, and data sources (Twitter API).  
3. Adjust query parameters and keywords for your needs.  
4. Run manually via webhook or schedule workflow.  

## Frontend Example
JSON returned by HTTP Response Node:

```json
{
  "tweets": [
    {
      "username": "@user1",
      "comment": "Negative comment",
      "suggested_response": "Thank you, we'll improve",
      "tweet_id": "1234567890"
    }
  ]
}
