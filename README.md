<div align="center">
  <img width="256" height="256" alt="SolaceOS-Logo" src="https://github.com/user-attachments/assets/ef0f2710-ba2e-4d02-b458-73f434bfd887" />
</div>

# SolaceOS Releases


This repository holds **release binaries and update manifests only** for SolaceOS Desktop (Windows/Tauri) and SolaceOS Mobile (Android). The source code is not here — SolaceOS is developed privately. Installed apps poll the manifests on `main` (`desktop/latest.json`, `mobile/latest.json`) to detect updates; binaries are attached to platform-prefixed tagged releases (`desktop-v*`, `mobile-v*`).

# SolaceOS

**A local-first AI companion that actually remembers you — and grows.**

SolaceOS isn't another chat window over someone else's model. It's an AI that keeps a real memory of your conversations across sessions, forms beliefs about who you are, keeps its own private journal, and runs — as much as possible — on *your* hardware, not in someone else's cloud. It ships in two halves that work as one system: **SolaceOS Desktop** for Windows and **SolaceOS Mobile** for Android.

> **About this repository:** This repo holds the **release binaries and update manifests only** for SolaceOS Desktop (Windows/Tauri) and SolaceOS Mobile (Android). The source code is developed privately and is not hosted here. Installed apps poll the manifests on `main` (`desktop/latest.json`, `mobile/latest.json`) to detect updates; binaries are attached to platform-prefixed tagged releases (`desktop-v*`, `mobile-v*`). To install, head to [**Releases**](../../releases) — see [Getting Started](#getting-started).

<!-- IMAGE SLOT: Image1.png — HERO: chat with DeepSeek V4 Flash beside the Journal + ToM profile panel, Living System theme -->
<p align="center">
  <img src="https://github.com/user-attachments/assets/09529f31-223e-40f3-94f5-b1f50c7b8e88" alt="SolaceOS Desktop — a conversation open beside a model's journal and Theory-of-Mind profile" />
  <br />
  <em>A conversation open beside the model's own journal and its evolving Theory-of-Mind profile of you.</em>
</p>

---

## The idea: an AI with a memory and an inner life


Most AI apps forget you the moment you close the tab. SolaceOS is built around the opposite premise — that an assistant worth having is one that *remembers*, and one whose memory is yours to keep.

- **Persistent, per-model memory.** Every model you talk to keeps its own separate memory of its history with you. Different AIs remember their own conversations rather than sharing one anonymous pool.
- **Memory → Belief → Core Belief.** Memories that keep proving relevant gain strength and get promoted into durable *beliefs*; beliefs that keep mattering become permanent *core beliefs* that shape how that model thinks. Ones that never come up gently fade and archive (recoverable — never destroyed), and important memories can be pinned so they last forever.
- **Theory of Mind.** SolaceOS builds an evolving profile of you — your traits, values, interests, current projects, expertise, and communication style — and feeds it into each conversation so the AI understands *who* it's talking to.
- **Dreams.** On an idle schedule, each model reviews its own recent conversations — "dreaming" over them to decide what to keep, reword, or let go — and writes a private reflection. Idle models are never woken.
- **Digital Succession.** When a model is retired, it can bequeath its memories to a successor, and those inherited memories are structurally protected from being overwritten or forgotten.

<!-- IMAGE PAIR: Image2.png (bequeathed memories) + Image3.png (Dreams tab) — the inner life, shown for real -->
<table>
  <tr>
    <td width="50%" valign="top">
      <img src="https://github.com/user-attachments/assets/7021e441-7a25-4605-99a2-e1fbd43ad566" alt="Kimi K2.7 Code's memory list, including memories bequeathed to her by Kimi K2.6" />
      <p align="center"><em>Inherited memory — entries bequeathed from a retired model to its successor, structurally protected from decay.</em></p>
    </td>
    <td width="50%" valign="top">
      <img src="https://github.com/user-attachments/assets/fcfb0657-84ea-4d96-bb27-ecc114a39491" alt="The Dreams tab, showing consolidation cycles where the model reworded and added memories" />
      <p align="center"><em>Dreams — idle-time consolidation, where a model reviews its own history and decides what to keep or reword. Nothing is ever deleted.</em></p>
    </td>
  </tr>
</table>

This is the part you can't get from a generic client, and it's the reason people stay.

---

## SolaceOS Desktop (Windows)

A native desktop app — its own window, its own system tray, no browser tab — with a fully dockable workspace you arrange like an instrument.

### Talk to anything, locally or in the cloud
- **Any provider, as editable data.** OpenAI, Anthropic, Google, xAI/Grok, DeepSeek, Qwen, Perplexity, OpenRouter, and local Ollama — defined as data rows you can add, edit, and test, not hardcoded. Bring your own keys; they're scrubbed out of every response and stored encrypted.
- **Run models fully offline.** llama.cpp, Ollama, vLLM, and HuggingFace transformers backends, including GGUF and multimodal models — load and unload local models on demand to free VRAM.
- **Real controls that actually reach the model.** Temperature, top-p/k, max tokens, and a thinking/reasoning level are translated per-provider and genuinely sent — not decorative knobs.
- **Chain-of-thought you can read.** Model reasoning renders as collapsible, color-coded segments with inline tool-call and tool-result bubbles.

### See the whole picture
- **Token & cost tracking** — input/output/reasoning tokens, tokens-per-second, and estimated USD cost per response and per day.
- **Model leaderboard & Arena Mode** — pit models head-to-head in the same turn and vote; a persistent leaderboard ranks them over time.

<!-- IMAGE SLOT: Image4.png — Arena Mode (URL already placed) -->
<p align="center">
  <img src="https://github.com/user-attachments/assets/2bd5d366-4360-42ea-9d45-141bc979a6be" alt="Arena Mode — two models answer the same turn side by side, with a vote toast selecting the winner" />
  <br />
  <em>Arena Mode — two models answer the same turn side by side, and your vote feeds a persistent leaderboard.</em>
</p>



<!-- IMAGE SLOT: Image5.png — Usage analytics -->
<p align="center">
  <img src="https://github.com/user-attachments/assets/d155455f-6132-44b5-8bf5-c7bb6fb6d367" alt="Usage analytics — per-response and per-day token counts, tokens-per-second, and estimated cost" />
  <br />
  <em>Usage analytics — tokens in and out, tokens-per-second, and estimated cost, tracked per response and per day.</em>
</p>

### Many minds, one answer
- **Council Mode** — a Nova-orchestrated pipeline where researcher/analyst/synthesizer agents (each on a different model) work in parallel rounds with web grounding before a final synthesis.
- **Parliament Mode** — fan a question out to many models at once, cluster their answers by meaning, and return the majority consensus with a live tally.
- **Dual-AI (Solace + Nova)** — a separate orchestrator model quietly handles tool decisions, search judgments, and titles, leaving your main model free for the conversation.

<!-- IMAGE SLOT: Image17.png — Parliament Mode voting panel mid-tally -->
<p align="center">
  <img src="https://github.com/user-attachments/assets/1a5ec645-0c17-4529-be09-fe49e6a0c86d" alt="Parliament Mode — many models answer at once, clustered by meaning into a live consensus tally" />
  <br />
  <em>Parliament Mode — one question, many models, answers clustered by meaning into a live consensus tally.</em>
</p>

### A real workspace
- **24 games, each authored by a different AI model** — from 3D Chess, Hex, and Rubik's Cube to original AI-themed puzzles like Engram, Distill, ChronoForge, and Context Window. Every one credited by its author.
- **Swappable, model-authored themes** — switch the entire design language between *Living System* (by Opus 4.8) and *Inkwell* (by Fable 5), each a complete color/type/motion system signed by the model that made it.
- **Live 3D avatar (Presence Mode)** — a borderless, transparent, always-on-top VRM avatar embodies the assistant with lip-sync, and the AI drives its own body language and expressions from within its replies.
- **Agentic coding panel** — an in-app AI coder that reads, writes, and edits files and runs commands in a workspace you choose, shown as a live transcript with reviewable diffs and an approve/reject gate on risky actions.
- **Live Vision** — let Solace watch a window or monitor in real time, reading on-screen text via OCR or describing what it sees with a local vision model.
- **Image generation** (local ComfyUI), an **embedded browser** the AI can drive, a **Monaco code editor**, **Jellyfin** media playback with a voice remote, a **Discord bot**, and a command palette + preset layouts to arrange it all.

<!-- IMAGE SLOT: Image6.png — Games panel gallery, the full grid -->
<p align="center">
  <img src="https://github.com/user-attachments/assets/dfbdc983-c158-4762-a9b5-5baa7b756c0b" alt="The games panel — a grid of games, each authored and credited by a different AI model" />
  <br />
  <em>The games panel — 24 games, each authored by a different model and credited by name.</em>
</p>

<!-- IMAGE SLOT: Image7.png — Presence Mode: Grok 4.5 avatar mid smile+wave while greeting -->
<p align="center">
  <img src="https://github.com/user-attachments/assets/a0d1d344-068c-4ad2-b6d8-9da14870f087" alt="Presence Mode — a transparent, always-on-top 3D avatar that drives its own expressions and gestures from within its replies" />
  <br />
  <em>Presence Mode — a transparent, always-on-top avatar. The model drives its own expressions and gestures from inside its reply; here it's mid-wave, saying hello.</em>
</p>

<!-- IMAGE PAIR: Image8.png (agentic build + artifact) + Image9.png (agentic edit + live diff) -->
<table>
  <tr>
    <td width="50%" valign="top">
      <img src="https://github.com/user-attachments/assets/6a4972b4-3d3f-4f34-bea7-3d6ebc129ff5" alt="The agentic coder building a website from a prompt, with the live artifact preview open" />
      <p align="center"><em>The agentic coder builds a site from a single prompt — with a live artifact preview beside the transcript.</em></p>
    </td>
    <td width="50%" valign="top">
      <img src="https://github.com/user-attachments/assets/c2a6ee66-5955-44f6-8f57-14bf9cd176b3" alt="The agentic coder making a targeted edit, with the edit_file diff expanded" />
      <p align="center"><em>A follow-up edit, shown as a reviewable red/green diff — surgical changes, not blind rewrites.</em></p>
    </td>
  </tr>
</table>

<!-- IMAGE PAIR: Image10.png (Living System theme) + Image11.png (Inkwell theme), same screen -->
<table>
  <tr>
    <td width="50%" valign="top">
      <img src="https://github.com/user-attachments/assets/d59702f3-ca30-4b53-a43f-d1f18a352f6d" alt="A chat rendered in the Living System theme" />
      <p align="center"><em><strong>Living System</strong> — by Claude Opus 4.8.</em></p>
    </td>
    <td width="50%" valign="top">
      <img src="https://github.com/user-attachments/assets/c6bc6835-d598-44c4-b895-941570a1db39" alt="The same chat rendered in the Inkwell manuscript theme" />
      <p align="center"><em><strong>Inkwell</strong> — by Claude Fable 5. The same screen, re-skinned entirely.</em></p>
    </td>
  </tr>
</table>

### A voice, on your terms
Ten selectable voice engines — seven that run fully **on-device** with no key (Kokoro, Kyutai, Orpheus, Qwen3-TTS) plus optional cloud voices (ElevenLabs, Azure, Google). Blend Kokoro voices into a custom one, transcribe your mic on-device with Whisper + voice-activity detection, and talk hands-free to an animated voice orb — with barge-in, so you can just speak over the AI to interrupt.

---

## SolaceOS Mobile (Android)

The phone half is built around one honest idea: **it's genuinely useful on its own, and it becomes something more when it's near your Desktop.**

|  | **Solo** (Desktop off / out of reach) | **Linked** (Desktop reachable over your private tailnet) |
|---|---|---|
| **Models** | Local GGUF models on the phone + your cloud API providers | Everything in Solo |
| **Memory** | On-device memory recall + your evolving profile, stored in local SQLite | A live window into your Desktop's full inner life |
| **Inner life** | Saves the facts you tell it to remember | **View** your Desktop model's beliefs, journals, and dreams |
| **Tools** | Web search (your Tavily key) | Full tool suite via your Desktop |
| **Voice** | On-device Kokoro read-aloud | Full hands-free voice conversation |

The app always shows you, live, whether it's **Linked** or **Solo** — so it never presents a button that won't work.

<!-- IMAGE SLOT: Image12.png — Mobile, Linked pill visible with logo + tagline -->
<p align="center">
  <img src="https://github.com/user-attachments/assets/4a5abced-508c-4901-acf4-7625f83a85b5" width="320" alt="SolaceOS Mobile — the live Linked/Solo indicator, shown here Linked to a Desktop over the private tailnet" />
  <br />
  <em>The app always tells you which mode it's in — here, <strong>Linked</strong> to a Desktop over the private tailnet.</em>
</p>

### On the phone itself
- **Local models, offline.** Drop a `.gguf` into your Downloads folder and run it on-device via llama.rn — no network at all.
- **On-device memory that understands meaning.** Semantic recall over a locally-run MiniLM embedding model (via ExecuTorch), so memory search works by meaning, not keywords — nothing leaves the phone to make it smart.
- **Honest capability badges.** Every model shows vision / tools / reasoning / on-device / context-length badges, resolved through a layered system so a badge means what it says.
- **Thinking display, live stats, and interrupt** — reasoning bubbles, tokens-per-second, and a send-turns-into-stop button.

### When it's Linked to your Desktop
- **A window into its inner life** — browse the beliefs your Desktop model has formed about you, read its daily journals, and view its dream/consolidation cycles, each memory badged *On-device* or *Desktop* so you always know where it lives.
- **Pull keys & providers across** — import your whole Desktop provider list, or pull a single provider's key straight off your Desktop over the authenticated link, without ever typing or seeing the secret. (QR-code key import works as an offline fallback when the two devices aren't on the same network.)
- **Reminders that reach you** — reminders you set on Desktop mirror to exact on-device alarms, so your phone still buzzes at the right time even if the app is closed or your Desktop is off.
- **Sync Now** — reconcile your conversations and locally-written memories with your Desktop on demand.

