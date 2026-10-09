# Adaption

Connect Claude to [Adaption](https://adaptionlabs.ai) for dataset management
and fine-tuning workflows.

The plugin adds the remote Adaption MCP server
(`https://api.prod.adaptionlabs.ai/api/v1/mcp`) and three skills:

| Skill | Description |
|-------|-------------|
| `adaption-dataset` | Import, adapt, augment, translate, localize, and combine datasets |
| `adaption-training` | Launch and monitor AutoScientist fine-tuning runs |
| `adaption-invent` | Generate synthetic datasets from natural language descriptions |

## Sign in

The server uses OAuth; no API key is needed.

- **Chat (claude.ai and Claude Desktop):** open the plugin's **Connectors**
  tab, click **Add** next to `adaption` (an Owner clicks **Add for your team**
  on Team and Enterprise plans), then **Connect**
- **Cowork:** click **Connect** when Claude asks to connect `adaption`
- **Claude Code:** run `/mcp`, select `plugin:adaption:adaption`, and choose
  **Authenticate**

In each case the Adaption sign-in page opens in your browser: sign in, choose
the organization, and click **Authorize**.

## Example prompts

- "List my Adaption datasets"
- "Import this HuggingFace dataset and adapt it for fine-tuning"
- "Start fine-tuning on my adapted dataset and pick a suitable base model"

Tools that launch adaptation, generation, or training spend Adaption credits.

## Support

- Documentation: [docs.adaptionlabs.ai](https://docs.adaptionlabs.ai)
- Issues: [GitHub Issues](https://github.com/adaptionlabs/adaption-claude-plugin/issues)
- Email: support@adaptionlabs.ai
