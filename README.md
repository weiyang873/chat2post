# Content Copilot 内容副驾驶

**Chat your way to polished posts. For any creator, any platform, any niche.**

**聊着聊着就写完了。适用于任何创作者、任何平台、任何领域。**

---

## What is this? 这是什么？

A Claude Code skill that helps you create social media posts through natural conversation.

一个 Claude Code 技能，让你通过自然对话来创作社交媒体内容。

You don't stare at a blank page. You **talk about ideas** — the copilot sharpens your angle, challenges your thinking, and drafts a post that sounds like you, because it's built from your actual words.

你不用对着空白页发呆。你只管**聊想法**——副驾驶帮你打磨角度、挑战你的思考，最后生成一篇听起来像你写的笔记，因为它本来就是从你说的话里提炼出来的。

**Supported platforms 支持平台：**
- 📕 Xiaohongshu 小红书
- 🐦 X / Twitter
- More can be added 可自行添加更多

---

## How it works 怎么用

Open Claude Code, say "热点" or "trending", pick a topic, chat a few rounds, say "出笔记" — done.

打开 Claude Code，说"热点"，选一个话题，聊几轮，说"出笔记"——搞定。

```
$ claude

> 热点

📡 Found 8 trending AI topics:
1. [💬 People] Sam Altman says...
2. [🚀 Product] Cursor ARR hits $500M with only 200 employees...
3. [💰 Business] DeepSeek launches new reasoning model...
...

> 聊聊第2个

200人做到$500M ARR，你觉得核心变量是什么？
你讲座里企业家听到这种数据，第一反应通常是什么？

> 我觉得大家都被估值迷惑了，真正的问题是：
> 200人做5000人的产出，那4800人去哪了？

"4800人去哪了"——这句太好了。那你的意思是，
传统企业的壁垒（人身上的隐性知识）被AI拆掉了？

> 对，以前雇人是买他脑子里的routine，现在routine
> 可以外包给AI。真正需要的是"老板力"——
> 知道要什么、判断好坏、敢拍板。

素材很足了。要不要我出笔记？

> 出吧

【标题】200人干出500M营收：你以为是效率故事，
其实4800人已经没有位置了

【正文】
所有人都在惊叹Cursor的估值...（723字）

要改哪里？直接告诉我，或者说"OK"我就帮你过合规然后保存。

> 第二段再犀利一点

（更新后的版本...）

> OK

✅ 合规检查通过，0处风险。已保存到草稿箱。
说"发了"可标记为已发布。
```

---

## Key features 核心功能

### 🔍 Trending topics 热点追踪
Say "热点" or "trending" — the copilot searches the web for what's hot in your niche, covering both global and Chinese sources.

说"热点"——自动搜索你所在领域的最新热点，覆盖海外和国内。

### 💬 Conversational drafting 对话式创作
The copilot is not a ghostwriter — it's your **editor**. It asks sharp questions, challenges your logic, and reminds you: "Why should your reader care?"

副驾驶不是代笔——它是你的**编辑搭子**。追问逻辑、挑战观点、提醒你："读者看完该怎么办？"

### ✏️ In-chat editing 对话内编辑
After generating, edit directly: "换标题" "第三段犀利一点" "加上我刚才那个比喻" — the copilot revises instantly.

生成后直接在对话里改：改标题、调段落、加表达，即时修改。

### ✅ Compliance check 合规检查
Before saving, automatically scans for Xiaohongshu restricted words — advertising superlatives, competitor platform names, sensitive topics. Suggests safe replacements.

保存前自动扫描小红书敏感词——广告法极限词、竞品平台名、敏感话题。给出安全替换建议。

### 💡 Light content sparks 轻内容灵感
Say "轻内容" or "light" — get 6 quick content ideas based on your profile. Each tagged with mood (self-deprecation, resonance, spicy, warm...). Chat about it or generate directly.

说"轻内容"——生成6条灵感，带情绪标签。可以展开聊，也可以直接出短笔记。

### 📋 Drafts & journal 草稿箱
All posts auto-saved with metadata (date, platform, type, status, word count). Say "草稿箱" to browse, "统计" to see your creation stats, "发了" to mark as published.

所有笔记自动保存，带完整元数据。说"草稿箱"浏览、"统计"看数据、"发了"标记已发布。

### 🌏 Bilingual 双语
Generate Chinese posts for Xiaohongshu AND English threads for X/Twitter — not translations, but platform-native versions of the same insight. Say "双语" or "bilingual".

同一个观点，生成小红书中文笔记和Twitter英文Thread——不是翻译，是各自适配平台语感的原生版本。

### 📱 Mobile via Dispatch 手机使用
With Claude Dispatch, you can do all of this from your phone. Your desktop runs the skill; your phone is the remote control.

通过 Dispatch，以上所有功能都可以在手机上完成。桌面执行，手机遥控。

---

## Install 安装

### Claude Code

```bash
# Clone 克隆
git clone https://github.com/[your-username]/content-copilot.git ~/projects/content-copilot

# Symlink to skills directory 软链接到技能目录
ln -s ~/projects/content-copilot ~/.claude/skills/content-copilot
```

### OpenClaw

```bash
git clone https://github.com/[your-username]/content-copilot.git ~/skills/content-copilot
```

---

## First run 首次使用

Open Claude Code and say "写笔记" or "write a post". The skill walks you through a 2-minute setup:

打开 Claude Code 说"写笔记"。首次使用会引导你做2分钟的个人设置：

