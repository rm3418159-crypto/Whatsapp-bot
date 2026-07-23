# WhatsApp Bot 🤖

A powerful WhatsApp bot built with Baileys that can manage groups, save view-once messages, and play games!

## Features ✨

### 👥 Group Management
- Promote/Demote members
- Kick members from groups
- View group information
- Set group description
- Set group name
- Mute/Unmute group

### 📱 View Once Saver
- Save view-once images
- Save view-once videos
- Save view-once audio
- **Resend saved view-once media** ✨ NEW
- **List all saved files** ✨ NEW

### 🎮 Games
- Tic Tac Toe
- Trivia Questions
- Dice Roll
- Rock, Paper, Scissors
- Fortune Teller

### 📋 General Commands
- Help command
- Ping/Status check
- Bot information

## Installation 🚀

### Prerequisites
- Node.js v14 or higher
- npm or yarn

### Setup Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/rm3418159-crypto/whatsapp-bot.git
   cd whatsapp-bot
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Create .env file**
   ```bash
   cp .env.example .env
   ```

4. **Start the bot**
   ```bash
   npm start
   ```

5. **Scan QR Code**
   - Open WhatsApp on your phone
   - Go to Settings > Linked Devices
   - Scan the QR code displayed in your terminal

## Commands 📝

### General
| Command | Description |
|---------|-------------|
| `!help` | Show all commands |
| `!ping` | Check bot status |

### Group Management (Admin Only)
| Command | Description |
|---------|-------------|
| `!promote @member` | Promote member to admin |
| `!demote @member` | Demote admin to member |
| `!kick @member` | Remove member from group |
| `!groupinfo` | Get group information |
| `!setdesc <text>` | Set group description |
| `!setname <name>` | Set group name |
| `!mute` | Mute group (admins only) |
| `!unmute` | Unmute group |

### View Once Saver
| Command | Description |
|---------|-------------|
| `!save` | Reply to view-once message to save |
| `!list` | View all saved media files with details |
| `!resend <filename>` | Resend a saved view-once message |

**Example Usage:**
1. Someone sends a view-once message
2. Reply to it with `!save`
3. Use `!list` to see all saved files
4. Use `!resend filename.media` to resend the saved media as view-once

### Games
| Command | Description |
|---------|-------------|
| `!dice` | Roll a dice (1-6) |
| `!rps rock/paper/scissors` | Play Rock, Paper, Scissors |
| `!trivia` | Start a trivia question |
| `!fortune` | Get a random fortune |

## Project Structure 📁

```
whatsapp-bot/
├── index.js              # Main bot file
├── package.json          # Dependencies
├── .env.example          # Example environment variables
├── .gitignore            # Git ignore file
├── README.md             # This file
├── handlers/
│   └── commandHandler.js # Command handler system
├── commands/             # All bot commands
│   ├── help.js
│   ├── ping.js
│   ├── promote.js
│   ├── demote.js
│   ├── kick.js
│   ├── groupinfo.js
│   ├── setdesc.js
│   ├── setname.js
│   ├── mute.js
│   ├── unmute.js
│   ├── save.js
│   ├── list.js           # NEW: List saved files
│   ├── resend.js         # NEW: Resend saved media
│   ├── dice.js
│   ├── rps.js
│   ├── trivia.js
│   └── fortune.js
└── saved_media/          # Folder for saved view-once media
```

## Configuration ⚙️

Edit `.env` file to customize:

```env
# Command prefix (default: !)
BOT_PREFIX=!

# Bot name
BOT_NAME=WhatsApp Bot

# Debug mode
DEBUG=false

# Session name
SESSION_NAME=whatsapp-bot-session
```

## Adding New Commands 🎨

Create a new file in the `commands/` directory:

```javascript
module.exports = {
  name: 'commandname',
  description: 'Command description',
  groupOnly: false,      // Only works in groups
  adminOnly: false,      // Only for admins
  async execute(bot, message, args, from, sender, isGroup) {
    // Command logic here
    bot.sendMessage(from, { text: 'Response' });
  },
};
```

## New Features 🆕

### View Once Resender
Save view-once messages that disappear and resend them whenever you want!

**How it works:**
1. Someone sends a view-once image/video/audio
2. Reply with `!save` - the media is saved locally
3. Use `!list` to see all saved files with timestamps
4. Use `!resend <filename>` to resend it as a new view-once message

**Features:**
- Auto-detects media type (image/video/audio)
- Shows file size and save date
- Messages resent as view-once (disappear after viewing)

## Troubleshooting 🔧

### Bot doesn't respond
- Make sure the bot is online (check terminal)
- Use the correct command prefix (default: `!`)
- Ensure bot has necessary permissions

### QR Code issues
- If QR doesn't load, try deleting the `session/` folder and restart
- Make sure you have internet connection

### Command errors
- Check bot console for error messages
- Verify command syntax
- Ensure bot has permissions for admin commands

### Saved media not working
- Ensure `saved_media/` folder exists
- Check file permissions
- Verify media format is supported

## Important Notes ⚠️

1. **Terms of Service**: Using bots with WhatsApp may violate their Terms of Service. Use at your own risk.
2. **Authentication**: The bot uses WhatsApp Web authentication. Your phone must be connected to scan the QR code.
3. **Session**: Keep your `session/` folder private and never share it.
4. **Rate Limiting**: WhatsApp has rate limits. Don't spam commands.
5. **Storage**: View-once media is stored locally. Manage storage accordingly.

## Support 💬

For issues and feature requests, please open an issue on GitHub.

## License 📄

MIT License - See LICENSE file for details

## Contributing 🤝

Contributions are welcome! Feel free to fork this project and submit pull requests.

---

**Made with ❤️ by rm3418159-crypto**
