# ⚡ n8n Automation Workflows by Gaurav Gocher

A collection of production-ready n8n automation workflows built with Groq AI, GitHub, Telegram, Gmail, and more.

---

## 📁 Workflows

### 1. 📝 Daily Notes to Git
**File:** `Daily_notes_to_git.json`

Automatically generates developer learning notes using Groq AI (LLaMA 3.3 70B) and commits them to this GitHub repository — 3 times a day.

| Detail | Info |
|--------|------|
| Trigger | Schedule — 08:00, 14:00, 20:00 daily |
| AI Model | Groq LLaMA 3.3 70B |
| Output | `.md` files committed to GitHub |
| Notification | Telegram message after each commit |

**How it works:**
- Morning → Generates a "what I learned" note with code examples
- Afternoon → Generates a "what I built/debugged" note
- Evening → Generates an end-of-day reflection note
- Each note is formatted as Markdown and committed to `notes/YYYY/MM/` folder

---

### 2. ✍️ AI Blog Generator (Groq + Gmail)
**File:** `AI_Blog_Generator__Groq___Gmail_.json`

Takes a blog topic from a web form and generates a full, structured blog post — then emails it directly to the user.

| Detail | Info |
|--------|------|
| Trigger | n8n Form (web) |
| AI Model | Groq LLaMA 3.3 70B |
| Output | HTML blog post sent via Gmail |

**How it works:**
1. User fills a form: topic, target audience, tone, email
2. Step 1 → AI generates a 4-section blog outline
3. Step 2 → AI writes the full blog post in HTML (150-200 words per section)
4. Step 3 → AI generates a catchy title
5. Final blog is emailed to the user with a styled HTML template

---

### 3. 📄 AI Resume Analyser
**File:** `AI_Resume_Analyser.json`

Accepts a resume PDF via a Tally form, analyzes it with Groq AI, and sends a detailed report to the candidate's email.

| Detail | Info |
|--------|------|
| Trigger | Tally Form webhook (POST) |
| AI Model | Groq LLaMA 3.3 70B |
| Output | Email report via Gmail |

**How it works:**
1. Candidate submits name, email, and resume PDF via Tally
2. PDF is downloaded and text is extracted
3. Groq AI analyzes: skills, experience, strengths, improvements, score
4. Score label assigned: 🟢 Strong / 🟡 Good / 🔴 Needs Improvement
5. Detailed HTML report sent to candidate's email

---

### 4. 📱 AI SMS Appointment Setter (Twilio + Groq)
**File:** `AI_SMS_Appointment_Setter_-_Twilio___Groq_v2.json`

An AI sales agent that qualifies leads over WhatsApp/SMS and books strategy calls automatically.

| Detail | Info |
|--------|------|
| Trigger | Twilio Webhook (incoming SMS/WhatsApp) |
| AI Model | Groq LLaMA 3.3 70B |
| Output | WhatsApp replies + Calendly booking link |
| Memory | Conversation memory per contact |

**How it works:**
- AI agent acts as "Michael" from NexaAI Solutions
- Follows a strict qualification flow: business type → revenue → budget → pain point
- Qualified leads (revenue $10k+, budget $5k+) get the Calendly booking link
- Handles objections, follows up once if no reply
- Supports Hindi/Hinglish naturally

---

### 5. 🤖 AI LinkedIn Post Humanizer
**File:** `AI_huamnizer_Linkedin_Post.json`

Generates viral LinkedIn posts from a Telegram message, humanizes them with AI, gets approval, and posts directly to LinkedIn.

| Detail | Info |
|--------|------|
| Trigger | Telegram message |
| AI Model | NVIDIA LLaMA 3 70B |
| Output | Posted to LinkedIn |

**How it works:**
1. Send a topic to Telegram bot
2. NVIDIA AI generates a viral LinkedIn post
3. Second AI pass humanizes it (removes AI-sounding phrases)
4. Post sent to Telegram for approval (accept/decline/feedback)
5. If accepted → posted to LinkedIn via API
6. If feedback given → revised and sent for re-approval

---

### 6. ☕ Foodrins Cafe Chatbot
**File:** `Foodrins_Cafe_v2.json`

A full food ordering chatbot for Foodrins Cafe — handles menu queries, order placement, order status, and FAQs via Telegram.

| Detail | Info |
|--------|------|
| Trigger | Telegram message |
| AI Model | Groq LLaMA 3.3 70B |
| Data | Google Sheets (menu, orders, FAQ) |
| Output | Telegram replies |

**How it works:**
- Customer messages the Telegram bot
- AI agent checks Google Sheets for live inventory before showing menu
- Takes order → checks stock → saves to Google Sheets Orders tab
- Handles: menu view, order placement, order status, FAQs, cancellation info
- Remembers conversation context per customer (10 message window)

---

### 7. 📑 PDF Summarizer
**File:** `pdf_summarizer.json`

Accepts any PDF via a Tally form, extracts and summarizes it with AI, and emails a structured summary report.

| Detail | Info |
|--------|------|
| Trigger | Tally Form webhook (POST) |
| AI Model | Groq LLaMA 3.3 70B |
| Output | Email summary via Gmail |

**How it works:**
1. User submits name, email, and PDF via Tally form
2. PDF downloaded and text extracted
3. Groq AI analyzes and returns: title, summary, key points, action items, document type
4. Styled HTML email report sent to user

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| [n8n](https://n8n.io) | Workflow automation |
| [Groq](https://groq.com) | Fast AI inference (LLaMA 3.3 70B) |
| [NVIDIA NIM](https://build.nvidia.com) | AI for LinkedIn workflow |
| GitHub API | Auto-commit daily notes |
| Telegram Bot API | Notifications & chatbot |
| Gmail OAuth2 | Send email reports |
| Twilio | WhatsApp/SMS messaging |
| Google Sheets | Live data for cafe chatbot |
| Tally | Form submissions (resume & PDF) |
| LinkedIn API | Auto-posting |

---

## 🚀 Setup

1. Import any `.json` file into your n8n instance via **Import from file**
2. Add your credentials (Groq API, GitHub OAuth2, Gmail OAuth2, Telegram Bot, etc.)
3. Activate the workflow

---

## 📬 Contact

**Gaurav Gujjar**
- GitHub: [@gaurav712-gujjar](https://github.com/gaurav712-gujjar)
- Email: gujjargaurav712@gmail.com

---

*Built with ❤️ using n8n + Groq AI*
