# Slack MCP Server by Insightful Pipe

[![MCP Compatible](https://img.shields.io/badge/MCP-Compatible-blue)](https://insightfulpipe.com/mcp-servers/slack)
[![Insightful Pipe](https://img.shields.io/badge/Insightful_Pipe-MCP_Servers-purple)](https://insightfulpipe.com/mcp-servers)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> **Connect Slack to AI assistants: channels, messages, users and reminders.**

Part of the [Insightful Pipe MCP Server Collection](https://insightfulpipe.com/mcp-servers) — use Slack from Claude, ChatGPT, Cursor, and other AI assistants through the Model Context Protocol (MCP).

<img src="images/slack-icon.svg" alt="Slack MCP Server" width="64" height="64">

## MCP Server URL

```
https://slack.insightfulmcp.com/
```

## What is Slack MCP?

Slack MCP is a **remote Model Context Protocol server** hosted by InsightfulPipe. Access channels, messages, users, conversations, and search across your Slack workspace.

## Installation

### Claude

1. Copy the MCP Server URL: `https://slack.insightfulmcp.com/`
2. Open [Claude Connectors Settings](https://claude.ai/settings/connectors)
3. Scroll to the bottom and click **Add custom connector**
4. Paste the URL and click **Add**
5. Click **Connect** on the connector to start authorization
6. Click **Authorize access** in the browser to complete the connection

### ChatGPT

Custom MCP servers are added through ChatGPT's **Developer mode**. Availability depends on your ChatGPT plan, and workspace admins may need to allow it.

1. Turn on **Developer mode** in ChatGPT settings
2. Create a new app for a remote MCP server and paste the URL: `https://slack.insightfulmcp.com/`
3. Authorize with your InsightfulPipe account

See OpenAI's guide: [Developer mode and MCP apps in ChatGPT](https://help.openai.com/en/articles/12584461-developer-mode-and-mcp-apps-in-chatgpt)

### Claude Code

```bash
claude mcp add --transport http slack https://slack.insightfulmcp.com/
```

### Cursor

Add the server to `~/.cursor/mcp.json` (all projects) or `.cursor/mcp.json` (one project):

```json
{
  "mcpServers": {
    "slack": {
      "url": "https://slack.insightfulmcp.com/"
    }
  }
}
```

Then authorize the connection when Cursor prompts you.

## Available Actions

21 actions: 12 read, 9 write.

### Read Actions (12)

| Action | Description |
|--------|-------------|
| `auth_test` | Test authentication and get information about the token |
| `get_conversation_info` | Get information about a specific conversation/channel |
| `get_message_permalink` | Get a permanent URL for a specific message |
| `get_team_info` | Get information about the Slack workspace |
| `get_user_info` | Get information about a specific user |
| `get_user_profile` | Get a user's profile information |
| `list_conversation_history` | Fetch message history for a conversation/channel |
| `list_conversation_members` | List members of a conversation/channel |
| `list_conversation_replies` | Fetch replies (thread) for a specific message |
| `list_conversations` | List all channels/conversations the bot or user is a member of or can see |
| `list_reminders` | List reminders for the authenticated user |
| `list_users` | List all users in the Slack workspace |

### Write Actions (9)

| Action | Description |
|--------|-------------|
| `add_reminder` | Create a new reminder |
| `archive_conversation` | Archive a conversation/channel |
| `create_conversation` | Create a new public or private channel |
| `invite_to_conversation` | Invite users to a conversation/channel |
| `join_conversation` | Join an existing public channel |
| `post_message` | Send a message to a channel, DM, or thread |
| `post_message_as_user` | Send a message as the authenticated user (not the bot) |
| `update_message` | Update an existing message |
| `update_message_as_user` | Update a message as the authenticated user |

## Control What Your AI Can Do

You decide what AI agents can do with each connected account:

- **Turn individual actions on or off** for every connected account, so agents only see the actions you allow.
- **Connect as Read-only or Read & Write.** A read-only connection can only enable read actions.
- **Destructive actions stay off by default.** Actions such as deletes are disabled until an admin enables them.
- **Team access per account.** Restricted team members only use the accounts they are granted, with the read actions enabled on them.

## Usage Examples

```
"Summarize the last day of messages in #marketing"
```

```
"Post the weekly report to #general"
```

```
"Remind me tomorrow at 9am to review campaigns"
```

## Pricing

The Slack MCP server is included in every InsightfulPipe plan, together with all other MCP servers and the CLI. Plans start at $29.99/month with a 7-day free trial. See [insightfulpipe.com/pricing](https://insightfulpipe.com/pricing) for current plans.

## Explore More MCP Servers by Insightful Pipe

Visit **[insightfulpipe.com/mcp-servers](https://insightfulpipe.com/mcp-servers)** to discover our full collection of MCP servers.

- [Telegram MCP](https://insightfulpipe.com/mcp-servers/telegram)
- [Notion MCP](https://insightfulpipe.com/mcp-servers/notion)

**[View All MCP Servers →](https://insightfulpipe.com/mcp-servers)**

## Resources

- [Documentation](https://insightfulpipe.com/docs)
- [Video Tutorial](https://www.youtube.com/playlist?list=PLJNzvjxzI5Xwe__BJJLAelSF0ewO3mEFk)
- [InsightfulPipe Blog](https://insightfulpipe.com/blog)

## Support

- **Documentation**: [insightfulpipe.com/docs](https://insightfulpipe.com/docs)
- **All MCP Servers**: [insightfulpipe.com/mcp-servers](https://insightfulpipe.com/mcp-servers)
- **Email**: support@insightfulpipe.com

---

**[Insightful Pipe](https://insightfulpipe.com)** — AI-powered marketing analytics through MCP servers. [Explore all integrations →](https://insightfulpipe.com/mcp-servers)

## License

MIT License - see [LICENSE](LICENSE) for details.
