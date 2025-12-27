# Reel Relay 🎥

**Reel Relay** is an automated n8n workflow designed to seamlessly port Facebook Reels to YouTube. It leverages AI to analyze video content, generate optimized SEO metadata, and manages the entire pipeline from discovery to archival.

---

## 🚀 Workflow Stages

The automation is divided into three distinct stages:

### 🔹 Stage 1: Message Inject Service
This stage monitors a Discord channel for new Facebook Reel links. It extracts the URL, checks for duplicates in a Google Sheet, and downloads the video in HD quality.

![Stage 1](https://github.com/user-attachments/assets/48453647-12dd-4997-9711-8f6f2b92d3d2)

**Key Actions:**
- **Schedule Trigger:** Runs every minute to check for new content.
- **Discord Integration:** Fetches messages from the specified channel.
- **Link Extraction:** Uses JavaScript to parse the Reel URL.
- **Duplicate Check:** Verifies if the Reel has already been processed.
- **HD Download:** Fetches the direct video link for high-quality processing.

---

### 🔹 Stage 2: Analyze Downloaded Reel
In this stage, the downloaded video is analyzed using **Google Gemini AI**. The AI generates a hyper-optimized YouTube title and description tailored for the "Anime Emotion & Mood" niche.

![Stage 2](https://github.com/user-attachments/assets/4bb7b8e0-d081-4b09-81f8-e974ae8b3849)

**Key Actions:**
- **Gemini AI Analysis:** Understands the video content and mood.
- **SEO Optimization:** Generates titles (50-70 chars) and descriptions (<350 chars).
- **Metadata Formatting:** Ensures the output is ready for YouTube's API.

---

### 🔹 Stage 3: Upload and Log
The final stage handles the distribution and logging. The video is uploaded to YouTube, backed up to Google Drive, and a notification is sent back to Discord.

![Stage 3](https://github.com/user-attachments/assets/674f88bc-171b-4ed2-8336-709c4cdf322c)

**Key Actions:**
- **YouTube Upload:** Posts the video as private with a scheduled release.
- **Google Drive Backup:** Stores a copy of the video for archival.
- **Google Sheets Logging:** Records the processed Reel link and timestamp.
- **Discord Notification:** Sends a success message to the team.

---

## 🖼️ Full Workflow Overview

The complete n8n canvas showing the end-to-end automation logic.

![Combined Workflow](https://github.com/user-attachments/assets/ae9b9c6b-309a-427f-835c-ee8c1d95b65d)

---

## 🛠️ Tech Stack
- **Automation:** [n8n](https://n8n.io/)
- **AI:** [Google Gemini 1.5 Flash](https://deepmind.google/technologies/gemini/)
- **Storage:** Google Drive, Google Sheets
- **Platforms:** Discord, YouTube
- **Language:** JavaScript (for custom logic nodes)
