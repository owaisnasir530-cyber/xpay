# ⚡ Quick Start - IVO ChatKit

## 🎯 What This Is

A production-ready Next.js app with ChatKit that connects to your Agent Builder workflow.

**Already configured with:**
- ✅ Your API key
- ✅ Your workflow ID
- ✅ Professional UI
- ✅ Theme switcher
- ✅ Edge runtime

---

## 🚀 Deploy in 5 Minutes

### Step 1: Go to Vercel
https://vercel.com/new

### Step 2: Upload This Folder
Drag & drop the entire project folder

### Step 3: Add Environment Variables

**CRITICAL - Add these 2 variables:**

1. `OPENAI_API_KEY` = `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`

2. `NEXT_PUBLIC_CHATKIT_WORKFLOW_ID` = `wf_690b8c28da6481908e19761210a3a3f70cb4efc55864e3c7`

### Step 4: Deploy
Click "Deploy" and wait 2-3 minutes

### Step 5: Verify Domain
**MOST IMPORTANT STEP - Don't skip!**

1. Go to https://platform.openai.com/settings/organization/security/domain-allowlist
2. Add your Vercel URL (e.g., `ivo-integration.vercel.app`)
3. Click "Verify"

**Without this, you'll get 401 errors!**

---

## 🌐 Embed in Your Website

```html
<iframe 
    src="https://YOUR-APP.vercel.app" 
    width="100%" 
    height="800px" 
    style="border: none; border-radius: 16px;"
></iframe>
```

---

## 📚 Full Documentation

See **VERCEL-DEPLOY.md** for complete instructions, troubleshooting, and advanced options.

---

## ✅ That's It!

Your ChatKit is ready to deploy. No code changes needed.
