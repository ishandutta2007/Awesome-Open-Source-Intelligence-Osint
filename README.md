# Awesome-Open-Source-Intelligence-Osint

## Top Open Source Intelligence (OSINT) Tools Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on Identity Resolution, Breach Correlation & Graph-Based Investigation*  
**Last updated: March 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Open Source Intelligence (OSINT)**. These tools help investigators, journalists, and security teams collect and correlate publicly available information — usernames, emails, phone numbers, domains, breach data, and social media footprints — turning scattered data points into actionable intelligence.

**Examples** include OpenSanctions, Sherlock, Maigret, Holehe, PhoneInfoga, theHarvester, SpiderFoot, and EyeOfWeb (the category leaders).

**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, key-free collection, and transparent provenance tracking — ideal for researchers who need repeatable, auditable investigations without uploading targets to a commercial black box.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **Clearview AI** — Commercial facial recognition search engine built on scraped web images. Proprietary, law-enforcement focused, and legally contested in multiple jurisdictions. **Best avoided** for organizations without explicit legal authorization and privacy counsel.

- **LexisNexis** — Enterprise risk and identity resolution platform with public records, corporate data, and due diligence databases. Subscription-based with significant licensing costs.

- **Thomson Reuters Special Services** — Investigative research platform combining public records, news archives, and corporate data for financial crime and due diligence investigations.

- **ShadowDragon** — Commercial OSINT platform with social media monitoring, breach data, and identity resolution tools for law enforcement and security teams.

- **Social Links** — Commercial OSINT platform specializing in social media analysis, link analysis, and graph visualization for investigations.

- **Babel Street** — Enterprise OSINT and risk intelligence platform with multilingual social media monitoring and entity resolution.

## Open-Source GitHub Projects

