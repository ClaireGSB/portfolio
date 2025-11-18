
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

### Cat Herder ([GitHub](https://github.com/ClaireGSB/cat-herder)) 

A command-line orchestration tool for structured, autonomous LLM-driven software development workflows.

**Problem Addressed**

* LLM-based coding tools lack structure, reproducibility, and state management
* Current agents can’t execute multi-step feature builds with validation and recovery
* Developers need a reliable way to guide autonomous coding agents through complex repositories

**Solution**

* Provides a **step-gated workflow engine** where each task passes through defined stages (plan → write tests → implement → review)
* Supports **multi-task sequences** (entire features) that evolve dynamically as early tasks create new ones
* Integrates with **Claude CLI** for direct, local development with fine-grained permissions and guardrails
* Tracks full state, logs, and costs — with a **real-time web dashboard**
* Supports Claude subscription (auto-restart when usage limit resets) and OpenAI subscriptions (to be merged soon)

**Key Capabilities**

* **Autonomy Control:** Adjustable “autonomy level” (0–5) to balance independence and collaboration
* **Resilient Execution:** Automatic retries, rate limit handling, and resumable Git branches
* **Dynamic Task Sequencing:** Allows the AI to generate follow-up tasks from PRDs or specifications
* **Guardrails & File Access Control:** Fine-grained restrictions on what files each step can modify
* **Integrated Debugging:** Rich logs with reasoning traces, token usage, and run history
* **Interactive Dashboard:** Web-based interface for monitoring sequences and answering AI questions in real time

**My Role: Creator & Vibe-Coder**

* **Architecture:** Designed the entire task orchestration model (sequence → task → step hierarchy)
* **CLI Tooling:** Implemented core orchestrator logic, CLI commands, and configuration validation
* **Web Dashboard:** Built the Vite-based UI for real-time task visualization and human-in-the-loop collaboration
* **Stack:** Node.js, TypeScript, Vite


### Kastor ([getkastor.com](https://getkastor.com/))

