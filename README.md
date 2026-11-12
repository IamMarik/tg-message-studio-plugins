# Message Studio — Telegram Message Formatting & Preview

Telegram UI Lab is a Telegram bot for previewing HTML, MarkdownV2, Rich Markdown and Rich HTML messages in a real chat.
Use the **tg-rich** AI skill to prepare Rich Messages with headings, tables, images and buttons,
then preview and share the result.

**[Open Telegram UI Lab →](https://t.me/ui_lab_bot)** · **[Get the tg-rich skill →](skills/tg-rich/SKILL.md)**

Telegram UI Lab helps bot developers, channel authors and anyone preparing formatted Telegram
messages check how their source renders before sharing it. The bot has English and Russian interfaces.

## Quick start

1. Open **[@ui_lab_bot](https://t.me/ui_lab_bot)** and press **Start**.
2. Open `/converter`. Rich HTML is the default; choose another format if your source uses it.
3. Paste your HTML, Markdown or plain text. Each message gets its own preview.
4. Use **View / Source** to inspect the result and its markup, then copy or forward the message.

Open `/gallery` for formatting examples, a Rich Text Showcase and a shareable promo template.
Open `/help` for a format reference and AI formatting instructions.

## What you can do

| Format | Command | Use it for |
| --- | --- | --- |
| HTML | `/html` | Telegram text formatting with tags such as `<b>` and `<i>` |
| MarkdownV2 | `/md` | Telegram's MarkdownV2 syntax and escaping |
| Rich Markdown | `/richmd` | Headings, lists, tables, media, buttons and expandable sections |
| Rich HTML | `/richhtml` | Structured Rich Messages written with HTML tags |
| Plain text | `/plain` | Viewing text exactly as written |

You can also forward an existing Telegram message to extract its text or caption as editable
source. Rich Messages offer Rich HTML, Rich Markdown, plain text and Telegram JSON exports.
Download source files or preview a supported export directly. Rich media and unsupported Rich
blocks remain available in JSON instead of markup.

## Format messages with AI

**[tg-rich — Telegram Rich](skills/tg-rich/SKILL.md)** is an AI skill that turns your text or message
idea into ready-to-paste Rich Markdown or Rich HTML. It preserves your language and meaning and
defaults to Rich HTML when you do not specify a format. The skill needs no API keys or scripts.

### Install in Codex

Add the marketplace from a terminal:

```bash
codex plugin marketplace add IamMarik/tg-message-studio-plugins
```

In Codex, open **Plugins**, select **Message Studio**, and choose **Install**. In Codex CLI,
you can also run `codex plugin add message-studio@message-studio`.
The plugin includes the `tg-rich` skill, shown as **Telegram Rich**, and the Message Studio MCP server.

1. In Codex, open **Settings → MCP servers** and select **Authenticate** for Message Studio.
2. In the browser, select **Open Telegram**, match the code and approve the connection in the bot.
3. Return to Codex and ask it to read `tg-message-studio://guide` to check the connection.

Open `/mcp` in [@ui_lab_bot](https://t.me/ui_lab_bot) to allow Codex to read retained inputs or
disconnect your Codex sessions. To update an earlier installation, run
`codex plugin marketplace upgrade message-studio`, then install Message Studio again.

The skill can format messages before you connect MCP. To install the skill by itself, send this
request **in Codex chat**:

```text
$skill-installer Install the skill from https://github.com/IamMarik/tg-message-studio-plugins/tree/main/skills/tg-rich
```

Then use it with your own text or brief, for example:

```text
$tg-rich Format a Telegram announcement: our design workshop starts Friday at 18:00. Include a checklist: notebook, pen and laptop.
```

Other AI assistants with skill support can install the [tg-rich folder](skills/tg-rich) using
their own installation workflow. For a single conversation, give an assistant that can read links
the [raw SKILL.md](https://raw.githubusercontent.com/IamMarik/tg-message-studio-plugins/main/skills/tg-rich/SKILL.md)
and ask it to follow the instructions with your text.

Copy the contents of the generated code block and send them to
[@ui_lab_bot](https://t.me/ui_lab_bot) to preview the result. The bot starts in Rich HTML;
if you changed modes, select `/richhtml` for Rich HTML or `/richmd` for Rich Markdown.
Omit the outer backticks and language label. If the AI returns several messages, send each block separately.

See the [official Codex skills guide](https://learn.chatgpt.com/docs/build-skills#install-curated-skills-for-local-use)
for installation details.

## Example: a Rich HTML message

Select `/richhtml` in [Telegram UI Lab](https://t.me/ui_lab_bot), then paste this example:

````html
<h2>A message worth sharing</h2>
<p><b>Your text</b>, with a little more structure.</p>
<ul>
<li>Highlight what matters.</li>
<li>Keep the next step clear.</li>
</ul>

<details><summary>Message ingredients</summary>

<table>
<tr><th>Ingredient</th><th>Details</th></tr>
<tr><td>Text</td><td>Yours</td></tr>
<tr><td>Formatting</td><td><b>Rich</b></td></tr>
<tr><td>Result</td><td>Ready to forward</td></tr>
</table>

</details>

<tg-button-row align="center">
<tg-button type="url" style="primary" url="https://t.me/ui_lab_bot">Try Telegram UI Lab</tg-button>
</tg-button-row>
````

This example combines a heading, bold text, a list, a table inside a collapsed section and a Rich URL button.
Explore `/gallery` in the bot for more examples and their Rich HTML / Rich Markdown sources.

## Frequently asked questions

### How can I preview Telegram HTML?

Open [@ui_lab_bot](https://t.me/ui_lab_bot), select `/html` and send markup such as
`<b>Hello</b>`. For structured content with headings or tables, choose `/richhtml`.

### Is Rich Markdown the same as MarkdownV2?

They are separate formats. Rich Markdown uses `**bold**` and `*italic*` and supports structured
Rich Messages. MarkdownV2 uses `*bold*` and `_italic_` and has its own escaping rules.
Choose the bot mode that matches your source.

### How can I format a Telegram message with AI?

Install `tg-rich` in an assistant with skill support, or share its instructions with your AI.
Ask for Rich Markdown or Rich HTML, then preview the generated source in Telegram UI Lab.
AI formatting runs in your own assistant; the bot renders the source in Telegram.

### Can I get HTML or Markdown from a forwarded Telegram message?

Forward the message to the bot and choose an export format. Ordinary text and captions offer
HTML and MarkdownV2; Rich Messages offer Rich HTML and Rich Markdown for supported content.
Telegram JSON is available when you need the received message structure.

## Public resources

This repository contains the **Message Studio Codex plugin**, the **tg-rich skill**, and public media.
Use the bot at **[t.me/ui_lab_bot](https://t.me/ui_lab_bot)** to preview messages.

- [`skills/tg-rich/`](skills/tg-rich) — portable Rich Message formatting instructions and Codex display metadata.
- [`statham.jpg`](statham.jpg) — portrait used in the bot's promo example.

Rich syntax references: [Rich Markdown](https://core.telegram.org/bots/api#rich-markdown-style)
and [Rich HTML](https://core.telegram.org/bots/api#rich-html-style).

Maintained by [@IamMarik](https://github.com/IamMarik).
