# Spark Minda AI Policy Assistant — Vercel Deployment Guide

## What's in this folder

```
sparkminda-deploy/
├── index.html        ← The full chatbot frontend
├── api/
│   └── chat.js       ← Secure serverless proxy (hides your API key)
├── vercel.json       ← Vercel routing config
└── README.md         ← This file
```

---

## Deploy in 5 minutes (Free)

### Step 1 — Create a free Vercel account
Go to https://vercel.com and sign up (free tier is sufficient).

### Step 2 — Upload this project

**Option A — Drag & Drop (easiest)**
1. Go to https://vercel.com/new
2. Click "Browse" and upload this entire folder (zip it first if needed)
3. Click "Deploy"

**Option B — GitHub (recommended for updates)**
1. Create a new GitHub repository
2. Upload all files from this folder
3. Go to https://vercel.com/new → Import from GitHub
4. Select your repository → Deploy

### Step 3 — Add your Anthropic API Key (secret)
After deploying:
1. Go to your project on Vercel dashboard
2. Click **Settings → Environment Variables**
3. Add a new variable:
   - **Name:** `ANTHROPIC_API_KEY`
   - **Value:** `sk-ant-api03-your-key-here`
   - **Environment:** Production, Preview, Development (check all)
4. Click **Save**
5. Go to **Deployments → Redeploy** (required for env vars to take effect)

### Step 4 — Share the link!
Vercel gives you a URL like:
```
https://sparkminda-policy.vercel.app
```
Share this with all Spark Minda employees. No login, no API key needed on their end.

---

## Get your Anthropic API Key
1. Go to https://console.anthropic.com
2. Sign up / Log in
3. Click **API Keys → Create Key**
4. Copy the key (starts with `sk-ant-`)

---

## Optional: Custom Domain
In Vercel → Settings → Domains, you can add your own domain like:
```
hr-assistant.sparkminda.com
```

---

## Security Notes
- The API key is stored as a Vercel Environment Variable — it never appears in the frontend code
- PDF documents are processed in the employee's browser only — they are NOT stored anywhere
- Only your Vercel proxy can access the Anthropic API

---

## Cost Estimate
- Vercel hosting: **Free** (Hobby plan)
- Anthropic API: ~$0.003 per question (Claude Sonnet pricing)
- 1,000 employee questions/month ≈ **$3–5/month**
