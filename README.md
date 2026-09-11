<h1 align="center">Chris Grady</h1>

<p align="center">
  <strong>Systems &amp; Solutions Engineer</strong><br />
  Atlanta, GA · Infrastructure · Security · Applied AI
</p>

<p align="center">
  <a href="https://cgfixit.com">Website</a> ·
  <a href="https://linkedin.com/in/cgrady92">LinkedIn</a> ·
  <a href="mailto:contact@cgfixit.com">Email</a>
</p>

I work on infrastructure automation, recovery tooling, and applied AI with explicit controls. Day to day that means Python, PowerShell, and Rust against real operator constraints.

[Featured projects](#featured-projects) · [More projects](#more-projects) · [How I build](#how-i-build) · [Get in touch](#get-in-touch)

## Featured projects

### [CyClaw](https://github.com/cgfixit/CyClaw) · offline-first local AI

Local knowledge-base Q&amp;A with retrieval before generation, plus an optional governed coding path for real repos. Write and cloud paths ship off.

- Hybrid semantic + keyword retrieval; LangGraph handles confirmation and audit steps on the request path.
- Optional coding harness stages patch → verify → human approve → push → draft PR.
- Audit logs and integrity checks; accounts and memory are available but disabled by default.

**Stack:** Python · FastAPI · LangGraph · ChromaDB · BM25/RRF · Ollama · SQLite · MCP<br />
[Architecture](https://github.com/cgfixit/CyClaw#architecture) · [Setup](https://github.com/cgfixit/CyClaw/blob/main/setup-guide.md) · [Tests](https://github.com/cgfixit/CyClaw/tree/main/tests)

[UI demo](https://bit.ly/CyClawDemo) · [Alternate demo](https://bit.ly/CyClaw-Demo)<br />
<sub>Demos are browser simulations of the UI. The Python backend is the repo above.</sub>

### [CyClaw-Net-Viewer](https://github.com/cgfixit/CyClaw-Net-Viewer) · macOS process egress

TCPView-style desktop app and CLI for macOS: which processes own which TCP/UDP endpoints. Built to watch egress while developing CyClaw. Crate/binary: `netboard`.

- Process, PID, IPv4/IPv6 endpoints, TCP state, and an off-box filter.
- Color-coded connection events; DNS labels optional (off by default); CSV export.
- egui GUI + CLI; universal Apple Silicon / Intel packaging.

**Stack:** Rust · egui/eframe · macOS libproc<br />
[Build](https://github.com/cgfixit/CyClaw-Net-Viewer/blob/main/docs/BUILD.md) · [Design](https://github.com/cgfixit/CyClaw-Net-Viewer/blob/main/docs/DESIGN.md) · [Tests](https://github.com/cgfixit/CyClaw-Net-Viewer/tree/main/tests)

### [CG-agent-harness](https://github.com/cgfixit/CG-agent-harness) · loopback coding harness

Rust port of CyClaw’s coding console and real-repo pipeline — without RAG or the rest of the CyClaw stack. Loopback-only; write gates ship closed.

- Browser console on `127.0.0.1` against a local model (Ollama by default).
- Pipeline: clone → plan → patch → sandbox verify → human decide → commit → push → draft PR.
- HTTP process reaches the pipeline only by spawning a child (`src/shim`); missing API key fails closed.

**Stack:** Rust · axum · tokio · cap-std<br />
[README](https://github.com/cgfixit/CG-agent-harness#readme) · [Invariants](https://github.com/cgfixit/CG-agent-harness/blob/main/INVARIANTS.md) · [Setup](https://github.com/cgfixit/CG-agent-harness/blob/main/setup-guide.md)

### [Veeam YARA Scanner](https://github.com/cgfixit/Veeam-PS1-Scanner-Yara-Rule-Detection-Onion-Links) · recovery inspection

PowerShell + YARA for scanning mounted recovery data for ransomware-related indicators before it returns to service.

- Tor / I2P / Freenet-oriented rules with context.
- JSON findings, matched strings, and scan logs for recovery workflows.
- Pester coverage for scanner logic and mocked Veeam paths; YARA fixtures for hits and exclusions.

**Stack:** PowerShell · YARA · Veeam · Pester<br />
[Scanner](https://github.com/cgfixit/Veeam-PS1-Scanner-Yara-Rule-Detection-Onion-Links/blob/main/Veeam-YARA-SecureRestore.ps1) · [Rules](https://github.com/cgfixit/Veeam-PS1-Scanner-Yara-Rule-Detection-Onion-Links/blob/main/yara-malware-detection.yara) · [Tests](https://github.com/cgfixit/Veeam-PS1-Scanner-Yara-Rule-Detection-Onion-Links/blob/main/tests/README.md)

### [Veeam Proxy Maintenance](https://github.com/cgfixit/sccm-veeam-proxy-patching) · patch windows

Coordinates VMware backup proxies around SCCM/ConfigMgr maintenance from VBR or a management host.

- Drain: disable proxies, wait for active tasks, stop services.
- Restore: restart services and re-enable proxies post-window.
- Timeouts, logs, `-WhatIf`/preview support, SCCM-aware exit codes.

**Stack:** PowerShell · Veeam · SCCM/ConfigMgr · WinRM · VMware<br />
[Implementation](https://github.com/cgfixit/sccm-veeam-proxy-patching/blob/main/sccmpatch.ps1) · [Tests](https://github.com/cgfixit/sccm-veeam-proxy-patching/tree/main/tests)

## More projects

| Project | What it demonstrates |
| :--- | :--- |
| [**Veeam HealthCheck Simplifier**](https://github.com/cgfixit/Veeam-HealthCheck-Simplifier) | Python analysis of CSV/JSON health exports into reports, PowerShell remediation previews, and ticket payloads. Optional Salesforce/Slack delivery. |
| [**Insight Extractor**](https://github.com/cgfixit/Insight_Extractor) | Python NLP: regex, dynamic keywords, and transformer scoring to turn long text into structured security insights. |
| [**AI Agent Instruction Templates**](https://github.com/cgfixit/AzureAI-CopilotStudio-PersonalAgent-Instructions) | Templates for source grounding, version checks, tool scope, and escalation (incl. model-specific variants). |
| [**Systems Administration Handbook**](https://github.com/cgfixit/Windows-Linux--Docker-Handbook) | Windows / Linux / macOS references (2026), plus Docker. [Windows web app](https://cgfixit.github.io/Windows-Linux--Docker-Handbook/). |
| [**Polymarket Mimic Trader**](https://github.com/cgfixit/PolyMarket_Mimic_Trader) | Async Python research bot with scoring, exposure limits, and circuit breakers. **Paper mode only; live trading is disabled.** |
| [**Scrape-n-Email**](https://github.com/cgfixit/Scrape-n-Email) | Python scrape + email digests with retries, CSV formula escaping, typed config, and offline tests. |

<details>
<summary><strong>Technology across the portfolio</strong></summary>

- **Infrastructure:** Veeam, VMware, SCCM/ConfigMgr, WinRM, Windows, Linux, macOS, Docker
- **AI / data:** FastAPI, LangGraph, Ollama, ChromaDB, BM25/RRF, Sentence-Transformers, Pydantic, SQLite, MCP
- **Validation:** pytest, Pester, Rust tests + Clippy, GitHub Actions, YARA

</details>

## Get in touch

Open to systems/solutions engineering, infrastructure automation, security tooling, and applied AI roles. If that matches what you’re hiring for, email is best.

[**contact@cgfixit.com**](mailto:contact@cgfixit.com) · [LinkedIn](https://linkedin.com/in/cgrady92) · [Website](https://cgfixit.com)

<sub>Reviewed September 7, 2026. Public, non-archived original projects only; archived work and forks are omitted.</sub>