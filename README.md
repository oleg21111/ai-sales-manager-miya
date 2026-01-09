# "Miya": An AI Sales Manager for a Visa Center

**"Miya"** is an AI-powered sales manager, built on `n8n`, designed to fully automate the initial communication with clients for a visa center via Telegram or a web chat.

The agent is capable of conducting natural conversations, answering questions about visas, handling objections, offering services, accepting documents, and notifying a human manager about "hot" leads that require immediate attention.

---

## 🔧 Tech Architecture

-   **Platform:** `n8n`
-   **Integrations:**
    -   ✅ **OpenAI API:** For natural language processing (NLP) and user intent classification.
    -   ✅ **Airtable:** Serves as the knowledge base (FAQs, objection handling scripts, dialogue scenarios, visa types).
    -   ✅ **Telegram API:** The primary communication channel with users.
    -   ✅ **Internal CRM (Airtable):** For session history and conversation logging.

---

## 🧩 Core Logic

1.  **Dialogue Initiation:** A user sends a message. The system identifies the platform, user, and language.
2.  **Intent Classification:** OpenAI analyzes the text to determine the user's intent (e.g., `GET_VISA_INFO`, `ANSWER_FAQ`, `HANDLE_OBJECTION`).
3.  **Knowledge Retrieval:** The system queries the Airtable knowledge base to find the relevant information (visa details, required documents, etc.).
4.  **Response Generation:** A response is formulated in the user's language (UA/RU/EN) with an adapted tone of voice.
5.  **Trigger System:** If a client shows purchase intent, asks for an expert, or asks a non-standard question, "Miya" automatically sends a notification to a human manager in Telegram with all the client's details and a priority tag:
    -   💰 **Ready to Buy:** High priority
    -   👨‍🎓 **Expert Requested:** Urgent contact
    -   ❓ **Unknown Question:** Requires manual response
6.  **Session Logging:** Every interaction is logged in the CRM, creating a complete history of the dialogue.

---

## 💼 Business Impact

-  ✔️ **Automates up to 80%** of initial client consultations.
-  ✔️ **Reduces manager workload by 15-20 hours per week**, freeing them up for closing deals.
-  ✔️ **Increases response speed** to inquiries, with instant notifications for hot leads.
-  ✔️ **Standardizes answers** across three languages, ensuring consistent communication.

## 💬 Key Capabilities

-   🗂 Providing detailed information on various visa types.
-   🧾 Generating lists of required documents.
-   💬 Handling common objections ("it's too expensive," "I'll think about it").
-   📞 Escalating "hot" leads to a human manager for follow-up.
-   💡 Supporting users in multiple languages.
-   🔔 Sending automated, detailed notifications to managers in Telegram.
