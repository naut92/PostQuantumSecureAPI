# 🔐 Post-Quantum Secure Messaging API

This is a demo REST API built with Java and Spring Boot, showcasing a basic design of how post-quantum encryption could be integrated into secure services (e.g., financial or telecom systems).

> ⚠️ The current implementation uses a stub in place of real post-quantum cryptography (Kyber, Dilithium). Future versions may integrate a real post-quantum algorithm using libraries like [Open Quantum Safe](https://openquantumsafe.org/).

---


## 🧩 Key Features
•	✅ Post-Quantum Cryptography Integration
Integrated a post-quantum cryptographic library (e.g., via wrapper around Bouncy Castle) to support algorithms like Kyber, NTRU, and Dilithium.
•	📡 Secure Messaging API
REST API for securely sending and retrieving encrypted messages between clients.
•	🔐 End-to-End Encryption
Ensures that only intended recipients can decrypt messages. Includes post-quantum key exchange support.
•	🧪 Comprehensive Testing
Includes unit and integration tests for:
•	Encryption/decryption logic
•	Key generation and exchange
•	REST API for encrypting and decrypting payloads

---

## 🛠️ Tech Stack

🚀 Stack
•	Java 17 / Spring Boot
•	PostgreSQL
•	Bouncy Castle PQC (custom wrapper)
•	Docker + Docker Compose
•	JUnit / Mockito
---

## 📂 Endpoints

### POST `/encrypt`
**Request:**

```json
{
  "data": "Hello, PQ world!"
}
```

**Response:**
```json
{
  "encrypted": "ENC[Base64-string]"
}
```

### POST `/decrypt`

**Response:**
```json
{
  "decrypted": "Hello, PQ world!"
}
```

curl -X POST http://localhost:8081/api/messages/encrypt -H "Content-Type: text/plain" -d "hello world"

### ▶️ Local Dev Setup

```bash
# Start database
docker-compose up -d
```

# Run tests
./gradlew test
