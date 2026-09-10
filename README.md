# StudyOS

> **A premium AI-powered study workspace built for focused learning.**

StudyOS is a single-page, browser-based AI study environment designed to
bring conversations, study tools, notes, voice input, mathematical
rendering, personalization, and workspace controls into one clean
interface.

------------------------------------------------------------------------

## ✨ Highlights

-   🤖 **AI study assistant powered by Groq**
-   🔄 **Live Groq model discovery**
-   🔐 **Primary + Secondary API slots**
-   🛟 **Automatic API fallback**
-   🧮 **KaTeX mathematical rendering**
-   🎙️ **Voice input**
-   🔊 **Live Voice mode**
-   📝 **Notes and workspace memory**
-   📎 **File/image-aware conversations**
-   🎨 **Customizable backgrounds and appearance**
-   👤 **Profile personalization**
-   ⚡ **Streaming-style answer animation**
-   📱 **Responsive mobile layout**
-   🖥️ **Desktop-friendly workspace**
-   💾 **Browser-local workspace persistence**
-   📤 **Workspace data export**

------------------------------------------------------------------------

## 🚀 What is StudyOS?

StudyOS is built around one idea:

> **Make studying feel like using a serious productivity system, not
> just opening a chatbot.**

Instead of separating your AI assistant, notes, preferences, voice
tools, and study workflow across multiple apps, StudyOS puts them
together in one focused interface.

The application is delivered as a single HTML page and can be used
directly in a modern browser.

------------------------------------------------------------------------

## 🧠 AI System

StudyOS connects directly to the Groq API from the browser.

### Primary + Secondary API

StudyOS supports two independent API connections:

  Connection      Purpose
  --------------- --------------------
  **Primary**     Main AI connection
  **Secondary**   Backup connection

When both are configured:

``` text
User
  ↓
StudyOS
  ↓
Primary Groq API
  │
  ├── Success ──→ Answer
  │
  └── Failure
        ↓
   Secondary Groq API
        ↓
      Answer
```

This provides a simple fallback mechanism when the primary connection is
unavailable or rejected.

### Live Model Fetching

StudyOS can query Groq's model endpoint and build its model selector
from the models available to the configured API keys.

The interface also indicates whether a model is available through the
Primary connection, Secondary connection, or both.

------------------------------------------------------------------------

## 🧮 Mathematics

StudyOS uses **KaTeX** for mathematical rendering.

For a fully local KaTeX setup, keep the following structure next to the
HTML file:

``` text
StudyOS/
├── StudyOS_Premium_Chat_First.html
└── katex/
    ├── katex.min.css
    ├── katex.min.js
    ├── contrib/
    │   └── auto-render.min.js
    └── fonts/
        └── KaTeX font files
```

The application references KaTeX locally:

``` html
<link rel="stylesheet" href="./katex/katex.min.css">
<script defer src="./katex/katex.min.js"></script>
<script defer src="./katex/contrib/auto-render.min.js"></script>
```

This allows the mathematical rendering layer to work without relying on
a KaTeX CDN.

StudyOS is designed to handle common LaTeX forms such as:

``` latex
\(F = ma\)
```

``` latex
\[
E = mc^2
\]
```

``` latex
\(\mathbf{F}_{AB} = -\mathbf{F}_{BA}\)
```

``` latex
\[
\boxed{r_s = \frac{2GM}{c^2}}
\]
```

------------------------------------------------------------------------

## 🎙️ Voice

StudyOS includes browser-based voice interaction features.

### Voice Input

The microphone control can capture speech and send it for transcription
through the configured Groq connection.

### Live Voice

Live Voice is an explicit mode rather than an automatic behavior.

Normal AI answers do **not** automatically start speaking.

When Live Voice is activated, StudyOS can use speech recognition and
speech synthesis as part of the voice interaction flow.

------------------------------------------------------------------------

## 🎨 Personalization

StudyOS includes a dedicated Settings workspace.

### Profile

You can configure:

-   Name
-   Pronouns
-   Assistant name

These preferences can be used by the assistant when generating
responses.

### Background

Available background styles include:

-   Default
-   Midnight
-   Nebula
-   Sunset
-   Plain
-   Custom color

### Appearance

The workspace also provides controls for visual presentation, including:

-   Theme
-   Accent
-   Font
-   Glass intensity
-   Animations
-   Compact mode
-   Smooth scrolling

------------------------------------------------------------------------

## 💬 Workspace

StudyOS keeps the study experience organized around conversations and
workspace data.

The application stores relevant workspace state in the browser using
`localStorage`, including items such as:

-   Conversations
-   Current conversation
-   Memories
-   Notes
-   User preferences
-   API/model settings

This means the workspace can persist between browser sessions on the
same device and browser.

------------------------------------------------------------------------

## 📤 Data Export

StudyOS provides a workspace export option.

Exported workspace data can include:

-   Settings
-   Conversations
-   Memories
-   Notes

API keys are intentionally excluded from the exported settings data.

------------------------------------------------------------------------

## 📱 Responsive Design

StudyOS is designed to work across desktop and mobile screen sizes.

### Desktop

The desktop layout provides:

-   Sidebar navigation
-   Large conversation area
-   Model controls
-   Spacious message composer
-   Full settings interface

### Mobile

The responsive layout adapts the interface for smaller screens with:

