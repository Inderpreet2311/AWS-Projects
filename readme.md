# AWS Projects

A collection of hands-on AWS projects covering conversational AI, serverless integration, and data visualization. Built through guided real-environment labs to strengthen practical cloud skills alongside AWS certification study.

## Projects

### 1. Build a Chatbot with Amazon Lex
Built a conversational banking chatbot (**BankerBot**) from scratch using Amazon Lex, configuring language settings, IAM permissions, and intent classification confidence thresholds.

- Created a `WelcomeIntent` as a friendly conversation starter
- Configured and tested the `FallbackIntent` to handle unrecognized input gracefully, including adding response variations to avoid repetitive replies to users
- Explored how intent classification confidence scoring (default 0.40) determines when a bot responds vs. falls back

### 2. Build a Chatbot with Custom Slots
Extended the BankerBot with **custom slots** to capture structured information (account type, date of birth) directly from natural conversation instead of generic replies.

- Created a custom slot type with restricted values to ensure only valid account types are accepted
- Connected the custom slot to a `CheckBalance` intent, using slot values to drive appropriate bot responses
- Added slot values directly into sample utterances (e.g. "can I check my account balance") to improve natural language matching

### 3. Connect a Chatbot with Lambda
Integrated the Lex chatbot with an **AWS Lambda** function to fetch a user's account balance dynamically after identity verification.

- Wrote a Lambda function to process intent requests and return account balance data
- Connected Lambda to the bot's `TestBotAlias`, ensuring external resources interact with the correct bot version
- Configured **code hooks** at the intent level to sync the Lambda function's fulfillment logic with the `CheckBalance` intent

### 4. Save User Info with Your Chatbot
Enhanced the chatbot to **remember conversation context** across multiple exchanges, avoiding repetitive questions and enabling natural follow-up conversations.

- Created an **output context tag** (`contextCheckBalance`) to store a verified user's date of birth for up to 5 turns or 90 seconds
- Built a new `FollowUpCheckBalance` intent so users could ask about additional accounts (e.g. "what about my savings account?") without re-verifying their identity
- Configured an **input context tag** to pull previously stored session data into the new intent automatically

### 5. Visualize Data with Amazon QuickSight
Used **Amazon QuickSight** to build an interactive analytics dashboard from a public Netflix titles dataset.

- Stored source data (CSV) and a `manifest.json` schema file in **S3**, and connected QuickSight directly to the bucket
- Built multiple visualizations — a donut chart, horizontal bar charts, and a stacked bar chart — breaking down content by release year and type
- Applied filters and adjusted chart titles to build a clean, presentation-ready dashboard
- Exported the finished dashboard as a PDF

## Skills Demonstrated

- **Conversational AI**: Amazon Lex bot design, intents, utterances, slots, slot types, fallback handling
- **Serverless Integration**: AWS Lambda function development, event-driven fulfillment, code hooks
- **State Management**: Context tags for multi-turn conversation memory (input/output contexts)
- **Data & Analytics**: S3 data storage, QuickSight dataset creation via manifest files, interactive dashboard design
- **IAM**: Least-privilege role creation scoped to bot-specific data access

## Tools

Amazon Lex · AWS Lambda · Amazon S3 · Amazon QuickSight · IAM

## Notes

These projects were completed as guided, real-environment builds to develop hands-on AWS skills. Each project was built independently in a live AWS account rather than a simulated environment.