An LLM-powered content marketing platform that scales content production while preserving authentic brand or user voice.
*7-day free trial - [Try it now](https://getkastor.com/)*

**Problem Addressed**
- Solopreneurs and small marketing teams struggle to scale content marketing and social media presence
- Existing AI tools produce generic content that lacks brand personality and consistency - unless the user sets up a consistent system to provide the model with voice examples, company and product context, knowledge of content published in the past, feedback on content generated, etc.

**Solution**
- **Multi-Voice System:** Create distinct voices for different purposes (corporate, executive, product-specific) with content type-specific guidelines
- **Content Generation:** Transform one piece of content into multiple channel-specific formats (Twitter, LinkedIn, blog posts, marketing emails) while maintaining voice consistency
  **Campaign Orchestration:** Generate coordinated multi-channel campaigns around single topics or product launches
- **Quality Control:** Multiple content options per generation with full editorial control

**How it works**
- Easy onboarding that guides the user through the collection of inputs (company and product context, brand or user "voice" which consists of a description, guidelines, + examples of do's and don'ts specific to each channel)
- The user can then, through a guided content generation flow, select the type of content to be created, the goal, and add additional requirements. Content generated in the past can also be selected as starting point to create new content (eg, turn a blog post into a tweet or marketing email)
- Or, they can define a "campaign" (a group of multiple content pieces that have a common theme or goal). Kastor will generate a brief for each of them, and after approval or edits, generate each piece individually.
- In the backend, all inputs are aggregated in structured prompts which are fed to multi-step LLM workflows.

**On the roadmap**
- Support for voice inputs
- Company website and social media scraping, with LLM processing, to make onboarding a breeze
- Support for existing inventory and more content planning features (eg, Kastor could suggest a content plan by itself based on defined goals and past content)
- Support for cold start (for entrepreneurs just starting their content journey)
- Image support (input and generation), more media in the future?
- Feedback support (collaborate with Kastor to improve a piece of content)
- Content Calendar management

**My Role: Solo Designer & Developer**
- **Prompt Engineering and workflows:** Designed LLM workflows that aggregate all user inputs to iteratively generate several content options, with some parallelization.
- **User Experience:** Component-based frontend for rapid prototyping and scalable design patterns
- **Full-Stack Development:** End-to-end ownership from database design to Stripe integration
- **Stack:** Vue.js, Vuetify, Nuxt, TypeScript, Node.js, Prisma, Postgres, Anthropic/OpenAI APIs

### Nativish ([nativi.sh](https://nativi.sh/))

An LLM-powered language learning application that helps users write more naturally in their second language.
*Free - [Try it now](https://nativi.sh/)*

**Problem Addressed**
- Language learners struggle to sound natural despite correct grammar and vocabulary
- Translation tools don't serve advanced speakers (90% fluency) who need nuanced improvements
- Existing tools like Grammarly miss idiomatic issues and don't support all languages

**Solution**
- Provides instant, fluent improvements to user-written text in any language
- Holistic text improvement (not edit-by-edit) for efficiency
- Multi-platform: web, mobile, and Chrome extension

**My Role**
- **UX and full frontend development** Responsive web app and Chrome extension, built with Vue.js
- **Prompt Engineering:** Designed LLM workflows and prompts
- **Evaluation Framework:** Built comprehensive Python-based prompt testing framework with CSV prompt libraries, multi-model evaluation, and LLM-as-judge methodology
- **Technical Collaboration:** Collaborated with Rust backend engineer using Git workflows, code reviews, and CI/CD
- **My Stack:** Vue.js, TypeScript, Nuxt, Python, Anthropic/OpenAI/Mistral APIs

**Prompt testing system**
- Custom prompt evaluation framework supporting both boolean tests (spelling, grammar and idiom correctness) and qualitative assessments (text improvement quality)
- Automated test data generation system + support for manually added test data with language detection and categorization
- CSV-based prompt library system enabling systematic testing of multiple prompt variants
- Comprehensive testing pipeline: prompt → model output generation → pair-wise ranking by LLM (for quallitative assessments) → statistical scoring
- Multi-model evaluation across OpenAI, Anthropic, and Mistral APIs with configurable parameters


## Developer Tools

### Project Context Generator ([GitHub](https://github.com/ClaireGSB/project-context))

A command-line tool that generates structured XML files containing project information for LLM context. The user can select files to include / exclude

**How it works**
- Generates visual file tree representations and XML output with configurable file contents
- TOML-based configuration with intelligent path management
- Preserves user selections across updates while discovering new files
- Handles XML escaping and special characters automatically

**Key Features**
- Shell alias integration for seamless workflow adoption
- Configurable inclusion/exclusion patterns
- Incremental updates that preserve user preferences
- Project metadata extraction from package.json



### Demo Recorder ([GitHub](https://github.com/ClaireGSB/demo-recorder))

An automated web application demo recording tool using Puppeteer with configuration-driven workflows.
Created based on a need I had to create a demo video for Kastor (and anticipating frequent updates).

**Problem Addressed**
- Creating product demos requires manual, repetitive, time-intensive screen recording, subject to manual error

**Solution**
- TOML configuration system for defining browser interaction sequences
- Custom mouse movement simulation for natural, professional-looking recordings
- Advanced recording controls: pause/resume, transitions, element-specific screenshots
- FFmpeg integration for video processing and transition effects

**Key Features**
- **Comprehensive Step Types:** Navigation, input, clicks, selects, waits, screenshots, scrolling
- **Smart Interactions:** Configurable typing speeds, hover durations, element targeting
- **Visual Polish:** Smooth mouse movements, fade/dissolve transitions, transparent backgrounds
- **Developer Experience:** Shell alias integration, template generation, error handling



## Links

- **GitHub:** [github.com/ClaireGSB](https://github.com/ClaireGSB)
- **Nativish:** [nativi.sh](https://nativi.sh/)
- **Kastor:** [getkastor.com](https://getkastor.com/)