-   Mobile navigation behavior
-   Touch-friendly controls
-   Responsive composer
-   Full-width conversation space
-   Mobile-friendly settings
-   Horizontal scrolling for wide code/table content
-   Reduced spacing where necessary

No separate mobile HTML file is required.

------------------------------------------------------------------------

## 🛠️ Local Usage

StudyOS can be used directly as an HTML application.

### 1. Get the project

Keep the main HTML file and local KaTeX directory together:

``` text
StudyOS/
├── StudyOS_Premium_Chat_First.html
└── katex/
```

### 2. Open the HTML file

Open:

``` text
StudyOS_Premium_Chat_First.html
```

in a modern browser.

### 3. Configure the AI

Open **Settings → AI Connections** and enter your Groq API key.

You can configure:

-   Primary API key
-   Secondary API key

Then use the live model selector to choose an available model.

------------------------------------------------------------------------

## 🔑 API Key Security

StudyOS currently stores configured API keys in the browser's
`localStorage` and sends requests directly from the browser to the Groq
API.

This is convenient for a personal/local application, but it is **not the
recommended architecture for a public application**.

### For personal/local use

This architecture can be acceptable if you understand that the API key
is stored on the device.

### For public deployment

A safer production architecture is:

``` text
Browser
   ↓
Your Backend
   ↓
Groq API
```

The backend should keep API keys server-side instead of exposing them to
the browser.

**Never publish a real API key inside the HTML source or Git
repository.**

------------------------------------------------------------------------

## 📦 Project Structure

A recommended local structure is:

``` text
StudyOS/
│
├── StudyOS_Premium_Chat_First.html
│
└── katex/
    ├── katex.min.css
    ├── katex.min.js
    │
    ├── contrib/
    │   └── auto-render.min.js
    │
    └── fonts/
        └── *.woff2
```

------------------------------------------------------------------------

## 🔧 Main Technologies

StudyOS is a front-end web application built around:

-   **HTML**
-   **CSS**
-   **JavaScript**
-   **Groq API**
-   **KaTeX**
-   **Marked**
-   **DOMPurify**
-   **Tesseract.js**
-   **PDF.js**
-   **Lucide icons**
-   **Browser Web APIs**
-   **localStorage**

Some dependencies are loaded externally by the application, while KaTeX
can be supplied entirely from the local `katex/` directory.

------------------------------------------------------------------------

## 🧩 Core Architecture

At a high level:

``` text
                         ┌──────────────────┐
                         │     StudyOS      │
                         │   Single HTML    │
                         └────────┬─────────┘
                                  │
          ┌───────────────────────┼───────────────────────┐
          │                       │                       │
          ▼                       ▼                       ▼
     AI / Groq                 Workspace               UI Layer
          │                       │                       │
   ┌──────┴──────┐          ┌─────┴─────┐        ┌───────┴───────┐
   │   Primary   │          │   Chats   │        │   Desktop     │
   │   Secondary │          │   Notes   │        │   Mobile      │
   └─────────────┘          │ Memories  │        │   Settings    │
                            └───────────┘        └───────────────┘
                                  │
                                  ▼
                             localStorage
```

------------------------------------------------------------------------

## 🌟 Design Philosophy

StudyOS aims for a balance between:

**Clean UI + powerful functionality + low setup friction**

The interface is intentionally designed around a dark, glass-inspired
aesthetic with focused spacing, compact controls, animated feedback, and
a study-oriented workspace rather than a generic chatbot layout.

------------------------------------------------------------------------

## ⚠️ Browser Requirements

For the best experience, use a modern browser with support for:

-   JavaScript
-   `fetch()`
-   `localStorage`
-   Web Speech APIs where available
-   Microphone permissions for voice features
-   Camera permissions if camera-based functionality is enabled
-   Modern CSS features

Some browser features, especially microphone/camera access, may require
a secure context such as `https://` or `localhost`.

------------------------------------------------------------------------

## 🐛 Troubleshooting

### Models are not appearing

1.  Open **Settings → AI Connections**
2.  Check the Primary/Secondary API key
3.  Save the connection
4.  Refresh the model inventory
5.  Confirm the selected model is available through one of the
    configured keys

### Mathematics is not rendering

Check that the local KaTeX structure exists:

``` text
katex/
├── katex.min.css
├── katex.min.js
├── contrib/
│   └── auto-render.min.js
└── fonts/
```

Also make sure the HTML is being opened with the expected relative
folder structure.

### Voice is not working

Check:

-   Microphone permission
-   Browser support
-   Available Groq connection
-   Network access
-   Browser console errors

### Workspace data disappeared

StudyOS stores workspace data locally in the browser. Clearing
site/browser storage, changing browser profiles, or using a different
device can result in a different workspace.

Use the built-in export feature to keep a backup of important workspace
data.

------------------------------------------------------------------------

## 🔒 Privacy Note

StudyOS is primarily a browser-side application.

Depending on the feature being used, information can be sent to external
services such as the configured Groq API or other loaded processing
services.

Do not enter sensitive personal information or confidential data unless
you understand where that information is being processed.

------------------------------------------------------------------------

## 📜 License

No explicit open-source license is currently defined by this project.

Unless a license is added to the repository, the source should be
treated as **all rights reserved**.

------------------------------------------------------------------------

## 👨‍💻 Project

**StudyOS**

A focused AI study workspace built around the idea that learning tools
should feel like a complete environment rather than a collection of
disconnected utilities.

------------------------------------------------------------------------

### Built with curiosity. Designed for studying. ⚡