- **[OpenSanctions](https://www.opensanctions.org/)**  
  **The open database of sanctions, watchlists, and politically exposed persons** — the most transparent source in the category . **Aggregates 469 global sources** including official sanctions lists, PEP data, and entities of criminal interest into a **clean, de-duplicated dataset** with **1,995,517 entities in the default distribution** . **Updates four times per day**, with every stated value linked to a public source . **FollowTheMoney data model** designed for graph technology to understand financial crime . **Free for non-commercial use**; commercial users require a data license or screening API . **SDK, CLI, and MCP server** available via `yente-client` for agentic compliance workflows . **Best for journalists, investigators, and compliance teams** needing auditable sanctions and PEP screening without vendor lock-in.

- **[Sherlock](https://github.com/sherlock-project/sherlock)**  
  **The standard username enumeration tool** — finds accounts across **400+ social networks** with a single command . **`pip install sherlock-project`** then `sherlock username` . **The fastest first pass** for digital footprint discovery — if a target uses the same handle everywhere, this finds it in seconds . **Integrated into larger toolkits** including OpenOSINT and TraceForge . **Best for quick username sweeps** before deeper investigation.

- **[Maigret](https://github.com/soxoj/maigret)**  
  **The advanced Sherlock fork covering 3000+ sites** — the depth option after Sherlock's breadth . **`pip install maigret`** then `maigret username` . **Also integrated into OpenOSINT and TraceForge** . **Best for thorough username investigation** where Sherlock's 400 sites aren't enough.

- **[Holehe](https://github.com/megadose/holehe)**  
  **Email-to-account enumeration** — checks which online services are registered to an email address without alerting the target . **`pip install holehe`** then `holehe target@example.com` . **Example output** shows Spotify, WordPress, Gravatar, and Office365 registrations . **The standard email OSINT tool** and a core component of OpenOSINT's `search_email` [citation:9].

- **[PhoneInfoga](https://github.com/sundowndev/phoneinfoga)**  
  **Phone number reconnaissance** — carrier, country, and line type detection without requiring paid APIs . **Core component of OpenOSINT's `search_phone`** [citation:9]. **For deeper phone investigation**, **PhoneOsint** wraps PhoneInfoga alongside Truecaller lookup, Telegram registration checks, breach hits, and an **exposure score (0–100)** — with batch mode, JSON/CSV/HTML/PDF export, and a `--diff` flag to show what changed since the last scan [citation:2].

- **[theHarvester](https://github.com/laramies/theHarvester)**  
  **Email, subdomain, host, and employee name harvester** for a given domain . **Integrates with multiple public sources** including search engines and certificate transparency logs . **Core component of TraceForge's domain intelligence and email breach modules** .

- **[SpiderFoot](https://github.com/smicallef/spiderfoot)**  
  **Automated OSINT reconnaissance** — 200+ modules for threat intelligence, DNS, WHOIS, and social media enumeration . **Targets: IPs, domains, emails, names, phone numbers, and usernames** . **Included in PhoneOsint's install script** for automated setup [citation:2]. **Best for broad automated reconnaissance** when you want a single tool to cover many data sources.

- **[EyeOfWeb](https://github.com/MehmetYukselSekeroglu/eye_of_web)**  
  **Open-source facial intelligence and face search platform** — the closest open-source alternative to commercial face search engines . **Hybrid database architecture**: PostgreSQL for structured metadata and **Milvus for high-dimensional vector embeddings** . **InsightFace AntelopeV2 model** generates 512-dimensional embeddings, indexed for **millisecond-level ANN searches across billions of faces** . **Supports 1:N identity searches, 1:1 comparisons, and social network analysis** . **JWT authentication, bcrypt password hashing, CSRF protection, and rate limiting** . **Docker Compose deployment**; recommended hardware: **8+ core CPU with AVX2, 16 GB+ RAM, 250 GB+ SSD** . **MIT licensed** with a strong legal disclaimer emphasizing academic research and legal security simulations only . **Limitations**: CPU-only Docker image by default; last commit 7 months ago with 0 stars in the last 30 days as of the SourcePulse listing [citation:10]. **Best for researchers** needing self-hosted facial intelligence with full data custody.

### Additional Strong Open-Source Options

- **OpenOSINT** — AI-powered OSINT toolkit wrapping Holehe, Sherlock, theHarvester, PhoneInfoga, and more into a single CLI with an interactive REPL and web UI. `pip install openosint` [citation:9].
- **TraceForge** — Case-workspace OSINT framework with 7 investigation modules (image forensics, network/PCAP, identity/social, email/breach, domain/DNS) and 152 installable catalog tools. MIT licensed .
- **Umbra** — Graph-first OSINT with **40 plugin collectors, most key-free**, entity graph across 21 types, and **confidence scoring with provenance** for every claim. Local-first SQLite storage. MIT licensed [citation:12].
- **SpectraGraph** — Visual investigation platform with a **graph-first workspace**, modular live transforms, and Neo4j backend for relationship mapping. Docker-based .
- **Spyder OSINT** — Universal OSINT research tool covering phone, IP, social media, email, name, address, domain, license plate, and username lookups .

**Frameworks for building custom systems**: Combine **Sherlock** or **Maigret** for username enumeration, **Holehe** for email-to-account discovery, **PhoneInfoga** or **PhoneOsint** for phone investigation, **theHarvester** for domain reconnaissance, **SpiderFoot** for automated multi-source collection, **OpenSanctions** for sanctions and PEP screening, and **EyeOfWeb** for self-hosted facial intelligence — to build an OSINT stack tailored to your investigation scope, data custody requirements, and legal authorization basis.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- **OSINT tools must only be used for lawful purposes** — investigating your own assets, conducting authorized security research, or gathering information on public figures and entities within legal boundaries. **Stalking, harassment, doxxing, and unauthorized access to private information are illegal and unethical.** **EyeOfWeb's developers explicitly disclaim liability for illegal or unethical use**, particularly concerning privacy laws like GDPR and KVKK [citation:10]. **PhoneOsint's Aadhaar and PayPal sections are informational-only placeholders** — no free/legal automated lookup exists for either [citation:2]. **OpenSanctions is free for non-commercial use**; commercial users must acquire a license [citation:5]. **Absence of a finding is not a clean result** — Umbra's documentation explicitly warns that when a source is unreachable it says so rather than reporting nothing found [citation:12].
- Self-hosted open-source solutions require proper authorization documentation, data retention policies, and awareness that OSINT collection can violate platform terms of service even when the underlying data is public.

---

**Made for investigators, journalists, security researchers, and compliance teams conducting lawful open-source intelligence gathering.**
Let's make OSINT more open, auditable, and legally defensible.
