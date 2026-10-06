---
permalink: /
title: "Hi, I'm Nazrul 👋"
excerpt: "About me"
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

I recently finished my **MS in Computer Science at Oklahoma State University** in May 2026, where I worked as a Graduate Research Assistant for more than two years. I am still working with [Dr. Paritosh Ramanan](https://ceat.okstate.edu/iem/people/ramanan-faculty-profile.html) in the [Distributed Intelligent Systems Lab](https://disys-lab.github.io/), where I built an LLM agent that lets people use zero-knowledge proof systems in plain language. I also worked with [Dr. Sharmin Jahan](https://experts.okstate.edu/sharmin.jahan), building an ML system that detects DDoS attacks on cloud services and responds to them automatically.

Before my master's, I spent more than two years as an Undergraduate Research Assistant with [Dr. Jannatun Noor](https://sites.google.com/site/jannatun0abigzero/home) at BRAC University, working on faster image retrieval for cloud systems and leading fieldwork in remote Indigenous communities of Bangladesh. I also worked for a year as a software engineer, building an ML document-validation system for a US mortgage-software company and the backend of a national government portal.

**I am applying to Computer Science PhD programs for Fall 2027.**
[CV](/files/Shanto_PhD_CV.pdf) · [Publications](/publications/) · [Projects](/projects/) · [Google Scholar](https://scholar.google.com/citations?user=N9aZcZYAAAAJ&hl=en) · [GitHub](https://github.com/nazrulhuda)

## News

- **Oct 2026:** My pull request to the [CoSMeTIC](https://github.com/disys-lab/cosmetic) zkSNARK framework was merged, including a fix for a bug that reported every valid KS and LRT proof as failed.
- **Sep 2026:** Released the code, test suite, and all 6,371 result records from my skeptical-tools paper. [[Code & data]](https://github.com/disys-lab/Skeptical-MCP-For-zkSNARKs)
- **Fall 2026:** Three more papers under review, at ICOIN 2027, ACM CHI 2027, and *Social Sciences & Humanities Open*.
- **Jul 2026:** Our paper on Indigenous primary education was accepted at ACM COMPASS 2026. [[Paper]](https://dl.acm.org/doi/abs/10.1145/3811242.3819095)
- **May 2026:** Completed my MS in Computer Science at Oklahoma State University.
- **Summer 2025:** Taught AI to 10 K–12 teachers as an AI Instructor in OSU's NSF Research Experiences for Teachers program.

# Selected Research

## Making LLM Agents Reliable When They Run Zero-Knowledge Proof Systems

*First author · with Dr. Paritosh Ramanan · under review, IEEE BigData 2026* · [**Paper**](https://github.com/disys-lab/Skeptical-MCP-For-zkSNARKs/blob/main/manuscript/Natural-Language-ZK-Verification-via-Skeptical-MCP-Tools.pdf) · [**Code & data**](https://github.com/disys-lab/Skeptical-MCP-For-zkSNARKs)

![The Prover Assistant chat interface](/images/skeptical_chat.png){: .align-center width="1400px"}
*The Prover Assistant: a user asks in plain language whether their data was used in any study, starts a KS proof, and follows it from submission to verification. Each reply carries a trust label that the server sets, not the model.*

![System architecture of the skeptical MCP agent](/images/skeptical_architecture.png){: .align-center width="840px"}
*How it works: every tool call from the LLM agent passes through an interceptor that replaces any identity the model invents, and the MCP server checks the request against stored state before calling the CoSMeTIC provers. Labels such as A3 and B2–B7 refer to design decisions in the paper, for example A3 (server-side identity) and B4–B6 (finding the right job, proof type, and prover from stored state).*

Zero-knowledge proofs let a clinical study prove that its statistics are correct without showing any patient records, but requesting a proof means writing exact API calls, which shuts out the participants and auditors these systems are meant to serve. I built an LLM agent that lets people request, check, download, and verify proofs in plain language, using eight custom MCP tools on top of the CoSMeTIC zkSNARK framework. Because LLMs often leave out or invent the exact values these tools need, I designed *skeptical tools*: 20 server-side checks that complete or override what the model sends.

- Task completion rose from **70% to 93%** on Qwen 3 32B, with a gain of about 23 points on all three model families we tested (6,000+ query runs).
- A "plausible default" inside one tool silently sent **198 status checks to the wrong prover**, and the models then told users their job did not exist. A server-side override removed all 198 errors.
- Made-up answers appeared only when the chat history contained an earlier success to copy.
- Without server-side identity checks, models invented user IDs (such as `user123`) that could tie a proof to the wrong person's data. We also showed that dataset hashes and account IDs reach the model provider in every setup, even though patient records stay private.
- Our first evaluation grader wrongly marked honest error recovery as fabrication, so I built a corrected one. The code, test suite, graders, and all 6,371 result records are public, and I contributed a merged fix to CoSMeTIC itself.

## Automatic DDoS Defense for Cloud Service Meshes

*Second author · with Dr. Sharmin Jahan · under review, ICOIN 2027* · [**Paper**](https://drive.google.com/file/d/1KdqIUXU8p5YX9Xib-yazjfmLLQQOJWKe/view?usp=sharing) · [**Prototype code**](https://github.com/nazrulhuda/AI-Driven-Anomaly-Detector-and-mitigation-as-a-service)

<!-- Recommended: add the dataflow figure from the paper (Fig. 2). Save it as images/ddos_dataflow.png, then remove the comment marks around the next line.
![How the DDoS detection and rerouting framework works](images/ddos_dataflow.png){: .align-center width="600px"} -->

Modern apps on Kubernetes are made of many small services, and a flood of requests to one of them can bring the whole app down, yet service meshes like Istio only offer fixed rules that people set by hand. I built a framework that runs as a single monitoring pod and needs no changes to application code. It reads traffic data from each service's Envoy sidecar, detects attacks with a separate ML model for each service, and patches Istio routing to move traffic to backup versions, then restores normal routing when the attack stops.

- Per-service models (Random Forest, Gradient Boosting, SVM, Decision Tree) reached **94.0–97.8% accuracy** on 4,705 labeled traffic windows.
- Running the models in parallel made each detection cycle **2.27× faster** than one central model across 12 pods.
- An Isolation Forest fallback protects new services that do not have a trained model yet.
- My earlier prototype analyzed more than 1.2M Envoy log entries and explained each detection with LIME.

## Faster Image Retrieval over the Cloud

*Corresponding author · with Dr. Jannatun Noor · IEEE Transactions on Cloud Computing* · [**Paper**](https://ieeexplore.ieee.org/document/9743811) · [**PDF**](https://drive.google.com/file/d/1cGszh8qcr3rGwz5syvW2p7vChsWeYC-B/view)

Large images load slowly when internet bandwidth is low, which makes cloud apps hard to use in many parts of the world. We customized progressive JPEG with a new scan script, so images become usable sooner while they load, and with a lossy design that makes files smaller, then built a cloud storage and retrieval framework around it. I designed the compression module and built the cloud framework.

- Cut user waiting time by up to **54%** and image size by up to **27%**.
- Tested in a real-world setup across two continents with a private cloud.
- Presented as a poster at NSysS 2021.

## The Digital Divide in Remote Indigenous Communities

*Second author · with Dr. Jannatun Noor · under review, ACM CHI 2027 and Social Sciences & Humanities Open · related paper **published** at ACM COMPASS 2026* · [**CHI paper**](https://drive.google.com/file/d/1CM6S0IEtVTGResn1ibBI_WT42TLttXBT/view?usp=sharing) · [**SSHO paper**](https://drive.google.com/file/d/1Db3PFK6loLyPHUt5R_66nLD8bsfMnogv/view?usp=sharing) · [**COMPASS paper**](https://dl.acm.org/doi/abs/10.1145/3811242.3819095)

![Fieldwork in the hills of Bandarban, Bangladesh](/images/o.jpg){: .align-right width="280px"}

Some Indigenous communities in the mountains of southeast Bandarban, Bangladesh, live without stable mobile networks, electricity, or roads. Over two field visits, we trekked for days to understand how people there reach phones, signals, and the outside world, and how researchers can work with such communities respectfully. I led the fieldwork, data collection, and analysis.

- Reached 15 villages of six ethnic communities, working through local leaders as interpreters because most residents do not speak Bengali.
- More than half of the participants had no mobile coverage at home, and many climbed to mountain peaks just to make a call.
- Proposed a seven-principle guide for respectful fieldwork in remote Indigenous communities.
- In our published COMPASS 2026 paper, we identified barriers to primary education and helped create learning content in three Indigenous languages.

**Earlier work:** DDoS mitigation with a resource-sharing network, which mitigated 66.7% of attacks in a 50-VM simulation (*NSysS 2022*, oral presentation) · [Paper](https://dl.acm.org/doi/10.1145/3569551.3569560)

# Industry & Engineering

- **ML document validation for [Kramasoft](https://kramasoft.com/landing)**, a US mortgage-software company: I led a system whose ML classifiers sort borrower documents and remove irrelevant pages before AWS Textract extracts key fields, running **45× faster than manual validation** (scikit-learn, AWS Textract, Lambda, ECR, Amazon MQ, Spring Boot, PostgreSQL).
- **Backend of [Janatar Sarkar](https://janatarsarkar.gov.bd/)**, a Bangladesh government portal serving **80,000+ citizens**: RESTful APIs and a JWT-based role management system.
- **[FwdStar](/projects/)**, a freight marketplace platform for Bangladesh (technical lead and sole architect, 2026–present): a Next.js and FastAPI system with 50+ REST endpoints, PostGIS, and layered security, built from a 2,695-line specification I wrote from the client's needs.

# Teaching and Beyond

I taught AI to 10 K–12 teachers as an AI Instructor in an NSF-funded program at Oklahoma State. Outside research, I am the founding captain of a cricket team in Stillwater, Oklahoma ([Hobbies](/hobbies/)).
