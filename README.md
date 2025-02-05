# Rasa Chatbot for University Admission Assistance

[![Rasa](https://img.shields.io/badge/Rasa-3.x-purple.svg?style=flat&logo=rasa)](https://rasa.com)
[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg?style=flat&logo=python)](https://www.python.org)
[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)

## Introduction
This project is a Rasa-powered chatbot designed to assist students with university admission-related queries. The chatbot provides:
- Automated responses for frequently asked admission-related questions.
- Guidance on admission deadlines, required documents, and eligibility criteria.
- Information on available programs, scholarships, and financial aid.
- Integration with Facebook Messenger and Slack for real-time support.
- Reduced workload for university admission offices by handling routine queries efficiently.
- AI-based conversational flow to improve student engagement and query resolution.
- Natural Language Processing (NLP) capabilities to understand and respond intelligently to user queries.
- Extensible architecture allowing for further enhancements, such as voice-based interaction and multilingual support.

## Project Overview
The chatbot is built using Rasa, an open-source machine learning framework for building AI-based conversational applications. It leverages:
- **Rasa NLU** for intent classification and entity extraction.
- **Rasa Core** for managing conversation flow through machine learning models.
- **Custom Actions** to fetch real-time admission details from databases or APIs.
- **Webhooks** for integrating with third-party applications like Facebook Messenger and Slack.
- **Training Data** enriched with real-world admission-related queries to improve response accuracy.

This project is particularly useful for universities and educational institutions aiming to automate and enhance their admission inquiry process.

## Installation
To set up the chatbot, install the necessary dependencies:
```bash
pip install rasa
pip install tensorflow
pip install --upgrade tensorflow
```

## Training the Chatbot
Train the Rasa model using:
```bash
rasa train
```

## Running the Chatbot
To start the chatbot in the terminal, use:
```bash
rasa shell
```

To run the chatbot and expose it via ngrok for integration with Facebook and Slack:
```bash
rasa run
ngrok http 5005
```
Then, configure your Facebook and Slack channels accordingly.

## Integration with Facebook and Slack
To integrate the chatbot with Facebook Messenger and Slack, follow these steps:

### Facebook Messenger Integration
1. **Create a Facebook App:**
   - Go to [Facebook Developer Portal](https://developers.facebook.com/)
   - Create a new app and select "Messenger"
2. **Create a Facebook Page:**
   - Your chatbot needs a page to interact with users.
3. **Generate a Page Access Token:**
   - Under "Messenger" settings, generate a token for your page.
4. **Set Up Webhooks:**
   - Go to "Webhooks" in the Facebook Developer Console.
   - Subscribe to messages and other relevant events.
   - Provide your `ngrok` URL as the webhook callback.
5. **Update Rasa Credentials:**
   - Open `credentials.yml`
   - Add the generated `page-access-token`:
   ```yaml
   facebook:
     verify: "YOUR_VERIFY_TOKEN"
     secret: "YOUR_APP_SECRET"
     access_token: "YOUR_PAGE_ACCESS_TOKEN"
   ```
6. **Restart Rasa and Test:**
   ```bash
   rasa run
   ngrok http 5005
   ```

### Slack Integration
1. **Create a Slack App:**
   - Visit [Slack API](https://api.slack.com/apps) and create an app.
2. **Enable Bot Permissions:**
   - Under "OAuth & Permissions," add `chat:write`, `im:history`, and `bot` scopes.
3. **Generate a Bot User OAuth Token:**
   - Copy the token from the OAuth settings.
4. **Update Rasa Credentials:**
   - Open `credentials.yml`
   - Add the generated `bot-token`:
   ```yaml
   slack:
     bot_token: "YOUR_BOT_USER_OAUTH_TOKEN"
     slack_signing_secret: "YOUR_SIGNING_SECRET"
   ```
5. **Restart Rasa and Test:**
   ```bash
   rasa run
   ngrok http 5005
   ```

## Recommended YouTube Tutorials
For visual guidance, check out these tutorials:
- **Facebook Messenger Integration:** [Watch Here](https://youtu.be/fRMyDIr1Pns?si=KVg00UtgDAWfB-l1)
- **Slack Integration:** [Watch Here](https://youtu.be/YsOcE8pCXsk?si=hUolsNrQZBCra-xj)

## License
This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).
