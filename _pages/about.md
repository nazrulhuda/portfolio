---
permalink: /
title: "👋 Hi, I'm Nazrul"
excerpt: "About me"
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

I build systems that keep automated decisions correct when the model making them is unreliable. My recent research studies **LLM agents that operate zero-knowledge proof systems** and **ML-based defenses for cloud service meshes**. I am interested in trustworthy AI agents, verifiable computation, and the security of cloud and AI systems.

**I am applying to Computer Science PhD programs for Fall 2027.** &nbsp; [CV](/files/Shanto_PhD_CV.pdf) · [Google Scholar](https://scholar.google.com/citations?user=N9aZcZYAAAAJ&hl=en) · [GitHub](https://github.com/nazrulhuda)

🎓 I completed my **MS in Computer Science at Oklahoma State University** in May 2026. As a Graduate Research Assistant, I worked with [Dr. Paritosh Ramanan](https://ceat.okstate.edu/iem/people/ramanan-faculty-profile.html) on natural-language interfaces to zero-knowledge verification, and with [Dr. Sharmin Jahan](https://experts.okstate.edu/sharmin.jahan) on ML-based DDoS detection for Kubernetes and Istio.

📚 Before that, I was an Undergraduate Research Assistant in the C2SG Lab at BRAC University with [Dr. Jannatun Noor](https://sites.google.com/site/jannatun0abigzero/home). I was corresponding author on an **IEEE Transactions on Cloud Computing** paper and led fieldwork in remote Indigenous communities of Bangladesh.

💼 I also worked for a year as a Junior Software Engineer at Tirzok Private Ltd., building ML document processing and backend systems.

## 📰 News

<!-- TODO: replace "2026" with the real month for each item. -->
- **Oct 2026:** My pull request to the [CoSMeTIC](https://github.com/disys-lab/cosmetic) zkSNARK framework was merged: new prover APIs and a fix for a bug that reported every valid KS and LRT proof as failed.
- **Sep 2026:** First-author paper *Natural-Language Zero-Knowledge Verification via Skeptical MCP Tools* submitted to IEEE BigData 2026. [[Paper]](https://github.com/disys-lab/Skeptical-MCP-For-zkSNARKs/blob/main/manuscript/Natural-Language-ZK-Verification-via-Skeptical-MCP-Tools.pdf) [[Code]](https://github.com/disys-lab/Skeptical-MCP-For-zkSNARKs)
- **2026:** Our paper on DDoS detection for service meshes is under review at ICOIN 2027.
- **2026:** Two papers from our fieldwork with Indigenous communities are under review (CHI 2027; *Social Sciences & Humanities Open*).
- **2026:** Our paper on Indigenous primary education was accepted at ACM COMPASS 2026. [[Paper]](https://dl.acm.org/doi/abs/10.1145/3811242.3819095)
- **May 2026:** Completed my MS in Computer Science at Oklahoma State University.
- **Summer 2025:** AI Instructor in OSU's NSF Research Experiences for Teachers (RET) program.

# Selected Research

## Natural-Language Zero-Knowledge Verification via Skeptical MCP Tools

*First author · with Dr. Paritosh Ramanan · Under review, IEEE BigData 2026* · [Paper](https://github.com/disys-lab/Skeptical-MCP-For-zkSNARKs/blob/main/manuscript/Natural-Language-ZK-Verification-via-Skeptical-MCP-Tools.pdf) · [Code](https://github.com/disys-lab/Skeptical-MCP-For-zkSNARKs)

Zero-knowledge proofs let a clinical study prove that its statistics are correct without revealing patient records, but requesting a proof means writing precise API calls by hand. I built an LLM agent that lets non-experts request, check, download, and verify zero-knowledge proofs in plain language. It runs the [CoSMeTIC](https://github.com/disys-lab/cosmetic) zkSNARK framework through eight custom MCP tools (LangGraph, FastMCP, Flask, Redis, PostgreSQL, Docker).

LLMs often leave out or invent the exact values these tools need, so I designed **skeptical tools**: 20 server-side design decisions that check, complete, or override what the model sends. Across three open-weight model families and more than 6,000 query runs, task completion rose from 70% to **93%** on Qwen 3 32B, with a gain of about 23 points on every model family.

One key finding: a "plausible default" inside a tool silently sent 198 status checks to the wrong prover, and the models then told users their job did not exist. A server-side override removed all 198 errors. We also found that dataset hashes, job IDs, and account IDs reach the model provider in every configuration, even though patient records stay inside the provers. The code, test suite, graders, and all 6,371 result records are public, with a script that recomputes every number in the paper.

## ML-Based DDoS Detection and Automatic Mitigation for Service Meshes

*Second author · with Dr. Sharmin Jahan · Under review, ICOIN 2027* · [Paper](https://drive.google.com/file/d/1KdqIUXU8p5YX9Xib-yazjfmLLQQOJWKe/view?usp=sharing) · [Prototype code](https://github.com/nazrulhuda/AI-Driven-Anomaly-Detector-and-mitigation-as-a-service)

I designed and built a DDoS detection and response system for Kubernetes and Istio that needs no changes to application code. It reads telemetry from each Envoy sidecar and uses a separate ML classifier for each service (94.0–97.8% accuracy). When it detects an attack, it patches Istio routing to move traffic to backup versions, then restores the original routing after a cooldown. Running the per-service models in parallel made each detection cycle 2.27× faster than one central model. My earlier prototype analyzed more than 1.2M Envoy log entries and explained each detection with LIME.

## The Digital Divide among Little-Known Indigenous Communities in Bangladesh

*Second author · with Dr. Jannatun Noor · Under review: CHI 2027* [[Paper]](https://drive.google.com/file/d/1CM6S0IEtVTGResn1ibBI_WT42TLttXBT/view?usp=sharing) *and Social Sciences & Humanities Open* [[Paper]](https://drive.google.com/file/d/1Db3PFK6loLyPHUt5R_66nLD8bsfMnogv/view?usp=sharing)

![Fieldwork in the hills of Bandarban, Bangladesh](images/o.jpg){: .align-right width="300px"}

Some Indigenous communities in the mountains of southeast Bandarban live without stable mobile networks, electricity, or roads. Over two field visits, we trekked for days to reach 15 villages of six ethnic communities and talked with people about how they reach phones, signals, and the outside world. More than half of the participants lived without mobile network coverage, and many climbed to mountain peaks just to make a call. Our papers describe this "physical access" layer of the digital divide and give practical guidance for respectful fieldwork in such places.

Related work: a study of barriers to primary education in Indigenous communities, where we helped create learning content in three Indigenous languages ([ACM COMPASS 2026](https://dl.acm.org/doi/abs/10.1145/3811242.3819095)).

# Engineering Projects

## FwdStar — Freight Marketplace Platform

I designed and built a multi-sided freight marketplace that connects shippers, brokers, and carriers: a three-tier system with **Next.js 16**, a **FastAPI** domain engine, and **Supabase (PostgreSQL + PostGIS)**, with 20 relational tables and 50+ REST API endpoints. I turned the client's verbal business needs into a 2,695-line technical specification and built the platform iteratively against their feedback. The core engineering is integrity and security: shipment state machines with optimistic locking, transactional award integrity (SELECT FOR UPDATE), JWT verification (HS256/ES256/RS256 via JWKS), HTTP-only cookie sessions, CSRF protection, OTP verification, and login lockout.

## LangChain + MCP Chatbot Framework

![LangChain and MCP chatbot framework](images/ii.jpeg){: .align-right width="300px"}

A chatbot with a Bootstrap frontend and Flask backend that uses LangChain's ReAct agent to choose and combine MCP tool servers (for example, a weather API and math tools), with Groq for fast LLM inference.

## Automatic Document Validation (Tirzok, client: [Kramasoft](https://kramasoft.com/landing))

ML classifiers that sort borrower documents and remove irrelevant pages before sending the rest to AWS Textract for field extraction, running 45× faster than manual validation (Spring Boot, PostgreSQL, Amazon MQ, AWS Lambda, ECR).

## Backend of [Janatar Sarkar](https://janatarsarkar.gov.bd/)

RESTful APIs (Node.js, MongoDB) and a JWT-based role management system for a Bangladeshi government–citizen service portal serving 80,000+ citizens.

# Teaching

**AI Instructor, NSF Research Experiences for Teachers (RET), Oklahoma State University (2025).** Taught 10 K–12 teachers Python, machine learning, and Transformers through hands-on tutorials, guided their research projects, and designed a Python-to-LLM curriculum used in their classrooms.
