# Developer Portfolio

## TOC

- [LLM-Powered Applications](#llm-powered-applications)
  - [Cat Herder](#cat-herder-github)
  - [Nativish](#nativish-nativish)
  - [Kastor](#kastor-getkastorcom)
- [Developer Tools](#developer-tools)
  - [Project Context Generator](#project-context-generator-github)
  - [Demo Recorder](#demo-recorder-github)
- [Links](#links)

## LLM-Powered Applications

### Cat Herder · LLM orchestrator for autonomous coding
[GitHub](https://github.com/ClaireGSB/cat-herder)

A command-line and web-UI system for structured autonomous coding workflows.  
Executes multi-step development tasks with planning, gated execution, guardrails, and real-time supervision.

**Highlights**  
- User-defined, step-gated workflow engine (example: plan → tests → implementation → review) 
- Dynamic task generation
- Integrates with Claude subscription and auto-resumes when usage limit resets
- Integrated dashboard for monitoring reasoning traces, logs, and cost usage  
- Built with Node.js, TypeScript, Vite, Claude/OpenAI APIs

---

### Kastor · AI-Native Content Marketing Platform  
_Retired (no longer hosted online)_

An LLM-powered content marketing platform that scales content production while preserving authentic brand or user voice.

**Highlights**  
- Multi-voice system with channel-specific guidelines  
- Multi-step workflows to generate and refine content options  
- Campaign builder coordinating multi-asset launches  
- Built with Vue, Nuxt, TypeScript, Node.js, Prisma, Postgres, Stripe, OpenAI/Anthropic APIs

---

### Nativish · Natural-Language Improvement Assistant  
[nativi.sh](https://nativi.sh/)

A language-learning tool that transforms learner-written text into fluent, native-like phrasing across dozens of languages.
*Free - [Try it now](https://nativi.sh/)*

**Highlights**  
- Holistic text improvement with idiomatic detection  
- Web app + Chrome extension  
- Custom prompt-testing system: boolean tests, qualitative ranking, multi-model scoring, CSV-based prompt libraries  
- Built with Vue, Nuxt, TypeScript, Python, Mistral/Anthropic/OpenAI APIs

---

## Developer Tools

### Project Context Generator  
[GitHub](https://github.com/ClaireGSB/project-context)

A command-line tool that generates a structured XML file containing project (repository) information. Useful for providing a chat LLM with context about a codebase.

**Highlights**  
- Smart file-tree generation and inclusion/exclusion rules  
- TOML config with persistent user preferences  
- Shell alias integration for fast workflows  
- Safe XML escaping and metadata extraction

---

### Demo Recorder  
[GitHub](https://github.com/ClaireGSB/demo-recorder)

Automated demo-recording engine using Puppeteer + FFmpeg, built to produce consistent, polished product demos.

**Highlights**  
- User-defined interaction sequences (clicks, typing, hovers, waits, navigation, screenshots)  
- Natural mouse-movement simulation  
- Fade/dissolve transitions, pausing, multi-step recording  

---

## Links

- **GitHub:** https://github.com/ClaireGSB  
- **Nativish:** https://nativi.sh  
- **Kastor:** Retired (formerly getkastor.com)