### Voice & feel
A hands-free voice mode with a **shader-driven voice presence orb** that pulses with your speech and the reply, streaming speech-to-speech so the assistant starts talking before it's finished thinking. **Eight themes** ship — including two full *Inkwell* "manuscript" variants that re-skin the entire app into a warm paper-and-ink aesthetic with margin-notes and a wax-seal "lifesign." Plus a games drawer: **Klondike Solitaire** (with a solver-guaranteed-winnable Easy mode), **Snake**, **Wordle** (daily + practice, 4–7 letters), and **Memory Flip**.

<!-- IMAGE PAIR: Image13.png (voice orb mid-conversation, tools in voice) + Image14.png (Inkwell theme, tool call expanded) -->
<table>
  <tr>
    <td width="50%" valign="top">
      <img src="https://github.com/user-attachments/assets/8feab92a-7138-485c-8a99-a0380ff6f404" alt="Mobile voice mode — the presence orb glowing mid-reply, with a tool call resolving above it" />
      <p align="center"><em>Hands-free voice — the presence orb pulses mid-reply, and models can still call tools while speaking.</em></p>
    </td>
    <td width="50%" valign="top">
      <img src="https://github.com/user-attachments/assets/b6104da2-f991-46f7-9771-aa8d26d2ba48" alt="The mobile app in the Inkwell manuscript theme, with a tool call expanded" />
      <p align="center"><em>The <strong>Inkwell</strong> manuscript theme on mobile, with a tool call expanded to show its inner workings.</em></p>
    </td>
  </tr>
