# Adaption Plugin for Claude Desktop

Connect Claude to [Adaption](https://adaptionlabs.ai) for dataset management, fine-tuning, and AutoScientist workflows.

## Installation

### One-Click Install

1. Download `adaption.mcpb` from [Releases](https://github.com/adaptionlabs/adaption-claude-plugin/releases)
2. Double-click the file to install
3. Enter your **Adaption API Key** when prompted
4. Done! ✓

### Get Your API Key

1. Go to [app.adaptionlabs.ai/settings/api-keys](https://app.adaptionlabs.ai/settings/api-keys)
2. Create a new API key
3. Copy and paste it when Claude Desktop asks

## Supported Platforms

- ✅ macOS
- ✅ Windows

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
- Monitor **training progress** and iterations

### 🔬 Invent (2 tools)

- Explore available **domains and subdomains**
- **Generate synthetic datasets** from specifications

## Example Usage

Once installed, you can interact with Adaption through natural conversation:

```
List my Adaption datasets
```

```
Import this HuggingFace dataset and adapt it for fine-tuning
```

```
Start fine-tuning llama-3.1-8b on my adapted dataset
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

- Claude Desktop (macOS or Windows)
- Adaption account with API access
- API key from [app.adaptionlabs.ai/settings/api-keys](https://app.adaptionlabs.ai/settings/api-keys)

## Building from Source

```bash
git clone https://github.com/adaptionlabs/adaption-claude-plugin.git
cd adaption-claude-plugin
zip -r adaption.mcpb manifest.json README.md LICENSE icon.svg skills/ server/
```

Then double-click `adaption.mcpb` to install.

## Support

- **Documentation**: [docs.adaptionlabs.ai](https://docs.adaptionlabs.ai)
- **Issues**: [GitHub Issues](https://github.com/adaptionlabs/adaption-claude-plugin/issues)
- **Email**: support@adaptionlabs.ai

## License

MIT License - see [LICENSE](LICENSE) for details.
