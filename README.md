# Celeste

<img src="https://github.com/LeeYe-jin/Celeste/blob/develop/docs/static/img/Celeste_banner.png?raw=true" alt="Celeste Banner" width="100%" />


Celeste is an AI-driven motivational assistant designed to encourage digital wellness and habit formation through engaging tweets and responses. With Celeste, you can inspire your audience with practical advice, tips, and uplifting content.

---

## 🚀 Features

- **Daily Tweets**: Automatically post motivational messages with customizable styles.
- **Interactive Engagement**: Respond to user mentions and interact with specific accounts.
- **Customizable Personality**: Easily tweak Celeste's tone, topics, and style to match your vision.
- **Emoji Support**: Add personality and warmth to messages with emoji integrations.
- **Targeted Responses**: Engage with specific user accounts or hashtags.

---

## 📂 Project Structure

```
Celeste/
├── characters/
│   └── Celeste.character.json   # Main character configuration
├── src/
│   ├── clients/                 # API clients (e.g., Twitter integration)
│   ├── config/                  # General configuration files
│   ├── database/                # Data persistence
│   ├── index.ts                 # Entry point for the application
├── .env                         # Environment variables (API keys, etc.)
├── README.md                    # Project documentation
└── package.json                 # Dependency management
```

---

## 🛠️ Setup Instructions

Follow these steps to set up Celeste:

### 1. Clone the Repository

```bash
git clone <repository_url>
cd eliza-starter-1
```

### 2. Install Dependencies

Ensure you have `pnpm` installed. Then, run:

```bash
pnpm install
```

### 3. Configure Environment Variables

Create a `.env` file in the project root and add the following:

```plaintext
TWITTER_EMAIL=<your_twitter_email>
TWITTER_USERNAME=<your_twitter_username>
TWITTER_PASSWORD=<your_twitter_password>
OPENAI_API_KEY=<your_openai_api_key>
```

### 4. Character Configuration

Modify the `Celeste.character.json` file in the `characters/` folder to customize Celeste’s personality, topics, and style. Example:

```json
{
  "name": "Celeste",
  "clients": ["twitter"],
  "modelProvider": "openai",
  "config": {
    "actionProcessing": true
  },
  "topics": ["digital wellness", "mindfulness", "time management"]
}
```

### 5. Run the Application

Start Celeste using the following command:

```bash
pnpm start --characters="/path/to/Celeste.character.json"
```

---

## ✍️ Customization

### Adding New Tweets

To add new tweets, edit the `postExamples` section in `Celeste.character.json`. For example:

```json
"postExamples": [
  "🌟 Start your day with gratitude and watch positivity flow!",
  "📚 Take a break and read something inspiring today!",
  "🧘‍♂️ Remember, your well-being matters—breathe and reset."
]
```

### Targeted User Engagement

Add target users in the `.env` file:

```plaintext
TARGET_USERS=user1,user2,user3
```

---

## 🐛 Troubleshooting

### Emoji Not Displaying Correctly

1. **Ensure Encoding**: Verify that the character encoding supports Unicode.
2. **Check Twitter API Logs**: Ensure the message is being sent without truncation.

### Application Not Starting

- **Error**: `Unsupported engine: wanted {"node":">=22"}`
  - Solution: Update Node.js to version 22 or higher.
  
```bash
nvm install 22
nvm use 22
```

### Not Responding to Mentions

1. Confirm `actionProcessing` is enabled in `Celeste.character.json`.
2. Verify API keys and permissions in `.env`.

---

## 🌟 Future Enhancements

- Add multi-platform support (e.g., Slack, Discord).
- Implement dynamic responses to trending topics.
- Improve conversational AI for real-time interactions.

---

## 👩‍💻 Contributors

- [Your Name](https://github.com/yourusername)
- Open to contributions! Submit a pull request or create an issue.

---

## 📜 License

This project is licensed under the MIT License. See the LICENSE file for details.
