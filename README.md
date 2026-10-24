# Awesome-Content-Credibility-Provenance

## Top Content Credibility & Provenance Ecosystem



**Curated List of SaaS Products & Open-Source GitHub Projects**  

*Focused on C2PA Content Credentials, Deepfake Detection & Self-Hosted Verification Pipelines*  

**Last updated: October 2026**



This repository tracks notable **SaaS platforms** and **open-source projects** for **Content Credibility & Provenance**. These tools help establish whether digital content is authentic—where it came from, who created it, and whether it has been altered—using cryptographic signatures, C2PA Content Credentials, and AI-based deepfake detection.



**Examples** include Adobe Content Authenticity, Truepic, Attestiv, Reality Defender, and the open-source leaders c2pa (Go library), Provenance, and is-it-ai-mcp (the category leaders).



**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, avoiding per-inspection SaaS fees, and controlling the verification pipeline. The open-source landscape is anchored by the **C2PA libraries** (Go and Python implementations for reading and validating Content Credentials), **Provenance** (dual-anchor signing with RFC 3161 and Bitcoin timestamps), and **is-it-ai-mcp** (an MCP server for AI agents to read C2PA manifests), with **Starling Lab's Authenticated Attributes** providing the research foundation for decentralized provenance.



Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.



## Table of Contents

