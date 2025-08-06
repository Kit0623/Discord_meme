# Discord Meme Bot 🤖🎭

A simple Discord bot that fetches and shares random memes from the internet using the meme-api.

## 🚀 Features

- **Random Memes**: Get fresh memes with the `$meme` command
- **Simple Commands**: Easy-to-use command system
- **Real-time Response**: Instant meme delivery to your Discord server

## 📋 Requirements

- Python 3.8 or higher
- Discord.py library
- Requests library
- A Discord Bot Token

## 🔧 Installation

### 1. Install Required Packages

```bash
pip install discord.py requests
```

### 2. Set Up Discord Bot

1. Go to [Discord Developer Portal](https://discord.com/developers/applications)
2. Create a **New Application**
3. Go to the **Bot** section
4. Create a bot and copy the **Token**
5. Go to **OAuth2 → URL Generator**
6. Select **Bot** scope and **Send Messages** permission
7. Use the generated URL to invite your bot to a server

### 3. Configure the Bot

Replace the token in `bot.py`:
```python
client.run('YOUR_ACTUAL_BOT_TOKEN_HERE')
```

**⚠️ Security Note:** Never share your bot token publicly!

## 🎮 Usage

### Running the Bot

```bash
python bot.py
```

When successful, you should see:
```
Logged on as YourBotName#1234!
```

### Commands

| Command | Description | Example |
|---------|-------------|---------|
| `$meme` | Fetches a random meme image | Type `$meme` in any channel |

## 📁 Files

- `bot.py` - Main bot script with meme functionality
- `README.md` - This documentation file

## 🔧 How It Works

1. **Bot Setup**: Creates a Discord client with message content intents
2. **Meme Fetching**: Uses `https://meme-api.com/gimme` to get random memes
3. **Command Processing**: Listens for `$meme` command and responds with meme URL
4. **Auto-ignore**: Ignores its own messages to prevent loops

## 📝 Code Structure

```python
def get_meme():
    # Fetches meme from API
    response = requests.get('https://meme-api.com/gimme')
    json_data = json.loads(response.text)
    return json_data['url']

class MyClient(discord.Client):
    async def on_ready(self):
        # Bot startup confirmation
        
    async def on_message(self, message):
        # Handles incoming messages and commands
```

## 🔍 Troubleshooting

### Common Issues:

1. **401 Unauthorized Error**
   - Check if your bot token is correct
   - Regenerate token if it was exposed publicly

2. **Bot Not Responding**
   - Ensure bot has "Send Messages" permission
   - Check if bot is online in your server
   - Verify message content intents are enabled

3. **Import Errors**
   - Install required packages: `pip install discord.py requests`

### Bot Permissions Required:
- ✅ Send Messages
- ✅ Read Message History
- ✅ Use External Emojis (optional)

## 🌐 API Information

This bot uses the **Reddit Meme API**:
- **Endpoint**: `https://meme-api.com/gimme`
- **Rate Limit**: No authentication required
- **Response**: JSON with meme URL and metadata

## 🛡️ Security Best Practices

1. **Never commit tokens** to version control
2. **Use environment variables** for sensitive data
3. **Regenerate tokens** if accidentally exposed
4. **Limit bot permissions** to only what's needed

## 📄 License

This project is open source and available under the MIT License.

## 🤝 Contributing

Feel free to fork this project and submit pull requests for improvements!

---

**Created by Kit0623** 🐍  
*Powered by Discord.py and Meme API*
