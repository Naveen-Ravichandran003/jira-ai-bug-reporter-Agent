# 🚀 Deployment Guide

Follow these steps to host your BugPilot AI Agent on the cloud using GitHub and Vercel.

---

## 1. Push to GitHub

If you've made changes locally and want to push them to your repository:

1.  **Open Terminal** in the project folder.
2.  **Add all changes**:
    ```bash
    git add .
    ```
3.  **Commit your changes**:
    ```bash
    git commit -m "Your message here"
    ```
4.  **Push to GitHub**:
    ```bash
    git push origin main
    ```

---

## 2. Host on Vercel

Vercel is the best place to host this FastAPI + Vanilla JS application.

### Step A: Connect Repository
1.  Go to the [Vercel Dashboard](https://vercel.com/dashboard).
2.  Click **"Add New"** > **"Project"**.
3.  Search for your repository `jira-ai-bug-reporter-Agent` and click **"Import"**.

### Step B: Configure Environment Variables
Before clicking "Deploy", you must add your keys so the app can talk to Groq and JIRA.

1.  Find the **"Environment Variables"** section.
2.  Add the following **Keys** and their **Values**:
    - `GROQ_API_KEY`: (Your Groq API Key)
    - `JIRA_URL`: (e.g., `https://yourname.atlassian.net`)
    - `JIRA_EMAIL`: (Your JIRA login email)
    - `JIRA_API_TOKEN`: (Your JIRA API Token)
    - `JIRA_PROJECT`: (Your JIRA Project Key, e.g., `KAN`)

### Step C: Deploy
1.  Click **"Deploy"**.
2.  Once finished, Vercel will give you a public URL (e.g., `bugpilot-ai.vercel.app`).

---

## 🔑 Multi-User Usage (Important)

Because this app uses **Local Storage** for passwords and keys:
- **For You**: Your keys stay in your browser. You can use the Vercel URL privately.
- **For Teammates/Clients**: Send them your Vercel URL. They will see the app, but they will need to go to the **Settings** tab and enter their own credentials once. This ensures everyone's data stays separate and secure!

> [!TIP]
> If you want to provide a **default** Groq key for everyone, make sure it is added in the Vercel Environment Variables. The app will use that key if the user doesn't provide their own.

---

## 🛠️ Troubleshooting
- **API Errors**: Ensure your `JIRA_URL` includes `https://`.
- **White Screen**: Check the browser console (F12) for errors.
- **Vercel Build Failure**: Ensure `api/index.py` and `vercel.json` are in the root directory.
