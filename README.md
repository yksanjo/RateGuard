# RateGuard 🛡️

> **API Rate Limit Monitor** - Never get caught off guard by rate limit errors again. Monitor multiple APIs simultaneously and get real-time alerts via Slack or Discord when you're approaching your limits.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Status: Active](https://img.shields.io/badge/status-active-success.svg)](https://github.com/yksanjo/RateGuard)
[![GitHub stars](https://img.shields.io/github/stars/yksanjo/RateGuard?style=social)](https://github.com/yksanjo/RateGuard)

**RateGuard** is a powerful monitoring tool that keeps track of your API rate limits across multiple services. Get proactive alerts before you hit your limits, preventing service disruptions and ensuring your applications run smoothly.

## Features

- 🔔 Real-time rate limit monitoring
- 📊 Track multiple APIs simultaneously
- 💬 Slack and Discord notifications
- ⚠️ Configurable warning thresholds
- 📈 Rate limit usage history
- 🔄 Auto-refresh monitoring

## Installation

```bash
pip install -r requirements.txt
```

## Configuration

Create a `.env` file:

```env
# Slack Configuration
SLACK_BOT_TOKEN=xoxb-your-token
SLACK_CHANNEL_ID=C1234567890

# Discord Configuration (alternative)
DISCORD_BOT_TOKEN=your-discord-token
DISCORD_CHANNEL_ID=123456789012345678

# APIs to Monitor
# Format: API_NAME:ENDPOINT:HEADER_KEY:HEADER_VALUE
# Example: GITHUB:https://api.github.com/rate_limit:X-RateLimit-Remaining:Authorization:token YOUR_TOKEN
```

## Usage

### Start Monitoring

```bash
python monitor.py
```

### Add API to Monitor

```bash
python monitor.py --add-api github --endpoint https://api.github.com/rate_limit --header Authorization --header-value "token YOUR_TOKEN"
```

### List Monitored APIs

```bash
python monitor.py --list
```

### Remove API

```bash
python monitor.py --remove-api github
```

## Supported APIs

- GitHub API
- Twitter API
- Stripe API
- OpenAI API
- Custom REST APIs (with rate limit headers)

## Rate Limit Header Formats

The monitor supports common rate limit header formats:
- `X-RateLimit-Remaining` / `X-RateLimit-Limit`
- `RateLimit-Remaining` / `RateLimit-Limit`
- `X-Rate-Limit-Remaining` / `X-Rate-Limit-Limit`

## Example Output

```
🚨 Rate Limit Alert!
API: GitHub
Remaining: 45 / 5000
Usage: 99.1%
Threshold: 95%
```

## License

MIT License


