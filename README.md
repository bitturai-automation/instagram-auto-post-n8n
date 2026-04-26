# 📸 Instagram Full Auto Post Workflow (n8n)

An n8n automation workflow that **automatically generates and posts Instagram content daily** using AI — no manual effort needed!

## 🔄 How It Works

```
Daily Trigger (9 AM)
    ↓
Read Google Sheet (post ideas/topics)
    ↓
Split into batches (1 at a time)
    ↓
Generate Caption + Hashtags + Visual Idea (Groq AI / LLaMA 3.3)
    ↓
Parse AI Response (JSON)
    ↓
Generate Image (Pollinations AI — 1080×1080)
    ↓
Wait (image generation delay)
    ↓
Upload to Instagram (Facebook Graph API)
    ↓
Wait (processing delay)
    ↓
Publish Post ✅
```

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| [n8n](https://n8n.io) | Workflow automation |
| [Groq API](https://groq.com) | AI caption & hashtag generation (LLaMA 3.3 70B) |
| [Pollinations AI](https://pollinations.ai) | Free AI image generation |
| Google Sheets | Content idea storage |
| Facebook Graph API | Instagram post publishing |

## 📋 Prerequisites

1. **n8n** installed (self-hosted or cloud)
2. **Groq API Key** — free at [console.groq.com](https://console.groq.com)
3. **Google Sheets** with your content ideas
4. **Instagram Business Account** connected to a Facebook Page
5. **Facebook Graph API Access Token** (from [Meta Developer Console](https://developers.facebook.com))

## 🚀 Setup Instructions

### Step 1 — Import Workflow
- Download `Instagram_Full_Auto_post_Workflow_PUBLIC.json`
- Open n8n → **Import from File**
- Paste the JSON

### Step 2 — Add Your Credentials

Replace all placeholder values in the workflow:

| Placeholder | What to Replace With |
|-------------|----------------------|
| `YOUR_GROQ_API_KEY_HERE` | Your Groq API key |
| `YOUR_GOOGLE_SHEET_URL_HERE` | Your Google Sheet URL |
| `YOUR_INSTAGRAM_BUSINESS_ACCOUNT_ID` | Your IG Business Account ID |
| `YOUR_INSTAGRAM_ACCESS_TOKEN_HERE` | Your long-lived Facebook/Instagram access token |
| `YOUR_GOOGLE_SHEETS_CREDENTIAL_ID` | Set up Google Sheets OAuth in n8n credentials |

### Step 3 — Set Up Google Sheets
Create a sheet with columns like:
- `Topic` / `Niche` / `Post Idea`

The workflow reads one row per run.

### Step 4 — Activate
Toggle the workflow to **Active** — it will run daily at 9:00 AM.

## ⚠️ Important Security Notes

- **Never share your actual API keys or access tokens publicly**
- Instagram access tokens expire — regenerate them periodically
- Store credentials in n8n's built-in credential manager, not hardcoded in nodes

## 📁 Files

```
├── Instagram_Full_Auto_post_Workflow_PUBLIC.json   ← Import this into n8n
└── README.md
```

## 🤝 Contributing

Feel free to fork, improve, and raise PRs! Ideas welcome:
- Add video/reel support
- Multi-account posting
- Auto-scheduling based on best engagement times

## 📬 Connect

Built by Bittu Rai — feel free to connect on [LinkedIn](https://www.linkedin.com/in/bitturai/)!

---

⭐ If this helped you, please star the repo!
<img width="800" height="404" alt="1777222625561" src="https://github.com/user-attachments/assets/d4389d64-c309-4d0e-b13a-a7b170d708c7" />
