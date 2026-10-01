# Spitball

Spitball is a Markdown-first framework for thinking and writing. You dump raw thoughts into files without worrying about how they read. Over time they build up into a corpus of your thinking. Claude Code then helps you find, connect, and synthesize that corpus into real writing, in styles you define.

It's just folders of Markdown. It works as an Obsidian vault, and you don't need any plugins. Nothing else is required, either. `CLAUDE.md` holds the detailed rules Claude follows.

## The three parts

| Folder | Question | Contents |
|---|---|---|
| `thoughts/` | *What do I think?* | Raw, messy, unedited thoughts. Everything in one flat folder. |
| `projects/` | *What am I trying to say?* | One folder per project, from a short post to a book. Structure develops here. |
| `style/` | *How should I say it?* | Reusable writing-style profiles. |

## Capturing a thought

**In Obsidian:** open this folder as a vault and press **Ctrl/Cmd+N**. New notes go into `thoughts/` automatically. Then just type. No title, formatting, or tags needed.

**Through Claude:** say *"Create a new thought."* You get `thoughts/YYYY-MM-DD-NNN.md` with this frontmatter:

```markdown
---
type: thought
created: 2026-09-29
tags: []
related: []
---

start typing here...
```

Frontmatter is optional when you write. If a note doesn't have any, Claude adds it later. If you'd rather dictate, tell Claude the text and it will save it word for word.

## Tagging

Say *"Tag my untagged thoughts."* Claude reads them and adds a few conceptual tags, reusing existing tags wherever they fit. Where two thoughts are actually connected, it also adds `related` links between them. Claude **only touches the frontmatter** and never changes what you wrote. If tags start overlapping, Claude suggests merging them and waits for your approval.

## Styles

A style is a readable profile in `style/<name>.md`. It covers tone, sentence rhythm, paragraphing, how arguments develop, what to avoid, and so on. You can build one from:

- **a description:** *"Create a philosophical essay style: plain, patient, first person, few hedges."*
- **writing samples:** paste your samples or point Claude at the files.
- **references:** authors, books, or genres. Claude pulls out the underlying characteristics rather than imitating anyone.
- **any combination** of the three.

Edit style files by hand whenever you like.

## Projects

Say *"Create a project about X."* Claude creates `projects/<name>/PROJECT.md`. That file is where you state the format, objective, audience, style, central questions, and constraints, and you only need to fill in what applies. A small essay gets `PROJECT.md` plus `draft.md`. A book adds an outline, source-thought lists, thematic synthesis notes, and chapters, but only as they become useful.

Then work with it:

- *"Develop this project's ideas from my thoughts."* Claude reports the key ideas, tensions, gaps, and a proposed thesis.
- *"Create an outline."*
- *"Draft the essay."* / *"Draft chapter 2."*

Each project records which raw thoughts contributed to it. That provenance lives in `PROJECT.md` or `source-thoughts.md`, not in the prose. Generated files are marked `generated: true`, so Claude's interpretations never get mixed up with your own record.

## Two rules to know

1. **Your raw thoughts are never edited.** Claude doesn't correct, tidy, summarize, or rewrite the body of a thought unless you explicitly ask it to change that specific thought. Only the frontmatter is maintained.
2. **Your corpus is the only intellectual source by default.** Claude doesn't bring in outside facts, quotes, history, or arguments to strengthen your writing. It can reason *across* your thoughts, and it labels those inferences. When something is missing, it leaves a `[gap: …]` marker rather than filling it in. If you want outside research, ask for it explicitly.

Contradictions and changes of mind in your thinking are brought to your attention, not smoothed over.

## Example requests

- "Create a new thought."
- "Tag my untagged thoughts."
- "What have I written about ritual?"
- "Find connections between my thoughts about technology and religion."
- "Look for contradictions in my thinking about secularization."
- "Create a style based on these writing samples: …"
- "Create a project: a Substack essay about why rituals outlast beliefs."
- "Develop this project's ideas from my thought corpus, then create an outline."
- "Draft the essay in my plain-essay style."
- "What raw thoughts contributed to the argument in section 2?"
- "Update this project with relevant thoughts I've written since we last worked on it."

## Source of truth

Everything important is a Markdown file: thoughts, styles, projects, drafts, and provenance. There's no database and no hidden state. The only extra file is `.obsidian/app.json`, which points new Obsidian notes at `thoughts/`. It's optional.
