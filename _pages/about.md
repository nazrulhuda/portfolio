---
permalink: /
title: "Hi, I'm Nazrul 👋"
excerpt: "About me"
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

I recently completed my **MS in Computer Science at Oklahoma State University** (May 2026), where I spent more than two years as a Graduate Research Assistant. My main research, with [Dr. Paritosh Ramanan](https://ceat.okstate.edu/iem/people/ramanan-faculty-profile.html), is on making LLM agents reliable when they operate zero-knowledge proof systems. I am still working with him on this project, and my first-author paper from it is under review at IEEE BigData 2026.

I also worked with [Dr. Sharmin Jahan](https://experts.okstate.edu/sharmin.jahan), building an ML system that detects DDoS attacks on cloud services and responds to them automatically. Before my master's, I spent more than two years as an undergraduate research assistant with [Dr. Jannatun Noor](https://sites.google.com/site/jannatun0abigzero/home) at BRAC University, publishing in *IEEE Transactions on Cloud Computing* as corresponding author and leading fieldwork in remote Indigenous communities of Bangladesh. I also worked for a year as a software engineer, building an ML document-validation system for a US mortgage-software company and the backend of a national government portal.

**I am applying to Computer Science PhD programs for Fall 2027.**
[CV](/files/Shanto_PhD_CV.pdf) · [Publications](/publications/) · [Projects](/project/) · [Google Scholar](https://scholar.google.com/citations?user=N9aZcZYAAAAJ&hl=en) · [GitHub](https://github.com/nazrulhuda)

## News

- **Oct 2026:** My pull request to the [CoSMeTIC](https://github.com/disys-lab/cosmetic) zkSNARK framework was merged, including a fix for a bug that reported every valid KS and LRT proof as failed.
- **Sep 2026:** Submitted my first-author paper on skeptical MCP tools to IEEE BigData 2026 and released its code and data.
- **Fall 2026:** Three more papers under review, at ICOIN 2027, ACM CHI 2027, and *Social Sciences & Humanities Open*.
- **Jul 2026:** Our paper on Indigenous primary education was accepted at ACM COMPASS 2026. [[Paper]](https://dl.acm.org/doi/abs/10.1145/3811242.3819095)
- **May 2026:** Completed my MS in Computer Science at Oklahoma State University.
- **Summer 2025:** Taught AI to 10 K–12 teachers as an AI Instructor in OSU's NSF Research Experiences for Teachers program.

# Selected Research

## Making LLM Agents Reliable When They Run Zero-Knowledge Proof Systems

*First author · with Dr. Paritosh Ramanan · under review, IEEE BigData 2026* · [**Paper**](https://github.com/disys-lab/Skeptical-MCP-For-zkSNARKs/blob/main/manuscript/Natural-Language-ZK-Verification-via-Skeptical-MCP-Tools.pdf) · [**Code & data**](https://github.com/disys-lab/Skeptical-MCP-For-zkSNARKs)

<!-- Recommended: add the system figure from the paper (Fig. 1). Save it as images/skeptical_architecture.png, then remove the comment marks around the next line.
![How the skeptical MCP agent works](images/skeptical_architecture.png){: .align-center width="600px"} -->

**The problem.** Zero-knowledge proofs let a clinical study prove that its statistics are correct without showing any patient records. But asking for a proof means writing exact API calls with hashes, proof types, and job IDs, which is hard for the participants and auditors these systems are meant to serve.

**What I built.** An LLM agent that lets people request, check, download, and verify proofs in plain language, such as *"Prove my data is in the KS test."* It runs the CoSMeTIC zkSNARK framework through eight custom MCP tools. Because LLMs often leave out or invent the exact values these tools need, I designed **skeptical tools**: 20 server-side design decisions that check, complete, or override what the model sends.

**What we found.**
- Task completion rose from **70% to 93%** on Qwen 3 32B, with a gain of about 23 points on all three model families we tested (6,000+ query runs).
- A "plausible default" inside one tool silently sent **198 status checks to the wrong prover**, and the models then told users their job did not exist. A server-side override removed all 198 errors.
- The only made-up answers in the study appeared when the conversation history contained an earlier success to copy, which supports designing tools that do not depend on chat history.
- Dataset hashes, job IDs, and account IDs reach the model provider in every configuration, even though patient records stay inside the provers.

**Open and reproducible.** The code, test suite, graders, and all 6,371 result records are public, with a script that recomputes every number in the paper. I also contributed a merged pull request to [CoSMeTIC](https://github.com/disys-lab/cosmetic), including the fix for its verification bug.

## Automatic DDoS Defense for Cloud Service Meshes

*Second author · with Dr. Sharmin Jahan · under review, ICOIN 2027* · [**Paper**](https://drive.google.com/file/d/1KdqIUXU8p5YX9Xib-yazjfmLLQQOJWKe/view?usp=sharing) · [**Prototype code**](https://github.com/nazrulhuda/AI-Driven-Anomaly-Detector-and-mitigation-as-a-service)

<!-- Recommended: add the dataflow figure from the paper (Fig. 2). Save it as images/ddos_dataflow.png, then remove the comment marks around the next line.
![How the DDoS detection and rerouting framework works](images/ddos_dataflow.png){: .align-center width="600px"} -->

**The problem.** Modern apps on Kubernetes are made of many small services, and a flood of requests to one of them can bring the whole app down. Service meshes such as Istio can control traffic, but only through fixed rules that people set by hand.

**What I built.** A framework that runs as a single monitoring pod and needs no changes to application code. It reads traffic data from each service's Envoy sidecar, detects attacks with a separate ML model for each service, and patches Istio routing to move traffic to backup versions. When the attack stops, it restores normal routing on its own.

**Results.**
- Per-service classifiers (Random Forest, Gradient Boosting, SVM, Decision Tree) reached **94.0–97.8% accuracy** on 4,705 labeled traffic windows.
- Running the models in parallel made each detection cycle **2.27× faster** than one central model across 12 pods.
- An Isolation Forest fallback covers new services that do not have a trained model yet.
- My earlier prototype analyzed more than 1.2M Envoy log entries and explained each detection with LIME.

# Other Research

**The digital divide in remote Indigenous communities** · *Second author · under review, ACM CHI 2027* [[Paper]](https://drive.google.com/file/d/1CM6S0IEtVTGResn1ibBI_WT42TLttXBT/view?usp=sharing) *and Social Sciences & Humanities Open* [[Paper]](https://drive.google.com/file/d/1Db3PFK6loLyPHUt5R_66nLD8bsfMnogv/view?usp=sharing) *· related paper at ACM COMPASS 2026* [[Paper]](https://dl.acm.org/doi/abs/10.1145/3811242.3819095)

![Fieldwork in the hills of Bandarban, Bangladesh](images/o.jpg){: .align-right width="280px"}

We trekked for days through the hills of Bandarban, Bangladesh, to reach 15 villages of six Indigenous communities, many with no mobile network, electricity, or roads. More than half of the people we met had no mobile coverage at home, and many climbed to mountain peaks just to make a call. Our papers describe this "physical access" layer of the digital divide and how to do respectful fieldwork in such places.

**Faster image retrieval over the cloud** · *Corresponding author · IEEE Transactions on Cloud Computing* · [[Paper]](https://ieeexplore.ieee.org/document/9743811)
We customized progressive JPEG so images load faster and take less space in low-bandwidth settings, cutting user waiting time by up to 54% and image size by up to 27% in a real-world test across two continents.

**DDoS mitigation with a resource-sharing network** · *Co-author and oral presenter · NSysS 2022* · [[Paper]](https://dl.acm.org/doi/10.1145/3569551.3569560)
A network that tracks attacker IP addresses and drops their requests through a proxy, which mitigated 66.7% of attacks in a simulation with 50 Nginx virtual machines.

# Industry & Engineering

- **ML document validation for [Kramasoft](https://kramasoft.com/landing)**, a US mortgage-software company: classifiers that sort borrower documents and remove irrelevant pages before AWS Textract, running **45× faster than manual validation**.
- **Backend of [Janatar Sarkar](https://janatarsarkar.gov.bd/)**, a Bangladesh government portal serving **80,000+ citizens**: RESTful APIs and a JWT-based role management system.
- **[FwdStar](/project/)**, a freight marketplace platform for Bangladesh (technical lead and sole architect, 2026–present): a Next.js and FastAPI system with 50+ REST endpoints, PostGIS, and layered security, built from a 2,695-line specification I wrote from the client's needs.

# Teaching and Beyond

I taught AI to 10 K–12 teachers as an AI Instructor in an NSF-funded program at Oklahoma State. Outside research, I am the founding captain of a cricket team in Stillwater, Oklahoma ([Hobbies](/hobbies/)).
