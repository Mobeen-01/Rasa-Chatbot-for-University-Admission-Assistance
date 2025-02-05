# Rasa Chatbot for University Admission Assistance

[![Rasa](https://img.shields.io/badge/Rasa-3.x-purple.svg?style=flat&logo=rasa)](https://rasa.com)
[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg?style=flat&logo=python)](https://www.python.org)
[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)

## Introduction
This project is a Rasa-powered chatbot designed to assist with university admissions. It provides automated support for queries related to the admission process, reducing the need for physical visits to the university office.

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
- Use ngrok to expose your local Rasa server: `ngrok http 5005`
- Configure Facebook Messenger and Slack webhook settings to connect to the Rasa server.

## License
This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).
