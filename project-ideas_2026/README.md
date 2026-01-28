# RADAR-Base Google Summer of Code (GSoC) **2026**

<img src="https://radar-base.org/wp-content/uploads/2018/03/Logo_RADAR-Base-RGB.png" width="250">

**RADAR-base (Remote Assessment of Disease And Relapses)** is an open source platform that leverages data from wearables and mobile technologies. Below is a list of project ideas.

## Project Ideas

### 1. Dexcomm integration

**Overview**: This project focuses on integrating Dexcomm continuous glucose monitoring data into the RADAR-base ecosystem so that it can be used alongside other wearable and mobile data streams for research and monitoring. 
TBD: Add info on the repos

**Goals:**

TBD: Add specific goals and what we aim to achieve with this work. Link to Oura work.
TBD: add a simple wokrflow diagram

| Milestones                                      | Description                                                                                       |
|-----------------------------------------------|---------------------------------------------------------------------------------------------------|
| Design Dexcomm ingestion architecture         | Define how Dexcomm data will be acquired, normalised, and routed into existing RADAR pipelines.  |
| Implement connector / integration component   | Implement and configure the connector, schemas, and mapping to RADAR-base topics.                |
| Validation, security and documentation        | Validate data quality, ensure appropriate security/consent flows, and document the integration.  |

**Required Skills:** TBD (likely Java/Kotlin, REST/OAuth, data modelling)

**Difficulty:** TBD

**Expected Size:** TBD

**Mentors**: @yatharth, @pauline, @aditya

---

### 2. Support for GCP/GKE in the infrastructure-as-code template

**Overview**: RADAR-base currently provides infrastructure-as-code templates for specific environments. This project aims to extend those templates to support deployment on Google Cloud Platform (GCP) and Google Kubernetes Engine (GKE) in a reproducible, secure, and scalable way. We already support AWS and Azure.

TBD: Add info on the repos

**Goals:**

TBD: Add specific goals and what we aim to achieve with this work. Link to Azure PR work.
TBD: add architecture diagram (include any managed services)

| Milestones                                    | Description                                                                                                  |
|-----------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| GCP/GKE architecture and environment design   | Define target architecture, networking, security, and required managed services on GCP/GKE.                 |
| Implement IaC modules for GCP/GKE             | Add Terraform/Helm/Kubernetes manifests (or similar) for deploying RADAR-base components on GKE.            |
| CI/CD and documentation                       | Add automated deployment/testing workflows and user-facing documentation for GCP/GKE deployments.           |

**Required Skills:** TBD (likely Terraform, Kubernetes, GCP)

**Difficulty:** TBD

**Expected Size:** TBD

**Mentors**: @xibai, @Mani Thumu

---

### 3. New real-time machine learning, inference and interventions pipeline

**Overview**: The new real-time pipeline will support configurable DAGs, model training on non-identifiable/synthetic data, and advanced ML/foundation-model use cases, plus realistic sensor simulation for experimentation and reinforcement learning.

TBD: Add info on the repos

**Goals:**

TBD: Add specific goals and what we aim to achieve with this work. Link to existing realtime work and the RFC.
TBD: add architecture diagram


| Milestones                                      | Description                                                                                                                |
|-----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------|
| DAG from configuration                         | Design and implement a configuration-driven DAG definition and execution layer for the real-time pipeline.                |
| Model training on non-identifiable/synthetic data | Enable model training using synthetic or anonymised data (e.g. engagement metrics) to preserve privacy.               |
| ML / Foundation model support                  | Add support for integrating ML or foundation models (e.g. for prediction, anomaly detection, or feature extraction).      |
| Real-time sensor simulator                     | Build a sensor simulator for reinforcement learning and framework testing, driven by existing datasets and scenarios.      |
| Adverse-event simulation                       | Implement triggers for adverse events (e.g. heart rate, depression-related metrics) as part of the simulator.             |

**Required Skills:** TBD (likely Python/Scala, streaming frameworks, ML/MLops)

**Difficulty:** TBD

**Expected Size:** TBD

**Mentors**: @Heet, @afolarin

---

### 4. Improved backend for Researcher management portal

**Overview**: The Researcher backend will power flexible, interactive tools for researchers, including dashboard and widget-based interfaces with AI-assisted and dynamic UI features.

TBD: Add info on the repos

**Goals:**

TBD: Add specific goals and what we aim to achieve with this work. Link to exisitng old APIs (MP, rest-sources, etc)
TBD: add architecture diagram 

| Milestones                                      | Description                                                                                                        |
|-----------------------------------------------|--------------------------------------------------------------------------------------------------------------------|
| Dashboard / widget framework                   | Design and implement a backend API for configurable dashboards and widget-based layouts.                           |
| AI-based and dynamic UI features               | Explore and implement AI-assisted features (e.g. smart filters, recommendations) and dynamic UI configuration.     |
| Integration with existing RADAR services       | Integrate the new backend components with existing RADAR-base auth, data, and configuration services.              |

**Required Skills:** TBD (likely Java/Kotlin, REST APIs, data modelling)

**Difficulty:** TBD

**Expected Size:** TBD

**Mentors**: @pauline, @Callum, @yatharth

---

### 5. Improve and modernise the Project website (radar-base.org)

