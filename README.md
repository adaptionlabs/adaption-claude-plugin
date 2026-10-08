# Adaption Plugin for Claude

Connect Claude to [Adaption](https://adaptionlabs.ai) for dataset management and fine-tuning workflows.

The plugin bundles three skills and the remote Adaption MCP server
(`https://api.prod.adaptionlabs.ai/api/v1/mcp`). You sign in with your Adaption
account in the browser; no API key is needed.

## Installation

### Claude (claude.ai and Claude Desktop)

1. **Customize → Plugins → + Add marketplace → Add from a repository**
2. Enter `adaptionlabs/adaption-claude-plugin`
3. Install the **adaption** plugin from the added marketplace
4. Sign in to Adaption. Claude asks you to connect `adaption` either right
   after install or the first time you use it in a session (for example
   "List my Adaption datasets"). Click **Connect**: the Adaption sign-in page
   opens in your browser. Sign in, choose the organization, and click
   **Authorize**

If the connector shows **Connects in sessions** under Connectors, that is
expected: Claude connects it inside a session, not from the settings page.

### Claude Code

Requires a recent Claude Code (`claude update`); older versions can't sign in
to this server.

```bash
claude plugin marketplace add adaptionlabs/adaption-claude-plugin
claude plugin install adaption@adaption
```

Then run `/mcp` in Claude Code, select `plugin:adaption:adaption`, and choose
**Authenticate**. Claude Code opens the Adaption sign-in page in your browser.

### Connector only (no skills)

To add just the Adaption tools without the plugin's skills:

1. **Settings → Connectors → Add custom connector**
2. MCP server URL: `https://api.prod.adaptionlabs.ai/api/v1/mcp`
3. Leave request headers empty, click **Add**, then **Connect** and sign in

### MCPB bundle with an API key

For Claude Desktop setups that can't use OAuth, the MCPB bundle connects with
an Adaption API key instead.

1. Create an API key at [adaptionlabs.ai/app/settings](https://adaptionlabs.ai/app/settings?tab=api_keys)
2. Download `adaption.mcpb` from [Releases](https://github.com/adaptionlabs/adaption-claude-plugin/releases)
3. Double-click the file and enter the API key when prompted

Don't install the bundle alongside the plugin: both register a server named
`adaption`.

## Features

### 📊 Dataset Management (11 tools)

- **Import** datasets from HuggingFace, Kaggle, or Google Sheets
- **Adapt** datasets with Adaption's processing pipeline
- **Augment** datasets with synthetic domain/general rows
- **Translate** and **localize** dataset content
- **Combine** multiple datasets
- **Export** processed results

### 🎯 Fine-tuning (5 tools)

- Browse available **base models**
- Get **hyperparameter recommendations**
- Launch **AutoScientist training runs**
- Monitor **training progress** and results

### 🔬 Invent (2 tools)

- Explore available **domains and subdomains**
- **Generate synthetic datasets** from natural language descriptions

## Available Skills

| Skill | Description |
|-------|-------------|
| `adaption-dataset` | Dataset import, processing, and transformation workflows |
| `adaption-training` | AutoScientist training run management |
| `adaption-invent` | Synthetic data generation with Invent |

## Example Usage

Once installed, you can interact with Adaption through natural conversation:

```
List my Adaption datasets
```

```
Import this HuggingFace dataset and adapt it for fine-tuning
```

```
Start fine-tuning on my adapted dataset and pick a suitable base model
```

```
Generate 1000 customer service examples using Invent
```

```
Check the status of my training job
```

## MCP Tools Reference

### Dataset Tools

| Tool | Description |
|------|-------------|
| `list_datasets` | List datasets visible to your organization |
| `get_dataset` | Get details of one dataset |
| `get_dataset_status` | Poll processing status and progress |
| `get_dataset_evaluation` | Get quality evaluation results |
| `get_dataset_export_links` | Get export download URLs |
| `import_dataset` | Import from HuggingFace, Kaggle, or Google Sheets |
| `run_dataset_adaptation` | Estimate or launch adaptation |
| `augment_dataset` | Add synthetic domain/general rows |
| `translate_dataset` | Translate rows to target languages |
| `localize_dataset` | Localize for country/language pairs |
| `combine_datasets` | Combine compatible datasets |

### Training Tools

| Tool | Description |
|------|-------------|
| `list_training_models` | List available base models |
| `list_autoscientist_runs` | List training runs |
| `get_autoscientist_run` | Get run details and progress |
| `recommend_autoscientist_hyperparameters` | Get recommended config |
| `create_autoscientist_run` | Launch training (spends credits) |

### Invent Tools

| Tool | Description |
|------|-------------|
| `list_invent_domains` | List valid domain/subdomain codes |
| `generate_dataset` | Estimate or launch dataset generation |

## Requirements

- Claude Desktop, Claude Code, or claude.ai
- An Adaption account

## Building the MCPB bundle from source

```bash
git clone https://github.com/adaptionlabs/adaption-claude-plugin.git
cd adaption-claude-plugin
rm -f adaption.mcpb
zip -r adaption.mcpb manifest.json README.md LICENSE icon.png server/ -x '*.DS_Store'
```

Then double-click `adaption.mcpb` to install.

## Support

- **Documentation**: [docs.adaptionlabs.ai](https://docs.adaptionlabs.ai)
- **Issues**: [GitHub Issues](https://github.com/adaptionlabs/adaption-claude-plugin/issues)
- **Email**: support@adaptionlabs.ai

## License

MIT License - see [LICENSE](LICENSE) for details.
