---
permalink: /
title: "Md. Nazrul Huda Shanto"
excerpt: "About me"
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

I'm a computer science researcher with more than four years of research experience across AI, systems security, and human-centered computing. I currently work with [Dr. Paritosh Ramanan](https://ceat.okstate.edu/iem/people/ramanan-faculty-profile.html) at Oklahoma State University on making LLM agents reliable when they operate zero-knowledge proof systems; a first-author paper from this work is under review at IEEE BigData 2026.

I completed my **MS in Computer Science at Oklahoma State University** in May 2026. As a Graduate Research Assistant there for more than two years, I also built an automatic DDoS defense for cloud services with [Dr. Sharmin Jahan](https://experts.okstate.edu/sharmin.jahan). Before that, I spent over two years as an Undergraduate Research Assistant with [Dr. Jannatun Noor](https://sites.google.com/site/jannatun0abigzero/home) at BRAC University. I also worked for a year as a software engineer, building an ML document-validation system for a US mortgage-software company and the backend of a national government portal in Bangladesh.

**I am applying to Computer Science PhD programs for Fall 2027.**
[CV](/files/Shanto_PhD_CV.pdf) · [Publications](/publications/) · [Projects](/project/) · [Google Scholar](https://scholar.google.com/citations?user=N9aZcZYAAAAJ&hl=en) · [GitHub](https://github.com/nazrulhuda)

## News

- **Oct 2026:** My pull request to the [CoSMeTIC](https://github.com/disys-lab/cosmetic) zkSNARK framework was merged, including a fix for a bug that reported every valid KS and LRT proof as failed.
- **Sep 2026:** Submitted my first-author paper on skeptical MCP tools to IEEE BigData 2026 and released its code and data. [[Paper]](https://github.com/disys-lab/Skeptical-MCP-For-zkSNARKs/blob/main/manuscript/Natural-Language-ZK-Verification-via-Skeptical-MCP-Tools.pdf) [[Code]](https://github.com/disys-lab/Skeptical-MCP-For-zkSNARKs)
- **Fall 2026:** Three more papers under review, at ICOIN 2027, ACM CHI 2027, and *Social Sciences & Humanities Open*.
- **Jul 2026:** Our paper on Indigenous primary education was accepted at ACM COMPASS 2026. [[Paper]](https://dl.acm.org/doi/abs/10.1145/3811242.3819095)
- **May 2026:** Completed my MS in Computer Science at Oklahoma State University.
- **Summer 2025:** Taught AI to 10 K–12 teachers as an AI Instructor in OSU's NSF Research Experiences for Teachers program.

## Selected Research

**Making LLM agents reliable at the tool boundary**
*First author · under review, IEEE BigData 2026* · [Paper](https://github.com/disys-lab/Skeptical-MCP-For-zkSNARKs/blob/main/manuscript/Natural-Language-ZK-Verification-via-Skeptical-MCP-Tools.pdf) · [Code & data](https://github.com/disys-lab/Skeptical-MCP-For-zkSNARKs)
<!-- Optional: add the system figure from the paper here, e.g.
![How the skeptical MCP agent works](images/skeptical_architecture.png){: .align-center width="560px"} -->
An LLM agent that lets non-experts request and verify zero-knowledge proofs in plain language. We found that a "plausible default" inside one tool silently sent 198 status checks to the wrong prover, and the models then told users their job did not exist. My *skeptical tools* design, 20 server-side checks that complete or override what the model sends, removed all 198 errors and raised task completion from 70% to 93% across 6,000+ runs on three model families.

**Automatic DDoS defense for service meshes**
*Second author · under review, ICOIN 2027* · [Paper](https://drive.google.com/file/d/1KdqIUXU8p5YX9Xib-yazjfmLLQQOJWKe/view?usp=sharing) · [Prototype code](https://github.com/nazrulhuda/AI-Driven-Anomaly-Detector-and-mitigation-as-a-service)
A Kubernetes and Istio system that spots attacks with a separate ML model for each service (94–98% accuracy) and moves traffic to backup versions on its own, with no changes to application code. Running the models in parallel made each detection cycle 2.27× faster than one central model.

**The digital divide in remote Indigenous communities**
*Second author · under review, ACM CHI 2027 and Social Sciences & Humanities Open; related paper at ACM COMPASS 2026* · [Paper 1](https://drive.google.com/file/d/1CM6S0IEtVTGResn1ibBI_WT42TLttXBT/view?usp=sharing) · [Paper 2](https://drive.google.com/file/d/1Db3PFK6loLyPHUt5R_66nLD8bsfMnogv/view?usp=sharing) · [COMPASS](https://dl.acm.org/doi/abs/10.1145/3811242.3819095)

![Fieldwork in the hills of Bandarban, Bangladesh](images/o.jpg){: .align-right width="280px"}

We trekked for days through the hills of Bandarban, Bangladesh, to reach 15 villages of six Indigenous communities, many with no mobile network, electricity, or roads. More than half of the people we met had no mobile coverage at home, and many climbed to mountain peaks just to make a call. Our papers describe this "physical access" layer of the digital divide and how to do respectful fieldwork in such places.

Earlier work includes faster image retrieval over the cloud (*IEEE Transactions on Cloud Computing*, corresponding author) and DDoS mitigation with a resource-sharing network (*NSysS 2022*, oral presentation). Full write-ups are on my [Projects](/project/) page.

## Industry

- **ML document validation for [Kramasoft](https://kramasoft.com/landing)**, a US mortgage-software company: classifiers that sort borrower documents and remove irrelevant pages before AWS Textract, running **45× faster than manual validation**.
- **Backend of [Janatar Sarkar](https://janatarsarkar.gov.bd/)**, a Bangladesh government portal serving **80,000+ citizens**: RESTful APIs and a JWT-based role management system.

Outside research, I am the founding captain of a cricket team in Stillwater, Oklahoma ([Hobbies](/hobbies/)).
