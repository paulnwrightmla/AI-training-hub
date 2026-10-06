# AI Literacy Hub

An interactive training hub for university staff and students on understanding and using generative AI well. It has six modules. Each one has a film, the full transcript, an exercise the learner completes on the page, and a reflection with separate prompts for students and staff.

Open `index.html` in a browser, or host the folder on any static web host (GitHub Pages, SharePoint, a university web server). It needs no build step.

## Adding the films

Every module shows a "coming soon" holding space until you add its film. Open `index.html`, find the `VIDEOS` block near the top of the script, and fill in `src` for each module:

```js
const VIDEOS = {
  1: { src: "videos/module-1.mp4", captions: "videos/module-1.vtt", poster: "" },
  2: { src: "https://youtu.be/XXXXXXXXXXX", captions: "", poster: "" },
  3: { src: "https://your-university.hosted.panopto.com/Panopto/Pages/Embed.aspx?id=...", captions: "", poster: "" },
  ...
};
```

`src` accepts:

- **A video file** placed in the `videos/` folder (`.mp4`, `.webm`, `.m4v`). You can add a WebVTT `captions` file and a `poster` image.
- **A YouTube or Vimeo link.** Ordinary share links are converted to embeds automatically.
- **Any other embed link**, such as Panopto, Microsoft Stream or Kaltura.

## What's in the folder

| Path | Contents |
| --- | --- |
| `index.html` | The whole hub: content, styles and interactions |
| `videos/` | Put your film files here |
| `resources/transcripts/` | The original module transcripts (Markdown). The hub embeds these, so if you edit one, paste the change into `TRANSCRIPTS` in `index.html` too. |
| `resources/exercises/` | The original exercise sheets (Word), linked from each module |

## Features

- A Student/Staff switch that changes the reflection prompts and the Module 4 redesign task
- Exercise steps that learners tick off, prompts with copy buttons, and recording tables they fill in on the page
- Exercise tools: a green/amber/red highlighter (Module 3), an AI-use declaration builder (Module 5), and a 15-minute writing timer with spellcheck off (Module 6)
- A transcript search, a progress tracker, and a toolkit with TRACE-AI, the AI-use dial, the four-question audit and a glossary
- Progress and notes are saved only in the learner's own browser. **Copy all my notes** puts a module's answers on the clipboard so learners can keep them.
