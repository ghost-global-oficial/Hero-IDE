[README.md](https://github.com/user-attachments/files/26089719/README.md)
<div align="center">

<br />

```
██╗  ██╗███████╗██████╗  ██████╗
██║  ██║██╔════╝██╔══██╗██╔═══██╗
███████║█████╗  ██████╔╝██║   ██║
██╔══██║██╔══╝  ██╔══██╗██║   ██║
██║  ██║███████╗██║  ██║╚██████╔╝
╚═╝  ╚═╝╚══════╝╚═╝  ╚═╝ ╚═════╝
```

**AI-Powered IDE — Built for Speed. Built for Devs.**

[![VS Code](https://img.shields.io/badge/VS%20Code-Extension-007ACC?style=flat-square&logo=visual-studio-code)](https://code.visualstudio.com/)
[![OpenRouter](https://img.shields.io/badge/OpenRouter-Multi--Model-6C47FF?style=flat-square)](https://openrouter.ai/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.x-3178C6?style=flat-square&logo=typescript)](https://www.typescriptlang.org/)
[![License](https://img.shields.io/badge/License-MIT-22c55e?style=flat-square)](LICENSE)

<br />

</div>

---

## What is Hero?

**Hero** is a VS Code extension that brings a full AI coding assistant directly into your editor — no browser tab switching, no context loss. It combines a persistent chat panel, an autonomous agent mode, multi-model selection via OpenRouter, and inline ghost text completions into a single, cohesive experience.

Think Cursor or GitHub Copilot, but without the lock-in.

---

## Features

### 🤖 Agent Mode
Hero can autonomously plan and execute multi-step tasks — reading files, running terminal commands, applying edits, and iterating — until the goal is complete. You stay in control; Hero does the legwork.

### 💬 Chat Panel
A native side panel inside VS Code for contextual conversations with your codebase. Reference files, ask about errors, request refactors — all without leaving the editor.

### 🔀 Multi-Model Selector
Switch between models on the fly via [OpenRouter](https://openrouter.ai/). Use GPT-4o for reasoning, Claude for long context, Mistral for speed — whichever fits the task.

### 👻 Inline Ghost Text Completions
Real-time completions that appear inline as you type, just like Copilot. Accept with `Tab`, dismiss with `Escape`.

### 🗂️ Context-Aware
Hero understands your workspace: open files, active selection, terminal output, and diagnostics are automatically included in context.

---

## Installation

### From VSIX (manual)

```bash
# Clone the repo
git clone https://github.com/your-username/hero.git
cd hero

# Install dependencies
npm install

# Build the extension
npm run build

# Package it
npx vsce package

# Install in VS Code
code --install-extension hero-*.vsix
```

### From VS Code Marketplace

> Coming soon.

---

## Configuration

After installing, open VS Code Settings (`Ctrl+,`) and search for **Hero**.

| Setting | Description | Default |
|---|---|---|
| `hero.apiKey` | Your OpenRouter API key | `""` |
| `hero.defaultModel` | Model used by default | `openai/gpt-4o` |
| `hero.inlineCompletions` | Enable ghost text completions | `true` |
| `hero.agentMode` | Enable autonomous agent capabilities | `true` |
| `hero.maxTokens` | Max tokens per response | `4096` |

**Get your OpenRouter API key at:** [openrouter.ai/keys](https://openrouter.ai/keys)

---

## Usage

### Open the Chat Panel

Press `Ctrl+Shift+H` or click the **Hero** icon in the Activity Bar.

### Agent Mode

Type a goal in natural language — Hero will break it down into steps and execute them autonomously.

```
"Refactor the auth module to use JWT and add refresh token support"
```

### Inline Completions

Just start typing. Ghost text suggestions appear automatically. Press `Tab` to accept.

### Model Switching

Click the model name in the Chat Panel header to open the model picker. Supports any model available on OpenRouter.

---

## Architecture

```
hero/
├── src/
│   ├── extension.ts          # Entry point
│   ├── panel/
│   │   ├── ChatPanel.ts      # Webview panel controller
│   │   └── webview/          # React UI (chat interface)
│   ├── agent/
│   │   ├── Agent.ts          # Autonomous task executor
│   │   └── tools/            # File, terminal, edit tools
│   ├── completions/
│   │   └── InlineProvider.ts # Ghost text completion provider
│   └── ai/
│       └── openrouter.ts     # OpenRouter API client
├── package.json              # Extension manifest
└── tsconfig.json
```

---

## Supported Models (via OpenRouter)

Any model on OpenRouter works. Recommended picks:

| Model | Best For |
|---|---|
| `openai/gpt-4o` | General coding, reasoning |
| `anthropic/claude-sonnet-4-5` | Long context, complex refactors |
| `google/gemini-2.0-flash` | Speed, cost-efficiency |
| `mistralai/mistral-large` | Fast, multilingual |
| `deepseek/deepseek-coder` | Code-specific tasks |

---

## Development

```bash
# Install deps
npm install

# Watch mode (rebuilds on change)
npm run watch

# Open extension host in VS Code
Press F5 in VS Code
```

Run tests:

```bash
npm test
```

---

## Roadmap

- [ ] File tree context picker
- [ ] Git diff awareness
- [ ] Multi-file agent edits with diff preview
- [ ] Custom system prompt per workspace
- [ ] Local model support (Ollama)
- [ ] Command palette integration

---

## Contributing

Pull requests are welcome. For major changes, open an issue first to discuss what you'd like to change.

1. Fork the repo
2. Create a feature branch (`git checkout -b feat/my-feature`)
3. Commit your changes (`git commit -m 'feat: add my feature'`)
4. Push and open a PR

---

## License

[MIT](LICENSE) — free to use, modify, and distribute.

---

<div align="center">

Built with caffeine and stubbornness.

</div>