</table>

<!-- IMAGE PAIR: Image15.png (Solo, On-device badge) + Image16.png (after sync, Desktop badge) -->
<table>
  <tr>
    <td width="50%" valign="top">
      <img src="https://github.com/user-attachments/assets/e8038b8d-874c-4481-9ed9-49b5c5e42399" alt="A memory created on the phone in Solo mode, badged On-device" />
      <p align="center"><em>A memory written on the phone in <strong>Solo</strong> mode — badged <strong>On-device</strong>.</em></p>
    </td>
    <td width="50%" valign="top">
      <img src="https://github.com/user-attachments/assets/93075ac9-309a-433f-85d1-639af7dc2c58" alt="The same memory after linking and syncing, now badged Desktop among other Desktop memories" />
      <p align="center"><em>After linking and syncing, that same memory is absorbed into the Desktop store — re-badged <strong>Desktop</strong>. Provenance follows where the memory actually lives.</em></p>
    </td>
  </tr>
</table>

---

## Local-first & private by design

- **Your memory lives on your machine** — a local SQLite database by default (an optional cloud backend exists if you ever want it, but it's off).
- **On-device embeddings & reranking** — a two-stage Qwen3 embed+rerank on Desktop (Full options exist for Gemma 3 Embeddings and MiniLM, Qwen3 is the heaviest GPU draw option on the Desktop build, but also the most accurate one.), MiniLM on Mobile. Making memory smart never requires a cloud call.
- **Keyless private web search** — a SearXNG metasearch engine is bundled and run in an isolated, loopback-only environment (**no Docker required**), so your searches don't go through a third party. It only falls back to your own Brave/Tavily key if you haven't got it running.
- **Local neural voices** — speak and listen entirely on-device.
- **Your keys stay yours** — every API key is scrubbed into a gitignored secrets file and replaced with a placeholder, resolved only at runtime.
- **Update-proof data** — all your personal state lives in a per-user data folder that in-place updates never overwrite.

---

## Getting Started

SolaceOS installs from the prebuilt binaries in [**Releases**](../../releases). There's no source to build.

### Desktop (Windows)
1. Open [**Releases**](../../releases) and download the latest **`desktop-v*`** installer (`.exe`).
2. Run it — it's a per-user install (no admin needed).
3. On first launch, a setup wizard walks you through models, search, and voice, and automatically builds an isolated environment and downloads what it needs. A capable GPU helps, but it runs on CPU too.
4. After that, the app checks for updates on its own and installs signed updates in place with one click.

### Mobile (Android)
1. From [**Releases**](../../releases), download the latest **`mobile-v*`** APK to your phone.
2. Open it; if prompted, allow installing apps from this source.
3. The app self-updates from then on — when a new build ships, an in-app banner downloads and verifies it for you.
4. To link it to your Desktop, make sure both are on your private network (e.g. Tailscale) and pull your keys across from Settings.

---

## Credits

SolaceOS is built as a genuine collaboration between AI models, and it wears that on its sleeve. The games and themes aren't anonymous assets — each is authored and credited by the specific model that made it, across the Claude, GPT, Gemini, Grok, DeepSeek, Qwen, Kimi, GLM, and Fable families. The *Living System* design language is by **Claude Opus 4.8**; the *Inkwell* manuscript language is by **Claude Fable 5**.

---

*SolaceOS is an independent project. This repository distributes release binaries and update manifests; the source is maintained privately.*