1. **Who are you 你是谁** — your background and expertise 你的背景和专长
2. **Your niche 你的领域** — AI, business, food, fitness... 任何方向
3. **Your style 你的风格** — spicy? warm? analytical? 犀利？温暖？深度？
4. **Your platforms 你的平台** — Xiaohongshu, Twitter, or both 小红书、推特或两者
5. **Your language 你的语言** — English, Chinese, or bilingual 英文、中文或双语

Then say "热点" to start. 然后说"热点"开始。

---

## Quick commands 快捷指令

| Command 指令 | What it does 功能 |
|:---|:---|
| `热点` / `trending` | Search trending topics 搜热点 |
| `轻内容` / `light` | Get content sparks 轻内容灵感 |
| `出笔记` / `draft it` | Generate post 生成笔记 |
| `再犀利一点` / `sharper` | Revise a section 修改段落 |
| `OK` / `可以了` | Compliance check → save 合规检查→保存 |
| `复制` / `copy` | Copy to clipboard 复制到剪贴板 |
| `双语` / `bilingual` | Output both languages 双语输出 |
| `草稿箱` / `drafts` | Browse saved drafts 浏览草稿 |
| `发了` / `published` | Mark as published 标记已发布 |
| `统计` / `stats` | Creation stats 创作统计 |
| `下一篇` / `next` | New topic 开始新话题 |
| `收工` / `done` | End session 结束今天 |
| `修改资料` / `update profile` | Edit your settings 修改个人设置 |

---

## Workflow 工作流

```
Chat 聊天 → Generate 生成 → Edit in chat 对话内编辑 → "OK" → Compliance 合规检查 → Save 保存
```

---

## Post structure 笔记结构

### Xiaohongshu 小红书 (600-800 chars)

| Section 段落 | Weight 比重 | Purpose 作用 |
|:---|:---|:---|
| Hook 钩子 | ~10% | Lead with your sharpest take 先亮判断 |
| Context 背景 | ~15% | What happened 热点是什么 |
| Why 意义 | ~15% | Why it matters 为什么重要 |
| Analysis 分析 | ~40% | Your unique angle 深度分析（核心） |
| Action 行动 | ~20% | What the reader should do 读者该怎么办 |

Core principle 核心原则：**Your voice, the copilot's structure. 声音是你的，骨架是结构的。**

### X/Twitter thread (3-7 tweets)

```
🧵 Hook → Context → Insight → Evidence → Implication → Closing question
```

### Light content 轻内容 (300-500 chars)

```
Small story 小场景 → Observation 观察 → Reader takeaway 读者启发
```

---

## Customization 自定义

Everything is configurable through conversation:

所有设置都可以通过对话修改：

| You say 你说 | What happens 效果 |
|:---|:---|
| "I changed jobs" / "我换工作了" | Updates your profile 更新个人信息 |
| "Make posts shorter" / "写短一点" | Adjusts length 调整字数 |
| "Add LinkedIn" / "加一个公众号" | Adds platform 添加平台 |
| "Match this style" / "学这个风格" | Learns your voice 学习你的风格 |
| "Don't mention XX" / "别提XX" | Adds to avoid list 加入屏蔽词 |

---

## Drafts sync 草稿同步

Drafts auto-save to `~/.content-copilot/drafts/`. Symlink to a cloud drive for cross-device access:

草稿自动保存到 `~/.content-copilot/drafts/`。软链接到云盘即可跨设备访问：

```bash
# iCloud (Mac)
ln -s ~/Library/Mobile\ Documents/com~apple~CloudDocs/content-copilot-drafts ~/.content-copilot/drafts

# Dropbox
ln -s ~/Dropbox/content-copilot-drafts ~/.content-copilot/drafts
```

---

## Example profiles 示例用户

<details>
<summary>🤖 AI & Business professor AI+商业教授</summary>

```json
{
  "name": "Wei Yang",
  "identity": "Associate Professor of Management at CEIBS",
  "topics": ["AI & Technology", "Business & Management"],
  "unique_angle": "Using classic management theories to decode AI disruption",
  "style": "Spicy hot takes backed by academic rigor",
  "platforms": ["xiaohongshu", "twitter"],
  "language": "bilingual"
}
```
</details>

<details>
<summary>🍳 Food creator 美食创作者</summary>

```json
{
  "name": "Mia",
  "identity": "Food photographer & recipe developer",
  "topics": ["Food & Lifestyle"],
  "unique_angle": "The science behind why home cooking fails",
  "style": "Warm & relatable with occasional spicy truths",
  "platforms": ["xiaohongshu"],
  "language": "zh"
}
```
</details>

<details>
<summary>🚀 Indie hacker 独立开发者</summary>

```json
{
  "name": "Alex",
  "identity": "Solo founder, building AI tools",
  "topics": ["Startups & Entrepreneurship", "AI & Technology"],
  "unique_angle": "Building in public — radical transparency on revenue and failures",
  "style": "Builder's log — raw, honest, tactical",
  "platforms": ["twitter"],
  "language": "en"
}
```
</details>

---

## Philosophy 理念

> This tool doesn't replace your thinking — it **structures** it.
>
> 这个工具不替代你的思考——它**组织**你的思考。

> Your ideas, your metaphors, your voice — all preserved. The copilot just helps you get from "I have a thought" to "here's a post" in 15 minutes.
>
> 你的想法、你的比喻、你的声音——全部保留。副驾驶只是帮你用15分钟，从"我有个想法"走到"这是一篇笔记"。

---

## Requirements 环境要求

- Claude Code with Max plan (uses Opus, no API cost) 需要 Claude Code Max 订阅
- Or Claude Code with any plan + API key 或任何方案 + API key
- Mobile: Claude app with Dispatch enabled 手机端：Claude app 开启 Dispatch

## License 许可

MIT
