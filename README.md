# 🗺️ Route Optimizer

AI-powered delivery & logistics routing. Upload a file of addresses, set a starting point, and get the most efficient route instantly.

## Deploy to Netlify via GitHub

### 1. Push to GitHub
Upload all files in this folder to a new GitHub repository.

### 2. Connect to Netlify
1. Go to [netlify.com](https://netlify.com) and log in
2. Click **"Add new site" → "Import an existing project"**
3. Choose **GitHub** and select your repository
4. Build settings are auto-detected from `netlify.toml` — no changes needed
5. Click **"Deploy site"**

### 3. Add your Anthropic API key
1. In Netlify, go to **Site configuration → Environment variables**
2. Click **"Add a variable"**
3. Set:
   - **Key:** `ANTHROPIC_API_KEY`
   - **Value:** your key from [console.anthropic.com](https://console.anthropic.com)
4. Click **Save**, then **Trigger a redeploy**

That's it — your site is live! 🎉

## Project Structure

```
route-optimizer/
├── index.html                  # The app
├── netlify.toml                # Netlify config
├── netlify/
│   └── functions/
│       └── claude.js           # Serverless API proxy (keeps your key secret)
└── README.md
```

## How it works

The app calls `/api/claude` (a Netlify serverless function) instead of the Anthropic API directly. This keeps your API key secret — it lives only in Netlify's environment variables, never in the browser.
