<p align="center">
  <img alt="Fetch Agent" src="https://github.com/j5onrf/fetch/blob/main/logo.svg" width="250" />
</p>

<h1 align="center">Fetch <kbd>v0.9.2.0-beta</kbd></h1>

<p align="center">
  <img src="https://img.shields.io/github/last-commit/j5onrf/fetch?style=for-the-badge&labelColor=1f1f1f&color=8dbdff" alt="Last Commit">
  <img src="https://img.shields.io/badge/language-python-a3be8c?style=for-the-badge&labelColor=1f1f1f" alt="Language">
  <img src="https://img.shields.io/github/repo-size/j5onrf/fetch?style=for-the-badge&labelColor=1f1f1f&color=d6b4e0" alt="Repo Size">
</p>

<p align="center">
  <code>agentic-tool-calls</code> &nbsp; <code>node: Q_79</code> &nbsp; <code>core: axon</code>
</p>

---

<h2 align="center">How it Works</h2>

All configurations and custom shortcuts are managed in [`ai-context.md`](ai-context.md).

*   **Direct (No Session)**: Sub-millisecond Jaccard matching (`jaccard_search`) instantly routes custom keywords to your local terminal.
*   **Single-Turn Agent (`ai <query>`):** Returns a single response directly to your shell prompt without loading an active conversation.
*   **Multi-Turn Chat (`ai` alone):** Starts a persistent terminal session with multi-turn context tracking.
*   **Workspace Agents (`ai init <path>`):** Indexes your directory into a lightweight codebase graph and boots up a codebase-aware chat.

<div align="center">
  <details>
    <summary style="cursor: pointer; color: #94A3B8; outline: none;">
      <i>Click to expand ecosystem diagram</i>
      <br />
    </summary>
    <br />
    <img alt="Fetch Agent Banner" src="https://github.com/user-attachments/assets/56fe2b60-0cbe-4f51-bc27-a35516f1088f" width="800" style="border-radius: 8px;" />
  </details>
</div>

---

<h2 align="center">CLI Launch Interface</h2>

```console
╭──────────────────────────────────────────────╮
│  >_ Fetch Robotics                           │
│                                              │
│  model:     Qwen3.6-35B-A3B.gguf             │
│  directory: ...-ai/projects/session-test     │
│  skill:     init codef                       │
│  database:  active (3 facts, 109 turns)      │
╰──────────────────────────────────────────────╯
[sys] Startup context: 210 tokens | Ctrl+C to exit.

Agent: Workspace loaded. Awaiting instructions.
❯
```

---

<h2 align="center">Temporal Personality Memory (TPM)</h2>

<p align="center">
  <em>Evolving with your workspace, learning your habits, and standardizing your identity.</em>
</p>

