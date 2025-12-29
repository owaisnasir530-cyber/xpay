# 🚀 Deploy to Vercel - Step by Step

## ✅ Your Project is Ready!

Your Next.js ChatKit app is already configured with:
- ✅ API Key in `.env.local`
- ✅ Workflow ID: `wf_690b8c28da6481908e19761210a3a3f70cb4efc55864e3c7`
- ✅ Next.js 15 with ChatKit React
- ✅ Edge runtime for fast performance
- ✅ Professional UI with theme support

---

## 🎯 Method 1: Vercel Dashboard (EASIEST)

### Step 1: Prepare Your Project

1. **Zip the project folder** (the "ivo integration" folder)
2. Or push to GitHub (recommended for easier updates)

### Step 2: Deploy

#### Option A: Upload ZIP
1. Go to https://vercel.com/new
2. Click "Browse" or drag & drop your ZIP
3. Vercel auto-detects Next.js

#### Option B: Connect GitHub (Recommended)
1. Push project to GitHub
2. Go to https://vercel.com/new
3. Import your repository
4. Vercel auto-detects Next.js

### Step 3: Configure Environment Variables

**CRITICAL**: Add these in Vercel dashboard:

1. Click "Environment Variables"
2. Add:
   - **Name**: `OPENAI_API_KEY`
   - **Value**: `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`
   - **Environments**: Select all (Production, Preview, Development)

3. Add:
   - **Name**: `NEXT_PUBLIC_CHATKIT_WORKFLOW_ID`
   - **Value**: `wf_690b8c28da6481908e19761210a3a3f70cb4efc55864e3c7`
   - **Environments**: Select all

### Step 4: Deploy

1. Click **"Deploy"**
2. Wait 2-3 minutes
3. You'll get a URL like: `https://ivo-integration.vercel.app`

### Step 5: Verify Domain

**IMPORTANT**: ChatKit requires domain verification!

1. Go to https://platform.openai.com/settings/organization/security/domain-allowlist
2. Add your Vercel domain: `ivo-integration.vercel.app`
3. Click "Verify" (verification is instant)
4. Refresh your deployed site

**Without domain verification, ChatKit will show 401 errors!**

---

## 🎯 Method 2: Vercel CLI

### Step 1: Install CLI

```bash
npm install -g vercel
```

### Step 2: Login

```bash
vercel login
```

### Step 3: Deploy

```bash
cd "ivo integration"
vercel
```

Follow prompts:
- **Set up and deploy?** Y
- **Which scope?** Select your account
- **Link to existing project?** N
- **Project name?** `ivo-chatkit` (or your choice)
- **Directory?** `.` (current)
- **Override settings?** N

### Step 4: Add Environment Variables

```bash
vercel env add OPENAI_API_KEY
# Paste your API key when prompted
# Select all environments

vercel env add NEXT_PUBLIC_CHATKIT_WORKFLOW_ID
# Paste your workflow ID when prompted
# Select all environments
```

### Step 5: Redeploy

```bash
vercel --prod
```

### Step 6: Verify Domain (Same as Method 1, Step 5)

---

## 🌐 Embed in Your Zenbox Website

Once deployed and domain verified, add to your PHP site:

```php
<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Czat z IVO - Wirtualny Doradca Spadkowy</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
            background: #f5f5f5;
        }
        .page-wrapper {
            max-width: 1600px;
            margin: 0 auto;
            padding: 20px;
        }
        h1 {
            text-align: center;
            color: #1e355d;
            margin-bottom: 30px;
            font-size: 2.5rem;
        }
        .chat-container {
            position: relative;
            width: 100%;
            height: 90vh;
            min-height: 600px;
            border-radius: 16px;
            overflow: hidden;
            box-shadow: 0 10px 40px rgba(0,0,0,0.15);
        }
        .chat-iframe {
            width: 100%;
            height: 100%;
            border: none;
        }
        @media (max-width: 768px) {
            h1 {
                font-size: 1.8rem;
            }
            .chat-container {
                height: 85vh;
                border-radius: 0;
            }
        }
    </style>
</head>
<body>
    <div class="page-wrapper">
        <h1>🤖 IVO - Wirtualny Doradca Spadkowy</h1>
        
        <div class="chat-container">
            <!-- REPLACE WITH YOUR VERCEL URL -->
            <iframe 
                src="https://YOUR-APP.vercel.app" 
                class="chat-iframe"
                title="IVO Chat - Wirtualny Doradca Spadkowy"
                allow="clipboard-write"
                loading="eager"
            ></iframe>
        </div>
    </div>
</body>
</html>
```

**Replace `YOUR-APP.vercel.app` with your actual Vercel URL!**

---

## 🔧 Troubleshooting

### Issue: 401 Unauthorized Errors

**Cause**: Domain not verified in OpenAI

**Solution**:
1. Go to https://platform.openai.com/settings/organization/security/domain-allowlist
2. Add your Vercel domain (e.g., `ivo-integration.vercel.app`)
3. Click "Verify"
4. Refresh your site

### Issue: Build Fails

**Check**:
- Environment variables added correctly?
- API key has no extra spaces?
- Workflow ID is correct?

**Solution**: Check Vercel build logs for specific error

### Issue: Chat Widget Doesn't Load

**Possible Causes**:
1. Domain not verified → See 401 fix above
2. API key invalid → Generate new one
3. Workflow not published → Publish in Agent Builder

**Debug**:
- Open browser console (F12)
- Check Network tab for errors
- Look for specific error messages

### Issue: "Missing OPENAI_API_KEY"

**Solution**: Environment variables not set

1. Go to Vercel dashboard
2. Project Settings → Environment Variables
3. Add both variables
4. Redeploy (Deployments → click "..." → Redeploy)

---

## ✅ Success Checklist

- [ ] Vercel account created
- [ ] Project deployed to Vercel
- [ ] Got deployment URL (e.g., https://ivo-integration.vercel.app)
- [ ] Environment variables added in Vercel
- [ ] Domain verified in OpenAI settings
- [ ] Opened URL - ChatKit loads
- [ ] Sent test message - got response
- [ ] Embedded in Zenbox PHP site
- [ ] Works from Zenbox site

---

## 📊 What You Get

Once deployed:
- ✅ Professional ChatKit interface
- ✅ Connected to your Agent Builder workflow
- ✅ Auto-sync - changes in Agent Builder appear instantly
- ✅ File upload support (PDF, DOCX)
- ✅ Message history preserved
- ✅ Theme switcher (light/dark mode)
- ✅ Mobile responsive
- ✅ FREE hosting on Vercel
- ✅ Fast edge runtime
- ✅ SSL/HTTPS included
- ✅ Custom domain support (if you want)

---

## 🎉 You're Ready!

The app is **production-ready** and **needs no code changes**.

Just:
1. Deploy to Vercel
2. Add environment variables
3. Verify domain in OpenAI
4. Embed in your website

**That's it!**
