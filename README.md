# Group Chat Summarizer

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![OpenClaw Skill](https://img.shields.io/badge/OpenClaw-Skill-blue.svg)](https://openclaw.ai)

> Intelligent group chat summarization for work and interest groups across all platforms.

Transform messy group chat conversations into structured, actionable insights with AI-powered analysis.

## ✨ Features

- 🌐 **Multi-Platform Support**: Feishu, DingTalk, WeChat Work, Discord, Slack, Teams, Telegram
- 📊 **Three Summary Levels**: Basic, Standard, Detailed
- ✅ **Smart Action Item Extraction**: Auto-detects tasks, owners, and deadlines
- 😊 **Sentiment Analysis**: Understand conversation tone and emotions
- ⚠️ **Risk Detection**: Identifies blockers, dependencies, and controversies
- 📝 **Structured Output**: 6 standardized sections for clarity

## 🚀 Quick Start

### Installation

```bash
# Install via ClawHub
clawhub install group-chat-summarizer

# Or download from GitHub Releases
wget https://github.com/zhuqingsonga/group-chat-summarizer/releases/download/v1.0.0/group-chat-summarizer.skill
```

### Usage

```bash
# Basic usage
python scripts/summarize_chat.py chat_log.txt

# With options
python scripts/summarize_chat.py chat_log.txt --level detailed --output summary.md

# As OpenClaw skill
"Summarize this chat log for me"
```

## 📋 Output Structure

All summaries include:

1. **Basic Info** - Group name, time range, participants, message count
2. **Topic Timeline** - Chronological discussion threads
3. **Key Points** - Decisions, risks, important information
4. **Action Items** - Tasks with owner, deadline, status
5. **Follow-up Suggestions** - Recommended next steps
6. **Notes** - Special mentions and reminders

## 🛠️ Supported Platforms

| Platform | Text Export | JSON Export | API |
|----------|------------|-------------|-----|
| Feishu (飞书) | ✅ | ✅ | Planned |
| DingTalk (钉钉) | ✅ | ✅ | Planned |
| WeChat Work | ✅ | ✅ | Planned |
| Discord | ❌ | ✅ | Planned |
| Slack | ❌ | ✅ | Planned |
| Teams | ❌ | ✅ | Planned |
| Telegram | ❌ | ✅ | Planned |

## 📖 Documentation

- [SKILL.md](SKILL.md) - Skill documentation and usage guide
- [references/output_template.md](references/output_template.md) - Output format specification
- [references/platform_formats.md](references/platform_formats.md) - Platform format details
- [references/prompts.md](references/prompts.md) - LLM prompts for analysis

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Built for [OpenClaw](https://openclaw.ai) AI agent platform
- Inspired by the need for better group chat productivity

## 📊 Stats Goal

🎯 **Target**: 10,000+ downloads and stars on ClawHub

Help us reach this goal by:
- ⭐ Starring this repository
- 📢 Sharing with your team
- 🐛 Reporting issues
- 💡 Suggesting features

---

**Made with ❤️ by the OpenClaw Community**
