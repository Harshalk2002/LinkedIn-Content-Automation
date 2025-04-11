
# n8n LinkedIn Content Automation Workflow

## Description
This is an end-to-end automation workflow for **LinkedIn content generation** using **OpenAI** (GPT-4) and posting to LinkedIn. It:
1. **Fetches trending AI/data content** from multiple RSS sources.
2. **Summarizes and rewrites the content** using OpenAI (GPT-4).
3. **Sends a review email** to ensure posts are approved before publishing.
4. **Stores posts in Google Sheets** and posts to LinkedIn once approved.

---

## Features
- Fetches content from:
  - TechCrunch
  - Analytics Vidhya
  - Machine Learning Mastery
- Uses OpenAI GPT-4 to summarize and rewrite articles.
- Sends drafts to **Gmail** for approval before posting.
- Saves approved posts in **Google Sheets**.
- Automatically posts approved content to LinkedIn.

---

## Setup Instructions

### Prerequisites:
- **n8n account** (self-hosted or n8n.cloud)
- **LinkedIn API credentials** for OAuth-based access to post on LinkedIn
- **OpenAI API credentials** for GPT-4 access
- **Google Sheets credentials** for saving approved posts

### Steps to Setup:
1. **Clone/Import the Workflow**:
   - Import the provided workflow JSON file into your n8n instance.
   
2. **Set Up Google Sheets**:
   - Create a Google Sheet with columns: `index`, `message`, `Approved`, `Posted`.
   - **Link your Google Sheets** credentials in n8n.

3. **Link LinkedIn API**:
   - In n8n, connect your **LinkedIn credentials** via OAuth to allow posting to LinkedIn.
   
4. **Link OpenAI API**:
   - Obtain your OpenAI **API key** and set up the **OpenAI node** in n8n.

5. **Email Setup (Optional)**:
   - Configure your **Gmail or SMTP node** to send emails for review before posting.

6. **Cron Scheduler**:
   - The workflow runs automatically at specified times: 7 AM, 1 PM, 5 PM, and 9 PM IST.

---

## How it Works:
1. **RSS Feed Reader** nodes fetch the latest AI-related content.
2. **OpenAI** rewrites the fetched articles into LinkedIn-ready posts.
3. **Email node** sends the post for review.
4. Once approved, the **Google Sheets node** stores the posts, and the **LinkedIn node** posts the content to LinkedIn.

---

## License
MIT License (or other, depending on your choice)

