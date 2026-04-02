---
name: group-chat-summarizer
description: Intelligent group chat summarization for work and interest groups across all platforms (Feishu, DingTalk, WeChat Work, Discord, Slack, etc.). Extracts key information, action items, topic threads, and generates structured summary reports. Use when users need to summarize group chat conversations, extract to-do items, identify decisions made, or track discussion progress. Supports both manual on-demand summaries and automated daily summaries.
---

# Group Chat Summarizer

Intelligent group chat summarization that transforms messy conversations into actionable insights.

## Quick Start

### Basic Usage

```
User: "Summarize this chat log"
[User pastes chat log]
→ Generate standard summary (Basic/Standard/Detailed based on length)
```

### With Options

```
User: "Give me a detailed summary of yesterday's team chat"
→ Use detailed format with full timeline

User: "Extract only action items from this discussion"
→ Skip narrative, output only action items table

User: "What's the sentiment of this conversation?"
→ Include sentiment analysis section
```

## Supported Platforms

The skill automatically detects and parses:
- **China**: Feishu (飞书), DingTalk (钉钉), WeChat Work (企业微信), QQ
- **International**: Discord, Slack, Microsoft Teams, Telegram
- **Generic**: Plain text, CSV exports, JSON logs

See [references/platform_formats.md](references/platform_formats.md) for format details.

## Summary Levels

### Basic (几句话)
- Best for: Quick catch-up, 50-100 messages
- Output: 3-5 bullet points of key decisions

### Standard (几个要点)  
- Best for: Daily standups, 100-300 messages
- Output: Topic threads + key decisions + action items

### Detailed (完整脉络)
- Best for: Important meetings, 300+ messages
- Output: Full timeline + all sections + risk analysis

## Output Structure

All summaries follow this structure (see [references/output_template.md](references/output_template.md)):

1. **Basic Info** - Group name, time range, participants, message count
2. **Topic Timeline** - Chronological thread of discussion topics
3. **Key Points** - Decisions made, risks, important information
4. **Action Items** - Tasks with owner, deadline, status
5. **Follow-up Suggestions** - Recommended next steps
6. **Notes** - Special mentions, absences, reminders

## Special Features

### Action Item Extraction
Automatically identifies:
- Task descriptions
- @mentioned owners
- Deadline phrases ("by Friday", "next week", "ASAP")
- Status indicators ("done", "pending", "blocked")

### Sentiment Analysis
Detects conversation tone:
- 😊 Positive - collaborative, supportive
- 😐 Neutral - factual, informational  
- 😟 Negative - conflicts, complaints, concerns
- ⚠️ Controversial - disagreements, unresolved debates

### Risk & Controversy Detection
Identifies:
- Blocked items or impediments
- Resource constraints mentioned
- Disagreements without resolution
- Missing information or dependencies

## Workflow

1. **Parse** - Detect platform format and extract messages
2. **Analyze** - Identify topics, participants, timeline
3. **Extract** - Pull out decisions, action items, key info
4. **Generate** - Create structured summary
5. **Enhance** - Add sentiment, risks, follow-ups

## Platform-Specific Notes

### Feishu/DingTalk/WeChat Work
- Supports exported chat logs
- Handles Chinese date/time formats
- Recognizes @mentions and reply threads

### Discord/Slack
- Supports JSON exports
- Handles threaded conversations
- Recognizes emoji reactions as sentiment signals

### API Integration
When platform APIs are available:
- Use `scripts/fetch_messages.py` to retrieve chat history
- Requires appropriate authentication tokens
- Respects rate limits and privacy settings

## Examples

### Example 1: Work Group Daily Summary
```
Input: 127 messages from product-tech team
Output: 
- 3 topics discussed (Q2 planning, UI review, technical concerns)
- 4 action items identified with owners
- 1 risk flagged (frontend timeline)
- Follow-up: Interface doc due Thursday
```

### Example 2: Interest Group Discussion
```
Input: 89 messages about weekend hiking plan
Output:
- Topic: Hiking route selection → Decision: Xiangshan Trail
- 5 participants confirmed
- Action: @Alice to book bus by Wednesday
- Note: @Bob unavailable this weekend
```

## Best Practices

1. **For long chats** (>500 messages): Suggest breaking into time periods
2. **For sensitive content**: Remind users about privacy when sharing logs
3. **For action items**: Always verify @mentions are correctly assigned
4. **For follow-ups**: Suggest specific dates based on context, not generic

## Limitations

- Cannot access chats without user-provided logs or API tokens
- May miss context from edited/deleted messages
- Complex threaded discussions may need manual clarification
- Very long messages (>2000 chars) may be truncated in analysis

## References

- [Output Template](references/output_template.md) - Complete output format specification
- [Platform Formats](references/platform_formats.md) - Supported chat log formats
- [Prompts](references/prompts.md) - LLM prompts for extraction and analysis
