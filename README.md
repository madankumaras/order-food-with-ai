# 🍛 Zomato MCP — Order Food from Claude Desktop

> Order food from Zomato using natural language — no app switching, no scrolling, just chat.

![Claude Desktop](https://img.shields.io/badge/Claude-Desktop-blue?style=flat-square)
![MCP](https://img.shields.io/badge/MCP-Model%20Context%20Protocol-orange?style=flat-square)
![Zomato](https://img.shields.io/badge/Zomato-Connected-red?style=flat-square)
![Node.js](https://img.shields.io/badge/Node.js-v18%2B-green?style=flat-square)

---

## 📌 What is This?

This project connects **Zomato** to **Claude Desktop** using **MCP (Model Context Protocol)** — allowing you to discover restaurants, browse menus, apply offers, and place orders directly through a Claude chat interface.

No more manual scrolling. Just one prompt and you're done. 🎯

---

## 🧠 What is MCP?

**Model Context Protocol (MCP)** is an open protocol that allows AI models like Claude to connect with real-world tools and services. It acts as a bridge between Claude and external APIs, enabling Claude to take real actions on your behalf.

Think of it as giving Claude **hands** to interact with the world. 🤝

---

## ⚙️ Prerequisites

Before getting started, make sure you have the following:

| Requirement | Version | Check Command |
|-------------|---------|---------------|
| Node.js | v18+ | `node -v` |
| Claude Desktop | Latest | [Download here](https://claude.ai/download) |
| Zomato Account | Active | [zomato.com](https://www.zomato.com) |
| npx | Bundled with Node.js | `npx -v` |

---

## 🚀 Setup Guide

### Step 1 — Download Claude Desktop

Visit [claude.ai/download](https://claude.ai/download) and install Claude Desktop for your OS (Mac / Windows).

---

### Step 2 — Locate or Create the Config File

#### On macOS:
```bash
# Check if config file exists
ls ~/Library/Application\ Support/Claude/
```

If `claude_desktop_config.json` does not exist, create it:

```bash
touch ~/Library/Application\ Support/Claude/claude_desktop_config.json
```

#### On Windows:
```
%APPDATA%\Claude\claude_desktop_config.json
```

---

### Step 3 — Add Zomato MCP Configuration

Open the config file:

```bash
# macOS — open in TextEdit
open -a TextEdit ~/Library/Application\ Support/Claude/claude_desktop_config.json

# macOS — open in VS Code
code ~/Library/Application\ Support/Claude/claude_desktop_config.json
```

Paste the following configuration:

```json
{
  "mcpServers": {
    "zomato-mcp": {
      "command": "npx",
      "args": [
        "mcp-remote",
        "https://mcp-server.zomato.com/mcp"
      ]
    }
  }
}
```

Save the file with **Cmd + S** (Mac) or **Ctrl + S** (Windows).

---

### Step 4 — Restart Claude Desktop

Fully quit Claude Desktop:
- **Mac:** Cmd + Q
- **Windows:** Right-click taskbar icon → Quit

Then reopen the app.

---

### Step 5 — Authenticate with Zomato

On first launch, Claude Desktop will prompt you to authenticate with Zomato. A browser window will open for **OAuth login** — approve access and return to Claude Desktop.

> ✅ Your password is never shared. Authentication uses OAuth and payments use UPI QR code for secure checkout.

---

## 💬 Usage — Example Prompts

Once connected, try these prompts directly in Claude Desktop:

```
Find me the best rated Biryani restaurants near me with offers.
```

```
Order the best rated Chicken Biryani near me with the best available offer.
```

```
Show me top 3 pizza places near me under ₹300 with good delivery time.
```

```
What are the current offers available on restaurants near me?
```

---

## 🔧 Troubleshooting

| Issue | Solution |
|-------|----------|
| MCP Disconnected notification | Check Node.js is installed: `node -v` |
| `zomato-mcp` npm package not found | Use the `mcp-remote` config as shown above |
| Auth not working | Ensure you're using Claude Desktop (not browser) |
| Config not detected | Verify JSON syntax and restart Claude Desktop |

---

## 📁 Project Structure

```
~/Library/Application Support/Claude/
├── claude_desktop_config.json   # MCP server configuration
└── config.json                  # Claude Desktop preferences
```

---

## 🙌 Author

**Madan** — AI-Driven SDET / Software Engineer  
Passionate about building intelligent automation systems that save time and reduce manual effort.

> *"The lazy engineer is the best engineer."* 😄

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).

---

## ⭐ Show Your Support

If this helped you, give the repo a ⭐ and share it with your fellow engineers!
