# Kimi Translator & Grammar Correction
*this page is mostly written by Kimi(K2.6)*
A lightweight, multiingual translation and grammar correction interface powered by [Moonshot AI (Kimi)](https://www.moonshot.cn). Deployed on Cloudflare Pages with a single-file backend.

[中文](#功能) | [English](#features)

---

## 功能 / Features

- **翻译 / Translate**: 中译英 with three tone presets (Casual / Natural / Formal), plus editable custom instructions
- **语法纠错 / Grammar Check**: Corrects grammar, spelling, punctuation while preserving tone and style
- **双语界面 / Bilingual UI**: 中文 / English switch
- **夜间模式 / Dark Mode**: ☀️/🌙 toggle with localStorage persistence
- **响应式设计 / Responsive**: Works on mobile and desktop

## 页面截图

![日间模式](screenshot-light.jpg)
![夜间模式](screenshot-dark.jpg)

## 技术栈 / Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | Vanilla HTML + CSS + JS |
| Backend | Cloudflare Pages `_worker.js` |
| AI API | Moonshot Kimi API (`kimi-k2.5`) |

## 部署 / Deployment

### 1. 准备文件 / Prepare files

```
your-project/
├── _worker.js        # Backend API proxy
├── translator.html   # Frontend interface
└── index.html        # Your existing homepage (optional)
```

### 2. 上传 to Cloudflare Pages

1. [Cloudflare Dashboard](https://dash.cloudflare.com) → Pages → Create a project
2. **Upload your files** (drag & drop)
3. Deploy

### 3. 设置环境变量 / Set environment variables

Pages Project → Settings → Environment variables:

| Variable | Value |
|----------|-------|
| `KIMI_API_KEY` | Your Moonshot API key (starts with `sk-`) |

### 4. 设置兼容性日期 / Set compatibility date

Pages Project → Settings → Functions → Compatibility date:

- Production: `2026-05-14` (or latest available)

Save and redeploy.

### 5. 访问 / Visit

```
https://your-project.pages.dev/translator.html
```

## 本地测试 / Local testing

Open `translator.html` directly in browser (backend calls will fail without `_worker.js`, but UI works).

## 提示词工程 / Prompt Engineering

(Honestly, you can just look in _worker.js yourself.)
The system prompts are designed for **idiomatic, native-level output**:

- **Translation**: Emphasizes natural tone over literal translation
- **Grammar**: Preserves slang, humor, and intentional awkwardness while fixing errors

Editable user prompts allow real-time style adjustments without code changes.

## 其他

高中生个人尝试，可能有小bug

## License

MIT License — see [LICENSE](./LICENSE) for details.

## Credits

- Powered by [Moonshot AI (Kimi)](https://www.moonshot.cn)
- Interface design by user request
- System prompt written by ChatGPT (GPT-5.5-Instant)
- Built for Cloudflare Pages