* [Weaviate Engram](https://github.com/weaviate/engram-python-sdk)'s active reconciliation concepts with [Noema](https://github.com/Fail-Safe/Noema)'s local Markdown file system.

---

<h2 align="center">Codebase Graph Mapper & Relational Index</h2>

<p align="center">
  <em>Building flat shorthand maps and queryable call graphs.</em>
</p>

* [Graphify](https://github.com/Graphify-Labs/graphify)'s codebase mapping with [codebase-memory-mcp](https://github.com/DeusData/codebase-memory-mcp)'s relationship queries.

---

<h2 align="center">System Administration & Diagnostics</h2>

<p align="center">
  <em>Inspecting package updates, monitoring system health, and optimizing performance.</em>
</p>

* [log-checker](/tools/agentic/system/log-checker) and [system-health](/tools/agentic/system/system-health) live diagnostics with [aur-audit](/tools/agentic/system/aur-audit), [security-audit](/tools/agentic/system/security-audit), [update-inspector](/tools/agentic/system/update-inspector) zero-trust auditing, [system-optimizer](/tools/agentic/system/system-optimizer) resource adjustments, [ai-status](/tools/agentic/system/ai-status) routing, and [ai-commit](/tools/agentic/system/ai-commit) hooks.

---

<h2 align="center">Core Capabilities</h2>

| Core | Capability | Description |
| :---: | :---: | :--- |
| **Performance** | **Zero-Daemon** | 0% idle CPU/RAM. `Ultra-light` execution. |
| **Intelligence** | **Scalability** | Optimized from `Qwen3.5-2B` up to frontier models. |
| **Resiliency** | **Fallbacks** | `Gemini` → `OpenAI` → `Claude` → `xAI` → `OpenRouter` → `GGUF`. |
| **Safety** | **Zero-Trust Guardrails** | Intercepts out-of-bounds commands and edits for manual approval. |
| **Safety** | **Type-Safe Validation** | Enforces [Pydantic AI](https://github.com/pydantic/pydantic-ai)'s schema concepts natively. |
| **Safety** | **Syntactic Guardrails** | [OpenAI Agents](https://github.com/openai/openai-agents-python)-style self-correcting `.py`/`.json` writes. |
| **Integration** | **Dynamic Context** | On-demand compilation of system specs and file contents. |
| **Optimization** | **Token-Slasher** | Custom [`tool`](https://github.com/j5onrf/fetch/tree/main/tools) and [`skill`](https://github.com/j5onrf/fetch/tree/main/skills) integration built for minimal token use. |
| **Interface** | **Conversational TUI** | Rich, multi-turn chat sessions directly in the terminal. |
| **Auditability** | **Zero-Dependency** | Under 500 lines of modular, standard-library Python. |

---

<h2 align="center">TUI Carousel & Input Controls</h2>

* **`Up` / `Down` Arrow Keys:** Cycle through available ranked selections.
* **`Enter`:** Execute the highlighted command (or initialize a [workspace](https://github.com/j5onrf/fetch/tree/main/projects) if the selection is a directory path).
* **`Esc` / `Right Arrow` / `Ctrl+C`:** Cancel/Skip the active menu, memory-recall, or tool authorization prompt cleanly.

```console
~ ❯ weather
[01/02] ❯ [weather full] curl -s wttr.in | cat
:: ↵ run  Esc:
```

---

<h2 align="center">Model Select TUI</h2>

<p align="center">
  <em>Manage your active cloud endpoints, inspect live API rankings, and toggle keys.</em>
</p>

* Run **`model select`** directly from your terminal to launch the interactive **[Cloud Connection](https://github.com/j5onrf/fetch/tree/main/modules)** TUI.

---

<h2 align="center">Command Reference</h2>

### 1. Global Shell Commands
*Executed directly from your terminal prompt.*

| Command | Description |
| :--- | :--- |
| **`ai`** | Launch an interactive, multi-turn chat session. |
| **`ai <query>`** | Get an instant, one-shot answer, straight back to your shell prompt. |
| **`ai init <path>`** | Launch (or create) a codebase-aware workspace agent. |
| **`hs` / `hist`** | Interactively search or view active workspace `history.md`. |

### 2. Active Session Commands
*Typed directly inside an active chat session.*

| Command | Description |
| :--- | :--- |
| **`/skill <query>`** *(or `/s`)* | Search and load dynamic specialist skills. |
| **`view file <path>`** *(or `read`)* | Dynamically read local files directly into your model context. |
| **`-save <tag>` / `-load`** | Save active states or rollback/clone snapshots (with Global Handoff). |
| **`/f`** / **`/t`** / **`/b`** / **`/a`** | Trigger prompt-generating subroutines: Follow-up, Thinking, Brainstorm, or All. |

### 3. Modular Toggle & Diagnostic Switches
*Typed inside an active chat session to adjust settings.*

| Command | Description |
| :--- | :--- |
| **`/clear`** / **`/reset`** | **Reset** Session context, local chat history, and the SQLite TPM table. |
| **`/spell`** / **`/sp`** | **Toggle** the context-aware grammar & spellchecker ON/OFF. |
| **`/g`** | **Toggle** workspace confirmation gates ON/OFF (autonomous editing mode). |
| **`/m`** | **Toggle** long-term memory and TPM reconciliation ON/OFF. |
| **`/r`** / **`/r <tokens>`** | **Toggle** reasoning ON/OFF. Supports custom limits (default: 500). |
| **`/stats` / `/tok`** | **Diagnostics**: Toggle real-time speed metrics or view live token usage. |

---

<h2 align="center">Agent Blueprint</h2>

Add your shortcuts, commands, and workspaces to [`ai-context.md`](https://github.com/j5onrf/fetch/blob/main/ai-context.md).

```markdown
# --- Weather & Live Networking ---
[TOOL] curl -s wttr.in --cat ---> weather full, wttr, weather
[TOOL] curl -s "wttr.in/?format=3" --cat ---> weather simple, wttr, weather

# --- Fetch Agent Blueprint (CheatSheet) ---
~/.config/fetch/tools/blueprint --leaf ---> cheatsheet, blueprint, bp, cs
```

---

<h2 align="center">Setup & Prerequisites</h2>

```bash
# 1. Optional: Install terminal rendering utilities
# (mdcat enables beautiful terminal markdown formatting)
yay -S mdcat

# 2. Install the required requests dependency
# Arch: sudo pacman -S python-requests
# Debian/Ubuntu: sudo apt install python3-requests
# macOS / Other: pip install requests
sudo pacman -S python-requests

# 3. Clone the repository locally
git clone https://github.com/j5onrf/fetch.git ~/.config/fetch

# 4. Add the environment hook into Bash & reload your profile
echo '[ -f "$HOME/.config/fetch/ai-hook.sh" ] && source "$HOME/.config/fetch/ai-hook.sh"' >> ~/.bashrc
source ~/.bashrc

# 5. Create your private configuration file (No global exports needed!)
# Fill in only what you use; the rest defaults safely.
# The agent reads this dynamically on every run with zero terminal restarts.
nano ~/.config/fetch/.env
```

#### Configuration Example (`.env`):
```env
# ~/.config/fetch/.env
# use "ai status" and "model select"

# Claude API
CLAUDE_API_KEY="your-claude-api-key-here"
CLAUDE_MODEL="claude-fable-5"

# OpenAI API
OPENAI_API_KEY="your-openai-api-key-here"
OPENAI_MODEL="gpt-5.6"

# x.AI Grok API
XAI_API_KEY="xai-your-grok-api-key-here"
XAI_MODEL="grok-4.5"

# Google Gemini API
GEMINI_API_KEY="AIzaSyYourFullGeminiApiKeyHere"
GEMINI_MODEL="gemini-3.1-flash-lite"

# OpenRouter API
OPENROUTER_API_KEY="sk-or-v1-YourFullOpenRouterKeyHere"
OPENROUTER_MODEL="openrouter/free"

# Context Limits
AI_MAX_TOKENS=8192
```

---

## Project Roadmap

Our vision is to transform **Fetch** into a highly responsive, zero-latency, cross-platform stationary software robot agent. Rather than memorizing complex CLI flags, users can naturally command their system using direct slash-commands, semantic text, or local voice triggers.

Below is our phased engineering plan:

### Phase 1: Consolidated Configuration & Hybrid Routing Core
*   **Unified Schema Registry**: Consolidate `ai-context.md` and standard prompts into a single, machine-readable `tools.json`. Each tool will register its standard OpenAPI function schema (for the LLM) alongside a private execution template (for local terminal execution).
*   **Dual-Engine Triage Router**: Implement a hybrid execution path in `ai-agent.py`:
    *   *Deterministic Jaccard Matching*: Instantly intercept slash-commands and exact keyword shortcuts at `<0.1ms` latency.
    *   *Cactus Needle (26M SAN)*: Route natural, complex phrasing on-device at `~5ms` latency using a quantized, local 14MB ONNX runtime.
*   **Fail-Safe Conversational Fallback**: Establish a clean delegation pattern. When local routing returns no matched tools, seamlessly forward the context to your conversational baseline (`gemini-3.1-flash-lite` or Qwen-35B).

### Phase 2: Synthetic Data Generation & Local Fine-Tuning
*   **Converse-to-Command Datasets**: Synthesize thousands of diverse, natural-language training examples (utilizing frontier models as teachers) matching the specific administration tools of `Fetch`.
*   **Needle Gating Fine-Tuning**: Fine-tune Cactus Needle's 26M attention weights locally (via CLI/Playground). Train the model to naturally isolate trigger patterns (e.g., *"Fetch, scan me drive"* vs *"Hey Fetch, can you..."*) and reliably populate JSON argument structures.
*   **Robustness Evaluation**: Build local evaluation validation datasets to verify routing accuracy, eliminating false positive command executions.

### Phase 3: OS Independence & Native Standalone Packaging
*   **Cross-Platform Script Abstraction**: Abstract system administration bash scripts into OS-aware execution pipelines, preparing `Fetch` to run natively on Linux, macOS, and eventually Windows.
*   **Standalone Binary Compilations**: Package the entire Python environment, dependencies, and the quantized 14MB routing model into a single, zero-dependency native binary executable (using `PyInstaller` or `Briefcase`) for streamlined user installation.

### Phase 4: Local Voice Layer (Offline Robot Ambient Feel)
*   **Offline Speech-to-Text (STT)**: Integrate a lightweight local speech transcriber (such as `whisper.cpp` or `Faster-Whisper`) to process voice inputs natively on CPU/GPU.
*   **Ultra-Fast Text-to-Speech (TTS)**: Hook up highly efficient local speech synthesis (like `piper` or `koko`) to allow the agent to talk back with negligible audio generation latency.
*   **Voice Trigger Hook**: Establish an ambient system-level hotkey or wake-word listener to summon `Fetch` instantly without terminal typing.

### Phase 5: Self-Correcting Syntactic Guardrails
*   **Abstract Syntax Tree (AST) Verification**: Run local background compilers in Python to verify code structures generated by smaller models (like Qwen-2B) before outputting to the console.
*   **Auto-Repair Turn**: If a syntax or indentation error is detected, automatically run a silent background patch turn to correct the code block on-the-fly.

---

## Credits

*   **Origin**: Based on the foundational [local-ai agent](https://github.com/j5onrf/local-ai) framework.
*   This application incorporates the [Cactus Needle](https://github.com/cactus-compute/needle) routing model developed by Cactus Compute, which is licensed under the MIT License:
Copyright (c) 2026 Cactus Compute
(Standard MIT License)