**Overview**: This project aims to modernise the public radar-base.org website, improving content structure, branding, performance, accessibility, and maintainability.

TBD: Add info on the repos/link to existing work (mention wordpress)

**Goals:**

TBD: Add specific goals and what we aim to achieve with this work.
TBD: add any screenshots and things we would like to improve 


| Milestones                           | Description                                                                                 |
|--------------------------------------|---------------------------------------------------------------------------------------------|
| Design and information architecture  | Refresh the visual design and content structure to better communicate RADAR-base’s value.   |
| Implementation and migration         | Implement the new site (framework/CMS TBD) and migrate existing content.                    |
| Performance, accessibility, SEO      | Optimise the site for performance, accessibility, and discoverability.                      |

**Required Skills:** TBD (likely modern web frontend framework, UX/design)

**Difficulty:** TBD

**Expected Size:** TBD

**Mentors**: @Wally, @Giada, @Omar, @afolarin

---

### 6. Benchmarking Rings

**Overview**: This project will develop a benchmarking framework (“Benchmarking Rings”) to systematically compare devices, pipelines, or models under controlled conditions. Exact scope is being finalised.

TBD: Add info on the protocols

**Goals:**

TBD: Add specific goals and what we aim to achieve with this work. Link to analysis methods
TBD: add workflow diagram  (if any)


| Milestones                           | Description                                                                                      |
|--------------------------------------|--------------------------------------------------------------------------------------------------|
| Define benchmarking scope and tasks  | Collaborate with stakeholders (including ZR) to define targets, metrics, and datasets.          |
| Implement benchmarking workflows     | Implement reproducible benchmarking workflows and reporting for the agreed scope.               |
| Documentation and reproducibility    | Document how to run, extend, and interpret Benchmarking Rings results.                          |

**Required Skills:** TBD

**Difficulty:** TBD

**Expected Size:** TBD

**Mentors**: TBD

---

### 7. Questionnaire app (or other frontend app) UX research and improvements

**Overview**: Focusing on the Questionnaire app (or another key frontend app), this project will investigate performance and engagement, then implement top UX and performance improvements.

TBD: Add info on the repos/link to existing work

**Goals:**

TBD: Add specific goals and what we aim to achieve with this work.
TBD: add any screenshots and things we would like to improve, including any wireframes. Mention the planned plugin architecture

| Milestones                                 | Description                                                                                                  |
|--------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| UX and performance research                | Analyse usage, performance, and engagement data to identify key UX and performance pain points.             |
| Design proposals and prototypes            | Propose, prototype, and validate UX and interaction improvements with users/researchers where possible.     |
| Implement top improvements                 | Implement the highest-impact UX and performance improvements in the chosen frontend app.                     |

**Required Skills:** TBD (likely web/mobile frontend, UX research)

**Difficulty:** TBD

**Expected Size:** TBD

**Mentors**: @wally, @giada, @pauline

---

### 8. Automation, load testing, and observability

**Overview**: This project will improve automation around performance and reliability testing, and enhance observability and error analysis (including log scanning and LLM-assisted tooling).

TBD: Add info on the repos/link to existing work (gatling tests, pauline's LLM-assisted bigquery app, etc)

**Goals:**

TBD: Add specific goals and what we aim to achieve with this work.

| Milestones                                        | Description                                                                                                                  |
|---------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------|
| Load testing for core services                    | Design and run automated load tests for gateway, Hydra, and Kratos, integrating them into CI/CD where possible.             |
| Observation tooling and log scanning              | Build or integrate tools for log scanning and observation to detect anomalies and regressions.                              |
| Firebase events error log analysis                | Extend existing Firebase/BigQuery analysis tools (e.g. Pauline’s webapp) for better error and event analysis.               |
| LLM-assisted analysis (e.g. Google AI Studio)     | Explore LLM-based workflows (e.g. via Google AI Studio) for triaging logs and errors and suggesting fixes.                  |

**Required Skills:** TBD (likely scripting, observability/monitoring stacks, cloud tooling)

**Difficulty:** TBD

**Expected Size:** TBD

**Mentors**: @pauline, @xibai, @Mani Thumu

---

### 9. Pixel Watch 4 data extraction and integration (custom WearOS application)

**Overview**: Develop a custom WearOS application for Pixel Watch 4 to collect relevant sensor data and integrate it into RADAR-base, enabling richer multi-device data collection.


TBD: Add info on the protocols

**Goals:**

TBD: Add specific goals and what we aim to achieve with this work. Link to wearOS docs.
TBD: add arch diagram (if any)

| Milestones                                | Description                                                                                                   |
|-------------------------------------------|---------------------------------------------------------------------------------------------------------------|
| Requirements and data mapping             | Define which Pixel Watch 4 data streams will be collected and how they map to RADAR-base schemas.            |
| WearOS app development                    | Implement the custom WearOS app for data collection and secure transmission.                                 |
| Integration and validation                | Integrate with RADAR-base ingestion, validate data quality, and harden for real-world study deployments.     |

**Required Skills:** TBD (likely Kotlin/Java, WearOS, Android)

**Difficulty:** TBD

**Expected Size:** TBD

**Mentors**: @Callum, @afolarin, Maxime Sasseville
