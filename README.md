🚀 AI Support Assistant (Hybrid Chatbot System)

A production-ready AI chatbot combining structured knowledge (FAQ) with generative AI for reliable, scalable customer support.

   

---
📌 Overview

This project is an AI-powered customer support chatbot designed to solve a real-world limitation:

«❗ Traditional chatbots are either:»

Static (FAQ-based → limited)
Fully AI-based (→ inaccurate / hallucination)
✅ Solution

This system implements a Hybrid Intelligence Model:

⚡ FAQ-first approach → Accurate & fast answers
🤖 AI fallback (Ollama) → Handles unknown queries
🎯 Controlled responses → Reduces hallucination
🧠 Key Features

🔹 Intelligent Response Engine

FAQ matching using normalized input
AI fallback for unmatched queries
Prompt-controlled responses (2–3 lines max)
🔹 Real-Time Chat Experience

Smooth UI with typing animation
Clean dark/light theme toggle
Mobile responsive design
🔹 Session-Based Architecture

Multiple chat sessions
Session switching (like ChatGPT)
Persistent conversation history
🔹 Production-Level Backend

Layered architecture (Controller → Service → Repository)
REST API design
Error handling & validation
🔹 Database Integration

PostgreSQL for persistent storage
Stores:
Chat history
FAQ knowledge base
🔹 PDF Export System

Export full conversation
Clean formatted output
Real-world feature (customer support logs)
🔹 Security

JWT-based authentication
Protected API endpoints
⚙️ Tech Stack

Backend

Java + Spring Boot
Spring Data JPA
REST APIs
AI Engine

Ollama (Local LLM - TinyLlama)
Frontend

HTML, CSS, JavaScript
Database

PostgreSQL
🏗️ System Architecture (Visualized)

               ┌──────────────────────────┐
               │        🧑 User            │
               └────────────┬─────────────┘
                            │
                            ▼
               ┌──────────────────────────┐
               │     🌐 Frontend UI       │
               │  (HTML, CSS, JS Chat)   │
               └────────────┬─────────────┘
                            │ HTTP Request
                            ▼
               ┌──────────────────────────┐
               │   ⚙️ Spring Boot API     │
               │      (Controller)        │
               └────────────┬─────────────┘
                            │
                            ▼
               ┌──────────────────────────┐
               │     🧠 Service Layer     │
               │ (Core Business Logic)    │
               └────────────┬─────────────┘
                            │
            ┌───────────────┼───────────────┐
            ▼                               ▼
┌──────────────────────┐         ┌────────────────────────┐
│     📚 FAQ Engine     │         │     🤖 AI Engine        │
│ (Database Matching)  │         │   (Ollama - LLM)        │
└──────────┬───────────┘         └──────────┬─────────────┘
           │ YES MATCH                     │ NO MATCH
           ▼                               ▼
    ┌──────────────────────────┐   ┌──────────────────────────┐
    │   Return FAQ Response     │   │   Generate AI Response    │
    └────────────┬─────────────┘   └────────────┬─────────────┘
                 │                               │
                 └───────────────┬───────────────┘
                                 ▼
               ┌──────────────────────────┐
               │     🗄️ PostgreSQL DB      │
               │ (Chat + FAQ Storage)     │
               └────────────┬─────────────┘
                            │
                            ▼
               ┌──────────────────────────┐
               │   📤 Send Response to UI  │
               └──────────────────────────┘
🔍 Flow Explanation

User sends a message from the UI
Request goes to Spring Boot backend
Service layer processes the logic
System first checks FAQ database
If match found → returns instantly
Else → forwards to AI model (Ollama)
Response is stored in PostgreSQL
Final output is sent back to user
⚡ Hybrid Flow = Fast (FAQ) + Smart (AI)

🔄 Workflow

User submits a query
Input is cleaned (normalization)
System searches FAQ database
If match → return instantly
Else → send to AI model
AI response generated
Response saved in DB
Displayed in UI
📂 Database Schema

"chat_message"

Field| Description id| Primary key username| User identifier session_id| Chat session user_message| Input message bot_reply| AI/FAQ response

"faq"

Field| Description id| Primary key question| Stored question answer| Predefined answer

📸 UI Preview

«Add screenshots here»

Chat Interface
Session Sidebar
PDF Export
🚀 Installation & Setup

1️⃣ Clone Repository

git clone https://github.com/your-username/ai-support-assistant.git cd ai-support-assistant

2️⃣ Configure PostgreSQL

spring.datasource.url=jdbc:postgresql://localhost:5432/chatbot spring.datasource.username=your_username spring.datasource.password=your_password spring.jpa.hibernate.ddl-auto=update

3️⃣ Start AI Model

ollama run tinyllama

4️⃣ Run Backend

mvn spring-boot:run

5️⃣ Open Application

http://localhost:8080/index.html

🎯 Why This Project Stands Out

✔ Hybrid AI + Rule-based system ✔ Reduces hallucination (FAQ-first) ✔ Optimized AI usage (cost-efficient) ✔ Real-world features (sessions, PDF export) ✔ Scalable backend design

📈 Future Enhancements

🔍 Semantic search using embeddings
🌍 Multi-language support
🎤 Voice assistant integration
📊 Admin dashboard with analytics
☁️ Cloud deployment (AWS/GCP)
👨‍💻 Author

Ganesh Kumar Sardar 📧 ganeshsardar2004@gmail.com

⭐ Support

If you find this project useful, give it a ⭐ on GitHub!

“Not just an AI chatbot — a production-ready intelligent support system.”
