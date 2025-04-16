# Intelation API Examples

This repository provides example clients, scripts, and Jupyter notebooks for integrating with the [Intelation](https://www.intelation.com) API — a real-time, AI-powered data anonymization platform for developers, AI/ML teams, and privacy-first organizations.

Intelation supports multiple anonymization techniques (masking, encryption, pseudonymization, hashing, redaction, etc.) through a simple, secure API.

---

## Features Covered

- Text anonymization via REST
- Batch document processing
- Entity-level encryption + decryption
- Tokenization and pseudonymization
- WebSocket anonymization (real-time)
- Example notebooks for exploration
- Postman collection for testing
- Cognito-based API authentication

---

## Structure

```
intelation-api-examples/
├── python-client/
│   ├── intelation_client.py      # Python wrapper around Intelation API
│   └── examples/
│       ├── basic_anonymize.py
│       ├── batch_anonymize.py
│       └── decrypt_example.py
├── javascript-client/
│   └── intelation.js             # JS fetch-based client
├── notebooks/
│   └── interactive_anonymization.ipynb
├── postman/
│   └── intelation_api_collection.json
└── .env.example
```

---

## Quick Start (Python)

1. Clone this repo:
```bash
git clone https://github.com/intelation/intelation-api-examples.git
cd intelation-api-examples/python-client
```

2. Create `.env` file based on `.env.example`

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Run a script:
```bash
python examples/basic_anonymize.py
```

---

## Authentication

Intelation uses AWS Cognito for secure user login and API access. You'll need to generate a bearer token (`access_token`) by logging in with your credentials and include it in your request headers:

```http
Authorization: Bearer YOUR_ACCESS_TOKEN
```

You can use the sample `cognito_auth.py` provided to fetch a token programmatically.

---

## REST Endpoints Covered

| Endpoint | Description |
|----------|-------------|
| `POST /anonymize/` | Anonymize a single block of text |
| `POST /anonymize/documents/` | Batch anonymize multiple documents |
| `POST /decrypt/` | Decrypt encrypted entities |
| `GET /get-anonymized-texts` | Fetch saved anonymized texts (authenticated) |

---

## WebSocket Demo

The `websocket/` example demonstrates how to stream live anonymization via:
```
ws://your-api-host/ws/anonymize
```

---

## Notebooks

Explore interactive anonymization, try custom entity types, and test masking strategies in real time with `notebooks/interactive_anonymization.ipynb`.

---

## Postman Collection

Import `postman/intelation_api_collection.json` into [Postman](https://www.postman.com/) for easy endpoint testing with example payloads and environments.

---

## Contributing

Want to add a new language client or integration? PRs welcome! Start by opening an issue or discussion.

---

## Learn More

- [Intelation Website](https://www.intelation.com)
- [API Documentation (Coming Soon)](https://docs.intelation.com)
- Contact: contact@intelation.com

---

© 2025 Intelation — Privacy-first data transformation at scale.
