
---

## ✅ **AI Agent Workshop – System Flow Diagram**

```plaintext
                           ┌─────────────────────────────┐
                           │     Chat Message Trigger     │
                           │     (n8n Webhook/Input)      │
                           └────────────┬────────────────┘
                                        │
                                        ▼
                           ┌─────────────────────────────┐
                           │         AI Agent Node        │
                           │     (Chat + Tool Control)     │
                           └─────┬──────────────┬─────────┘
                                 │              │
        ┌────────────────────────┘              └────────────────────────┐
        ▼                                                           ▼
┌────────────────────┐                                 ┌───────────────────────────────┐
│ Memory / Context    │                                 │   External API Call Tools     │
│ (e.g., SimpleMemory)│                                 │  (Dynamic GET/POST workflows) │
└─────────┬───────────┘                                 └──────┬──────────────┬─────────┘
          │                                                          │              │
          ▼                                                          ▼              ▼
 ┌────────────────────┐                                  ┌────────────────┐ ┌──────────────────┐
 │ Coordinates Lookup │                                  │ Weather API    │ │ WhatsApp Webhook │
 │ (e.g., get_city)   │                                  │ (Open-Meteo)   │ │ (incoming msg)   │
 └────────────────────┘                                  └────────────────┘ └──────────────────┘

                    ┌───────────────────────────────┐
                    │     Google Gemini / GPT       │
                    │     (NLP & Response Gen)       │
                    └───────────────────────────────┘
```

---

### 🔍 Breakdown by Workflow

#### 📍 `1.Your-First-AI-Agent`

* Trigger: Chat message
* Agent: GPT/Gemini
* Tools:

  * `get_coordinates` → city to lat/lon
  * `get_weather` → fetch real-time weather

#### 💬 `2-whatsapp-gpt-n8n-agent`

* Trigger: Webhook (from WhatsApp API)
* Agent: GPT or Gemini
* Tools: None (direct text-to-response)

#### 📄 `3-Resume-Screener`

* Trigger: Resume file input or prompt
* Agent: GPT
* Tool: GPT prompt → structured resume insights

---
