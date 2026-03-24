# Content Copilot

Chat your way to polished social media posts. For any creator, any platform, any niche.

## What is this?

A Claude Code skill that turns natural conversation into publish-ready posts for Xiaohongshu (小红书), X/Twitter, and more.

You don't write posts. You **talk about ideas**. The copilot sharpens your angle, challenges your thinking, and drafts a post that sounds like you — because it's built from your actual words.

## How it works

```
$ claude

> 热点     (or "trending" / "find topics")

📡 Found 8 trending topics in AI:

1. [💬 People] Sam Altman says...
2. [🚀 Product] Anthropic launches Dispatch...
3. [💰 Business] Cursor raises at $10B...
...

> Let's talk about #3

Cursor at $10B with 200 employees — what's your take?
What makes this different from the last wave of dev tools?

> I think the real story isn't the valuation, it's that...

(2-3 more exchanges)

Ready to draft? I think we have a solid angle.

> Go for it

【标题】40个人撑起百亿估值：Cursor卖的不是工具，是组织变革的入场券

【正文】
...
```

## Features

- **🔍 Trending topic discovery** — searches the web for what's hot in your niche
- **💬 Conversational drafting** — chat about ideas, get posts that preserve your voice
- **💡 Light content sparks** — quick inspiration for personal, reflective posts
- **🌏 Bilingual** — Chinese, English, or both
- **📕🐦 Multi-platform** — Xiaohongshu, X/Twitter, with custom platforms supported
- **👤 Fully customizable** — your profile, your topics, your style, your rules
- **📱 Mobile via Dispatch** — text from your phone, posts draft on your desktop

## Install

### Claude Code
```bash
git clone https://github.com/[your-username]/content-copilot.git ~/.claude/skills/content-copilot
```

### OpenClaw
```bash
git clone https://github.com/[your-username]/content-copilot.git ~/skills/content-copilot
```

## First run

Just start Claude Code and say "write a post" or "写笔记". The skill walks you through a 2-minute profile setup:

1. **Who are you** — your background and credentials
2. **Your niche** — AI, business, food, fitness, anything
3. **Your style** — spicy hot takes? warm & relatable? deep analysis?
4. **Your platforms** — Xiaohongshu, X/Twitter, or both
5. **Your language** — English, Chinese, or bilingual

After setup, you're ready to create.

## Quick commands

| Say this | Get this |
|----------|----------|
| `trending` / `热点` | Search trending topics in your niche |
| `light` / `轻内容` | Get 6 quick content sparks |
| `draft it` / `出笔记` | Generate post from conversation |
| `sharper` / `再犀利一点` | Revise a section |
| `bilingual` / `双语` | Output both Chinese + English |
| `make it a thread` | Convert to X/Twitter thread |
| `next` / `下一篇` | Start a new topic |
| `done` / `收工` | End session, see summary |
| `update profile` | Change your settings |

## Post structure

### Xiaohongshu (600-800 chars)

```
Hook (10%) → Context (15%) → Why it matters (15%) → Deep analysis (40%) → Action for reader (20%)
```

### X/Twitter thread (3-7 tweets)

```
🧵 Hook tweet → Context → Core insight → Evidence → Implication → Closing question
```

### Light content (300-500 chars)

```
Small story/scene → Observation → Reader takeaway
```

## Customization

Everything is configurable through conversation:

- "I changed jobs" → updates your profile
- "Make posts shorter" → adjusts length preferences
- "Add LinkedIn" → adds a new platform with custom rules
- "Here's a post I liked, match this style" → learns your voice
- "I want to avoid mentioning X" → adds to your avoid list

## Mobile usage

With [Claude Dispatch](https://support.claude.com/en/articles/13947068), you can create posts from your phone:

1. Keep Claude Desktop running on your computer
2. Open Claude mobile app → Dispatch tab
3. Chat and create posts from anywhere
4. Posts draft on your desktop, results sync to your phone

## Philosophy

> Follow builders, not influencers. Write posts, don't manufacture content.

This tool doesn't replace your thinking — it **structures** it. Your voice, your ideas, your metaphors stay intact. The copilot just helps you get from "I have a thought" to "here's a post" faster.

## License

MIT
