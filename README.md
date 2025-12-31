# 🚀 AI Agent: LinkedIn Content Machine

An advanced **n8n workflow** that turns raw notes or URLs into viral-style LinkedIn posts using **Google Gemini**. It features a "Human-in-the-loop" approval system via Telegram to ensure quality before publishing.

![Workflow Screenshot]<img width="2182" height="859" alt="image" src="https://github.com/user-attachments/assets/88f25509-b980-4cfc-ab5a-02c6a874bdb7" />

<img width="2516" height="1294" alt="image" src="https://github.com/user-attachments/assets/c2470b2a-cd73-48cc-b3e6-6ee54d52f0d3" />


## ✨ Key Features

* **🤖 Multi-Modal AI Agent:** Uses **Google Gemini** to analyze input text/URLs and rewrite them in a specific persona.
* **🎨 AI Image Generation:** Automatically creates a relevant image prompt and generates a visual using **Gemini Imagen**.
* **👮 Human-in-the-loop:** Sends a generated preview (Text + Image) to Telegram. You can **Approve** or **Decline** via interactive buttons.
* **📱 Smart Input Router:** Accepts both raw text notes or existing LinkedIn URLs via Telegram.
* **☁️ Cloud Ready:** Built using standard n8n nodes, fully compatible with n8n Cloud (no custom npm packages required).

## 🛠️ How It Works

1.  **Trigger:** You send a message (Note or URL) to your Telegram Bot.
2.  **Processing:**
    * The workflow identifies if the input is a URL or text.
    * **Persona Loading:** Loads a defined writing style (Tone, Voice, Formatting) from the Code Node.
3.  **AI Generation:**
    * **LangChain Agent** drafts the post following the persona guidelines.
    * **Image Generator** creates a visual asset based on the post context.
4.  **Approval:** You receive the draft and image in Telegram.
    * ✅ **Approve:** The post is published instantly to LinkedIn.
    * ❌ **Decline:** The process stops.

## ⚙️ Setup & Prerequisites

### 1. Credentials Needed
You will need to set up credentials in n8n for:
* **Telegram API:** (Bot Token)
* **Google Gemini (PaLM) API:** (For Text & Image generation)
* <img width="2503" height="1351" alt="image" src="https://github.com/user-attachments/assets/4a170452-78b9-4805-a120-05e65eef042e" />

* **LinkedIn OAuth2:** (For publishing)

### 2. Environment Variables
Add the following variable to your n8n environment variables to secure the bot:
* `TELEGRAM_USER_ID`: Your numeric Telegram User ID (The workflow checks this to prevent unauthorized access).

### 3. Customization
* **Persona:** Open the node named `👤 Load Your Persona` to edit the `PERSONA` constant (Name, Tone, Emojis, etc.) to match your own voice.
* <img width="2474" height="1288" alt="image" src="https://github.com/user-attachments/assets/f51c3d8b-1ae0-40fe-915c-af8e86d8697f" />

* **LinkedIn ID:** In the `Create LinkedIn Post` node, ensure the `person` parameter is set to your URN (or use `me` if supported by your scope).

## 📦 Installation

1.  Download the `workflow.json` file from this repository.
2.  Open your n8n instance.
3.  Go to **Workflows** > **Import from File**.
4.  Select the JSON file.
5.  Update the Credentials and Environment Variables.
6.  Activate the workflow!

---
*Built with ❤️ using n8n and OpenAi*
