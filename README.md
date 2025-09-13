## Features

* Generate contextual email replies using GPT
* Choose tones: **Professional**, **Friendly**, or **Brief**
* Understands original email context
* Works seamlessly inside Gmail compose
* Instant response generation
* Copy or insert with one click

---

## Tech Stack

* **Frontend:** JavaScript, Chrome Extension API, CSS
* **Backend:** Python, FastAPI, OpenAI API, Uvicorn, Pydantic

---

## Quick Start

### Prerequisites

* Python 3.8+
* Chrome browser
* OpenAI API key

### Setup

**1. Clone repository**

```bash
git clone https://github.com/omjambhale/GMAIL-AI-ASSISTANT.git
cd GMAIL-AI-ASSISTANT
```

**2. Start backend**

```bash
cd backend
pip install -r requirements.txt
cp .env.example .env  # add your API key
python main.py
```

**3. Load Chrome extension**

* Open `chrome://extensions/`
* Enable *Developer mode*
* Click **Load unpacked** → select `extension/`

**4. Use inside Gmail**

* Open Gmail
* Click **AI Assistant** in compose/reply
* Enter context + choose tone → generate reply

---

## Project Structure

```
GMAIL-AI-ASSISTANT/
├── backend/          # FastAPI backend
│   ├── main.py
│   └── requirements.txt
├── extension/        # Chrome extension
│   ├── manifest.json
│   ├── background.js
│   ├── content.js
│   └── styles.css
└── README.md
```

---

## Configuration

Create `.env` inside `backend/`:

```env
OPENAI_API_KEY=your_openai_api_key_here
```

**API Endpoints**

* `GET /` → Health check
* `POST /api/generate-reply`

```json
{
  "email_content": "Original email",
  "user_context": "Your message",
  "tone": "professional|friendly|brief"
}
```

---

## Example Use Cases

* **Professional** → “Thank them for the meeting, confirm Tuesday 2pm”
* **Friendly** → “Ask about vacation, share funny story”
* **Brief** → “Confirm receipt of documents”

---

## Troubleshooting

* Extension not visible → Check backend running on `:8001`
* Failed reply → Verify API key + credits
* Backend issues → `curl http://localhost:8001/`


