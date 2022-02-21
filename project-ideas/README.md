# RADAR-Base Google Summer of Code (GSoC) 2022

<img src="https://radar-base.org/wp-content/uploads/2018/03/Logo_RADAR-Base-RGB.png" width="250">

**RADAR-base (Remote Assessment of Disease And Relapses)** is an open source platform that leverages data from wearables and mobile technologies. Below is a list of project ideas.

## Project Ideas

### Management Portal

The Management Portal is a component built by the RADAR-base community to manage remote monitoring studies of participants/patients. It helps to manage studies, participants, data-sources and handles authentication and authorization of entities with the help of role based access control.

**[1] Organization and Project Archival and Export**

**Mentors**: nivemaham, blootvoets

**Overview**: At the moment archival of organisation and project entities are not easy or possible in Management portal. 

**Goal:** The goal is to develop a project archival feature which allows archiving of inactive projects and exporting of data/metadata.

**Required Skills:** Java, Javascript, Angular

**Complexity:** Full time

***

### Dashboards

**[1] Patient/participant Dashboard**

**Mentors**: nivemaham, mpgxvii, blootvoets

**Overview**: The platform collects active and passive data from the participants which is stored for researchers to access. There are data completeness visualisations which researchers also have access to. Currently the participants are not able to see their own data (apart from third-party dashboards, e.g. Fitbit). 

**Goal:** The goal is to develop a web-based & mobile-friendly visualisation tool for both passive and active data. This would complete the loop of collecting data and feeding the processed/aggregated versions of the data back to the participant. (Can also reuse previous developments done for H2O)

**Required Skills:** Javascipt, Typescript, Angular, ChartJS

**Complexity:** Full time
***

**[2] Grafana Plugins**

**Mentors**: nivemaham, mpgxvii

**Overview**: The platform uses Grafana to visualise the data coming from the devices and apps. A TimescaleDB Kafka connector delivers both active and passive data from the Kafka topics to a TimescaleDB database. Data from the database is then used to visualise data completeness through various dashboards in Grafana. Currently, the dashboards that have been created are specific to the studies running them (with specific devices and requirements). For example, one dashboard is called "Fitbit Weartime", which shows the daily number of hours the participant wore the Fitbit device. However, not all studies may be using the Fitbit device. It would be helpful to generalise the dashboards and allow easy configurations.

**Goal:** The goal is to create different Grafana dashboard configurations for different data/devices and types of visualisations needed. This would make dashboard setup easier and quicker for different studies. This would also allow easy reuse of configurations across studies.

**Required Skills:** Grafana, TimescaleDB

***

### aRMT App

The aRMT app (also known as Questionnaire app) is an app used to deliver questionnaires to participants in a study. 

**[1] aRMT Protocol Generator and Questionnaire Tester**

**Mentors**: nivemaham, mpgxvii

**Overview**: The app takes in a protocol.json file and uses this to generate a questionnaire schedule for the participant based on their enrolment date. The protocol requires a list of offsets which are used to calculate the timings from the enrolment date. For example: {"unit": "hour", "unitsFromZero": [9, 12]} will generate that questionnaire at 9am and 12pm (with the enrolment date as the offset). Currently, these timings and offsets are manually calculated and added to the protocol.json file. 

The protocol also contains urls of the questionnaire definitions json files. These files can be automatically generated from Redcap (survey management application) or can be manually written. Currently the files have to be added to the protocols, which then have to be configured with the app, in order to test them. 

**Goals:** 
- One of the goals is to create a simple application that will take in questionnaires and human-readable timings (for example 'everyday at 9am') and generate a protocol.json file according to this.
- A sample schedule (a list of questionnaires with timestamps) will also need to be generated so that the user can review this.
- In the same application, it would be good to have a questionnaire testing UI that takes in a questionnaire definition file and displays a sample of what it would look like in the aRMT UI.

**Required Skills:** Javascript, Typescript, React/Angular

**Complexity:** Full time
***

### pRMT App

The pRMT app is an app used to collect passive data from participants' phone sensors and integrated devices. 

**[1] iOS version of pRMT with HealthKit**

**Mentors**: peyman-mohtashami, blootvoets

**Overview**: The RADAR-base Passive Mobile App (pRMT App) is the hub for collecting background sensor data and provides data streams from both on-phone sensors and the capability to collect data from a number of wearable devices. Currently, the platform is able to collect passive data through Android phones. We want to develop and extend the iOS version of pRMT to collect data from HealthKit and send it to RADAR-base server. For this purpose, because in iOS devices we couldn't collect HealthKit data in background, we need a notification mechanism (via App Config) to provide configurations to periodically send notifications to start the app for data collection.

**Current Status**: The app is in initial state and with it the participant can sign in and collect her/his step count data from HealthKit.

**Source Code**: https://github.com/RADAR-base/radar-prmt-ios/tree/feature-hk-step-count

**Goal:** 
- Develop an iOS version of the pRMT app by integrating with `HealthKit`.
- Develop and integrate the app to `App Config` to receive notifications for collecting the data from HealthKit and send it to RADAR-base server.

**Required Skills:** Swift

**Complexity:** Full time

***

### iOT Framework

The RADAR-IoT is a lightweight, flexible, configurable and highly extensible framework for IoT devices (like a raspberry pi) that allows for capturing sensor data (and potentially other devices) and consuming it in different ways including sending it to the RADAR-base mHealth platform backend.

**[1] Production-ready Version of the Framework**

**Mentors**: yatharth, heet

**Overview**: The IoT gateway framework for RADAR-base differentiates itself from related work by being device, sensor and programming language agnostic, supporting all types of common IoT input-output protocols, being open-source, modular and easily extensible, providing support for multiple data sinks (like mHealth platform, on-device AI and ML, dashboard and more), interoperability, providing industry-leading security and medical level privacy, and providing integration to a well established open-source mHealth cloud platform for data collection, aggregation, transformation and heavyweight analytics with different types of data sources like wearables, IoT sensors, mobile apps, eCRFs.

The framework is currently in the Proof-Of-Concept (POC) stage and has been tested working in a staging environment. We want to finalise the framework and make it production-ready. This will involve working on core aspects of the framework like sensor states machines, M2M communication protocols and implementing advanced visibility into the framework.

**Goals:** 
- Extend support for industry-standard IoT protocols.	
  - Implement an MQTT producer and a consumer to capture and utilise sensor data.
  - Deploy an MQTT broker locally using docker and build and test the implementations using Mock sensor.
- Provide visibility and insight into the framework and sensors allowing for more robust fault isolation.
  - Add State machine to the sensor to capture and track sensor events lifecycle.
  - Publish device/sensor events and logs to pubsub system
- Add more abstractions and extensions to the framework.
- Make the framework easier to develop and deploy.
- Make the framework production-ready and to be used in various research studies.

**Required Skills:** IoT, Python

**Helpful Skills:** Kotlin/Java, Docker, Automation, I/O protocols like GPIO

**Complexity:** Full time
***
