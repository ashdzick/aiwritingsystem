# Writing System Template

A personal writing system for working with AI on content that sounds like you, not like AI. Built around six files that load at the start of every session to give the model the context it needs. *Step by step instructions included at the end, if you need them.*

Read more about how it works at [dzick.com/content/writing-system](https://dzick.com/content/writing-system).

---

## Files in This System

**system-prompt.md** — The startup file. Paste this into your AI tool's system prompt or project instructions. It tells the assistant what to read, how to approach each session, and how to close.

**voice-rules.md** — Your voice document. Covers tone, format, and the non-negotiables for how you write. The more specific this is, the better the output.

**avoid-patterns.md** — Everything that makes your writing sound like it wasn't written by you: phrases, structures, tone signals. Grows over time as you notice patterns.

**writing-samples.md** — Existing writing you're happy with. The model reads these to calibrate to your actual voice, not the average.

**content-calendar.md** — Tracks what you've published, what's coming, and how things performed. Prevents repetition and helps build future content from what's resonating.

**drafts.md** — Holding space for posts in development. Move to `content-calendar.md` once finalized.

---

## How to Get Started

You don't need everything filled in before your first session. Start with these two and build from there:

1. **writing-samples.md** — Add 3 to 6 pieces of writing you're proud of. This is the highest-leverage file. It gives the model an actual target instead of an approximation.
2. **voice-rules.md** — Fill in your voice, tone, and format rules. The more specific the better. "Conversational" is not an instruction. "Write like a smart colleague talking to another smart colleague, not like a consultant writing a report" is.

After that:

3. Fill in **system-prompt.md** — replace the [PLACEHOLDER] fields with your name, platform, and any workflow preferences.
4. Build out **avoid-patterns.md** as you use the system. The End of Session step is specifically designed to help you catch patterns worth adding.
5. Log past content in **content-calendar.md** if you want the model to have historical context from day one. Otherwise, start fresh and log as you go.

---

## How the System Grows

This is not a one-time setup. Every session is an opportunity to refine it. The End of Session step in `system-prompt.md` asks: based on what happened today, should anything be added to `voice-rules.md` or `avoid-patterns.md`? The system gets better as you use it.

---

## Detailed Instructions

### Just Getting Started

If you aren't ready to create a skill, a project, or code, this is for you. Download the files (click on each and then "Download Raw File"). Copy and paste the "System Prompt" text into ChatGPT or Claude. Upload all other files as attachments.

### Use This as a Claude Project

A Claude Project lets you upload your files once and have them available in every writing session automatically. No re-uploading, no copy-pasting prompts. It's the easiest way to use this system if you're on Claude.

1. Go to [claude.ai](https://claude.ai) and create a new Project
2. Open Project Settings and paste the contents of `system-prompt.md` into the Custom Instructions field
3. Upload `voice-rules.md`, `avoid-patterns.md`, and `writing-samples.md` as Project files

Every conversation you start inside the Project will have your voice rules and writing samples loaded automatically. Skip `content-calendar.md` and `drafts.md` — those change too frequently to keep as static uploads. Paste them into the conversation when you need them.

### Turn This Into a Claude Skill

A skill goes one step further than a Project. Once installed, Claude will automatically apply your voice and tone rules to any writing session without you needing to open a specific Project or upload anything.

#### What to include

Your skill needs two things:

A `SKILL.md` file that combines the contents of `voice-rules.md` and `avoid-patterns.md` into a single instruction set, wrapped in this structure:

```markdown
---
name: your-name-writing
description: Your name's personal writing assistant. Use this skill whenever your name asks for help writing, drafting, or editing content. Trigger on phrases like "help me write", "draft a post", "edit this", or when a draft is pasted for feedback.
---

# Your Name's Writing Assistant

[voice-rules.md contents]

[avoid-patterns.md contents]

When drafting, read references/samples.md to calibrate tone.
```

A `references/samples.md` file with 3–6 examples of your own writing that you're proud of. Add a short note to each one explaining what it demonstrates. This is what gives Claude an actual target to aim for — the rules tell it what to avoid, the samples show it what good looks like.

#### How to package and install it

Organize your files like this:

```
your-name-writing/
├── SKILL.md
└── references/
    └── samples.md
```

Compress the folder into a zip file and rename it from `.zip` to `.skill`. Then go to Settings in Claude.ai, find the Skills section, and upload the file.

If you'd rather not do this manually, upload your files to a Claude chat and ask: "Package these into a .skill file for me."

### Use This in a Cowork Session

Cowork is Claude's desktop tool for automating file and task management. This is how the original writing system was built and used. Cowork reads your files directly from your computer, so your content calendar and drafts stay live and in sync rather than being static uploads.

1. Store all six files in a folder on your computer
2. Start a Cowork session and point it to the folder
3. Paste the contents of `system-prompt.md` as your starting instruction

Claude will read the files directly at the start of each session, including your content calendar and drafts in progress. The full session management workflow in `system-prompt.md` — syncing recent posts, checking the calendar, end-of-session reflection — is designed for this setup.
