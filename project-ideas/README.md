# RADAR-Base Google Summer of Code (GSoC) 2022

<img src="https://radar-base.org/wp-content/uploads/2018/03/Logo_RADAR-Base-RGB.png" width="250">

**RADAR-base (Remote Assessment of Disease And Relapses)** is an open source platform that leverages data from wearables and mobile technologies. Below is a list of project ideas.

## Project Ideas

### Management Portal

The Management Portal is a component built by the RADAR-base community to manage remote monitoring studies of participants/patients. It helps to manage studies, participants, data-sources and handles authentication and authorization of entities with the help of role based access control.

**[1] Organization and Project Archival and Export**

**Overview**: At the moment archival of organisation and project entities are not easy or possible in Management portal. 

**Goal:** The goal is to develop a project archival feature which allows archiving of inactive projects and exporting of data/metadata.

**Required Skills:** Java, Javascript, Angular

***

### Dashboards

**[1] Patient/participant Dashboard**

**Overview**: The platform collects active and passive data from the participants which is stored for researchers to access. There are data completeness visualisations which researchers also have access to. Currently the participants are not able to see their own data (apart from third-party dashboards, e.g. Fitbit). 

**Goal:** The goal is to develop a web-based & mobile-friendly visualisation tool for both passive and active data. This would complete the loop of collecting data and feeding the processed/aggregated versions of the data back to the participant. (Can also reuse previous developments done for H2O)

**Required Skills:** Javascript, Typescript, D3

***

**[2] Grafana Plugins**

**Overview**: The platform uses Grafana to visualise the data coming from the devices and apps. A TimescaleDB Kafka connector delivers both active and passive data from the Kafka topics to a TimescaleDB database. Data from the database is then used to visualise data completeness through various dashboards in Grafana. Currently, the dashboards that have been created are specific to the studies running them (with specific devices and requirements). For example, one dashboard is called "Fitbit Weartime", which shows the daily number of hours the participant wore the Fitbit device. However, not all studies may be using the Fitbit device. It would be helpful to generalise the dashboards and allow easy configurations.

**Goal:** The goal is to create different Grafana dashboard configurations for different data/devices and types of visualisations needed. This would make dashboard setup easier and quicker for different studies. This would also allow easy reuse of configurations across studies.

**Required Skills:** Grafana, TimescaleDB

***

### aRMT App

The aRMT app (also known as Questionnaire app) is an app used to deliver questionnaires to participants in a study. 

**[1] aRMT Protocol Generator and Questionnaire Tester**

**Overview**: The app takes in a protocol.json file and uses this to generate a questionnaire schedule for the participant based on their enrolment date. The protocol requires a list of offsets which are used to calculate the timings from the enrolment date. For example: {"unit": "hour", "unitsFromZero": [9, 12]} will generate that questionnaire at 9am and 12pm (with the enrolment date as the offset). Currently, these timings and offsets are manually calculated and added to the protocol.json file. 

The protocol also contains urls of the questionnaire definitions json files. These files can be automatically generated from Redcap (survey management application) or can be manually written. Currently the files have to be added to the protocols, which then have to be configured with the app, in order to test them. 

**Goal:** One of the goals is to create a simple application that will take in questionnaires and human-readable timings (for example 'everyday at 9am') and generate a protocol.json file according to this.
A sample schedule (a list of questionnaires with timestamps) will also need to be generated so that the user can review this.
In the same application, it would be good to have a questionnaire testing UI that takes in a questionnaire definition file and displays a sample of what it would look like in the aRMT UI.

**Required Skills:** Javascript, Typescript, React/Angular

***
