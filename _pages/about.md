---
permalink: /
title: "👋 Hello there, I'm Nazrul!"
excerpt: "About me"
author_profile: true
redirect_from:
  - /about/
  - /about.html
---



I'm a **software engineer and researcher** with 5+ years of experience building trustworthy, verifiable AI systems — and the full-stack platforms around them. My work sits at the intersection of AI/ML engineering, full-stack development, and secure, auditable systems.


🎓 I recently completed my **MS in Computer Science** at Oklahoma State University, where I was a **Graduate Research Assistant** under [Dr. Paritosh Ramanan](https://ceat.okstate.edu/iem/people/ramanan-faculty-profile.html). My core research is an **Agentic Verifiable Computation Framework** built with the Model Context Protocol (MCP), LangChain/LangGraph, Zero-Knowledge Proofs, and Gustavo — a natural-language interface for verifiable computation in which sensitive data never reaches the language model. Previously, under [Dr. Sharmin Jahan](https://experts.okstate.edu/sharmin.jahan), I built an **AI-driven self-healing cloud security system** with Kubernetes, Istio, and explainable ML (LIME).


💼 As a **Junior Software Engineer** at Tirzok Private Ltd., I spent nearly a year specializing in backend development — building AI solutions, integrating AWS services, and developing backend systems and APIs in clients' preferred frameworks and databases.


📚 As an **Undergraduate Research Assistant** at BRAC University for over two years, I co-authored a **Q1 IEEE Transactions on Cloud Computing** paper (20+ citations) and led HCI4D fieldwork in remote indigenous communities, honing my skills in data collection and analysis.


Please don't hesitate to connect if you see potential for collaboration or simply wish to network.

*If you are viewing the homepage from a mobile phone, please click the menu on the top-right corner to find other navigations. Furthermore, you can find contacting information by clicking the follow button.*

# Selected Experience

## Agentic Verifiable Computation Framework (ZKP + MCP)

My core research is an agentic framework that lets users verify Zero-Knowledge Proofs through natural-language conversation. I built a Dockerized 4-service system — a Flask + LangGraph/LangChain backend, a FastMCP prover server, Redis for session state, and PostgreSQL — with **eight custom MCP tools** and a security-critical interceptor that enforces per-request user isolation and prevents LLM-based user impersonation, so sensitive data stays in the database and never reaches the language model. I introduced a "skeptical tools" design pattern (22 design decisions across four categories) and validated it through a 4-configuration ablation across 6,000+ API calls, improving task completion from 70% to 93% with 99% response faithfulness. To the best of my knowledge, this is the first natural-language interface for zero-knowledge verifiable computation. *(First-author manuscript in preparation.)*

## AI Self-Adaptive Security as a Service [github link](https://github.com/nazrulhuda/AI-Driven-Anamoly-Detector-as-a-service)

I built an AI-driven self-protective service mesh that combines anomaly detection with automated defense for microservices. To support this, I collected and engineered a dataset of over **1.2M Istio/Envoy traffic logs** and trained ML models with Scikit-Learn, achieving **94% DDoS detection accuracy** with LIME explainability. When attacks were detected, the system automatically removed affected services and rerouted traffic to healthy alternatives, creating a self-healing, resilient cloud-native environment powered by Kubernetes, Istio, and Docker. *(Submitted to IEEE ACSOS 2026 — under review.)*

## FwdStar — Freight Marketplace Platform (Sole Architect)

I designed and built a production-grade, multi-sided freight marketplace end-to-end — connecting shippers, brokers, and carriers. A three-tier system with **Next.js 16** (App Router), a **FastAPI** domain engine, and **Supabase (PostgreSQL + PostGIS)**, comprising **20 relational tables and 50+ REST API endpoints**. I turned a client's verbal business needs into a **2,695-line technical specification** through repeated stakeholder sessions, then built the platform iteratively against their feedback. The engineering depth is in marketplace integrity and security: load and shipment **state machines with optimistic locking** and transactional award integrity (SELECT FOR UPDATE), plus dual-algorithm **JWT verification (HS256/ES256/RS256 via JWKS)**, HTTP-only cookie sessions, CSRF protection, OTP verification, login lockout, and database-level uniqueness on phone identifiers.

## LangChain + MCP Chatbot Framework

I built a chatbot framework with a Bootstrap frontend and Flask backend that connects to LangChain's ReAct agent for multi-service orchestration. The system integrates MCP tool servers (e.g., a weather API and math operations) and leverages Groq![Illustration of combining vision and language modalities](images/ii.jpeg){: .align-left width="1200px"} for fast LLM inference, allowing the chatbot to dynamically select and combine services in real time. This project demonstrates how LLMs can act as intelligent orchestrators, coordinating multiple APIs and tools within a seamless conversational interface.

## Automatic Document Validation with Textract

For a US-based borrowing company [Kramasoft](https://kramasoft.com/landing), I implemented automatic validation for borrower documents by developing machine learning classifiers to identify document types, enhancing the system's verification process. I engineered a specialized document trimmer that uses advanced ML classifiers to intelligently remove irrelevant pages, sending only important pages to AWS Textract for precise data extraction. I developed robust extraction processes to retrieve crucial field values accurately and built RESTful APIs using Spring Boot and PostgreSQL to facilitate auto-validation processes. Additionally, I integrated AmazonMQ (RabbitMQ) for seamless internal communication and deployed the system in AWS Lambda using ECR.

## Bridging the Digital Divide: A Study of HVECs in Southeast Bandarban

In the high mountains of southeast Bandarban, highly vulnerable ethnic communities (HVECs) live without basic mobile and network availability. To address the digital divide among HVECs, we conducted a mixed-method study involving two visits ![Illustration of combining vision and language modalities](images/o.jpg){: .align-left width="300px"} to six different ethnic communities across 15 villages. Trekking for nine days to collect data, we engaged 72 participants in quantitative and qualitative research, using statistical and machine learning methods. Our findings revealed that 34.2% of participants had never used the Internet, and only 13.7% used it once a week. We explored their Internet skills, outcomes, and reasons for limited use, providing insights to narrow the physical access divide and inform future HCI4D design. This study contributes to understanding the digital divide and technology design for distant indigenous communities, broadening the scope of the HCI4D/ICT4D community.

## Developing the Backend of Janatar Sarkar

I developed RESTful APIs for the backend of the [Janatar Sarkar](https://janatarsarkar.gov.bd/) government-public interaction website using Node.js and MongoDB. I also implemented a comprehensive Role Management System utilizing JWT authentication, Node.js, and MongoDB. This system ensures secure access control tailored to various types of administrators within janatarsarkar, allowing precise assignment of roles and responsibilities.