- [SaaS/Hosted Platforms](#saas-hosted-platforms)

- [Open-Source GitHub Projects](#open-source-github-projects)

- [How to Contribute](#how-to-contribute)

- [Disclaimer](#disclaimer)



## SaaS/Hosted Platforms



| Product | Description | Pricing | Free Tier Limit |

| :--- | :--- | :--- | :--- |

| **[Adobe Content Authenticity](https://helpx.adobe.com/creative-cloud/apps/adobe-content-authenticity/beta-overview.html)** | Free web app for applying, customizing, and inspecting C2PA Content Credentials, with a Chrome extension for viewing credentials across the web. | **Free** (beta) with an Adobe account . | **Fully free**: Upload up to **50 files at once**, each up to **20 MB in JPG or PNG format** . |

| **[Truepic](https://truepic.com/)** | Enterprise C2PA platform with controlled-capture camera SDK, cryptographically signing media at the moment of capture. | **Growth tier**: **$1,450/month** at **$58 per controlled-capture inspection**. Enterprise: custom . | **No free tier** . Demo-gated. |

| **[Attestiv](https://attestiv.com/)** | Forensic AI platform for detecting deepfakes, altered images, and forged documents. | **Free media tier** for journalists and fact-checkers. Paid plans via sales for business/enterprise . | **Free for media professionals**: Forensic detection across photo, document, and video analysis. **Free video tier**: up to **5 video scans/month** . |

| **[Reality Defender](https://realitydefender.com/)** | Deepfake detection platform with public API and SaaS web platform. | **RealAPI Business**: **$399/year** for **1,000 scans/month**. Enterprise: custom (on-prem, air-gapped available) . | **Free tier**: **50 scans/month**, up to 3 seats, image and audio analysis, API keys . |



## Open-Source GitHub Projects



- **[c2pa (Go library)](https://pkg.go.dev/github.com/richardwooding/c2pa)** [![GitHub Stars](https://img.shields.io/github/stars/richardwooding/c2pa?style=social&color=white)](https://github.com/richardwooding/c2pa/stargazers)  

  **The pure-Go C2PA reader and validator.** MIT licensed. Provides full cryptographic verification of Content Credentials: COSE signature validation, certificate chain and C2PA profile enforcement, hash bindings, Merkle BMFF verification, RFC 3161 timestamp validation, and recursive ingredient validation . **Install**: `go get github.com/richardwooding/c2pa`. **Capabilities**: `Read()` extracts manifest claims; `Validate()` performs full cryptographic verification with per-step status codes. Best for Go developers building verification pipelines or integrating C2PA validation into server-side applications.



- **[Provenance](https://github.com/Vektor-Memory/Provenance)** [![GitHub Stars](https://img.shields.io/github/stars/Vektor-Memory/Provenance?style=social&color=white)](https://github.com/Vektor-Memory/Provenance/stargazers)  

  **The dual-anchor signing registry.** Signs source code, PDFs, documents, media, and fonts through **two independent timestamp authorities**: RFC 3161 (traditional TSA, immediate) and Bitcoin via OpenTimestamps (permanent settlement) . **C2PA interoperability**: full round-trip validation through `c2pa.Reader`. **Supported formats**: 27 file types including images, audio, video, documents, fonts, and source code (`.py`, `.js`, `.yaml`, `.sql`, `.md`, `.html`). **Install**: `npm install -g @vektormemory/prov`. Best for developers wanting verifiable existence proofs for code and documents without depending on a single timestamp authority.



- **[is-it-ai-mcp](https://pypi.org/project/is-it-ai-mcp/)** [![GitHub Stars](https://img.shields.io/github/stars/JohannsenLum/is-it-ai-mcp?style=social&color=white)](https://github.com/JohannsenLum/is-it-ai-mcp/stargazers)  

  **The MCP server for AI agent provenance checks.** Reads embedded C2PA manifests and reports two separate things: what the manifest claims about the file's origin, and whether the cryptographic signature still matches the current bytes . **Three verdicts**: `AI_DECLARED`, `NO_AI_DECLARED`, `UNKNOWN`—with `UNKNOWN` as the default when no manifest exists or the signature is broken. **Tools**: `check_image_provenance` (single file) and `scan_directory` (batch scanning with aggregate counts). **No account or API key required**—reads local files only. Best for developers building AI agents that need to verify content authenticity before processing.



- **[Starling Lab Authenticated Attributes](https://starlinglab.org/)**  

  **The decentralized provenance research framework.** An open infrastructure for establishing proven integrity of metadata through cryptographic hashes, digital signatures, and third-party timestamping . **Philosophy**: shifts verification from reactive deepfake detection to **affirmative proof of existence**—demonstrating exactly when a file was created and ensuring it hasn't been altered. **Real-world deployment**: Canon-Reuters collaboration on hardware-backed signing in professional cameras (glass-to-glass chain of custody). Best for researchers and newsrooms building tamper-evident archives and investigating provenance at scale.



### Additional Strong Open-Source Options



- **c2pa-python** — The official Python bindings for the C2PA library, enabling manifest reading and validation in Python pipelines .

- **OpenTimestamps** — The decentralized timestamping protocol underlying Provenance's Bitcoin anchor. Best for developers building their own dual-anchor verification systems.



## How to Contribute



1. Fork the repo.

2. Add/edit entries in `README.md` (follow existing format).

3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.

4. Submit PR with a short explanation.



Star the repo if you find it useful!



## Disclaimer



- This is a **community-curated** list — not exhaustive and not an endorsement.

- **"Signature verified" is not "claim is true"**: C2PA validation proves the manifest hasn't been tampered with since signing—it does not prove the original content is authentic or unmanipulated. `is-it-ai-mcp` explicitly separates these two questions and returns `UNKNOWN` when no manifest exists .

- **Enterprise provenance is expensive and quote-gated**: Truepic charges **$58 per inspection** after a **$1,450/month** minimum ; Reality Defender's business tier is **$399/year for 1,000 scans** . Free tiers are for evaluation, not production scale.

- **Adobe Content Authenticity is free but beta**: upload limits of **50 files × 20 MB** apply, and the service may change .

- **Open-source C2PA tooling is emerging**: the Go library and Provenance are functional and actively maintained, but the ecosystem is younger than commercial offerings—evaluate maturity against your production requirements.



---



**Made for journalists, fact-checkers, platform engineers, and developers building content authenticity infrastructure.**  

Let's make content credibility more open, cryptographically verifiable, and accessible.
