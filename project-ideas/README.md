# RADAR-Base Google Summer of Code (GSoC) 2022

<img src="https://radar-base.org/wp-content/uploads/2018/03/Logo_RADAR-Base-RGB.png" width="250">

**RADAR-base (Remote Assessment of Disease And Relapses)** is an open source platform that leverages data from wearables and mobile technologies. Below is a list of project ideas.

## Project Ideas

### Organization and Project Archival and Export on Management Portal

**Mentors**: nivemaham, blootvoets

**Background:** The Management Portal is a component built by the RADAR-base community to manage remote monitoring studies of participants/patients. It helps to manage studies, participants, data-sources and handles authentication and authorization of entities with the help of role based access control.

**Overview**: At the moment archival of organisation and project entities are not easy or possible in Management portal. 

**Goal:** The goal is to develop a project archival feature which allows archiving of inactive projects and exporting of data/metadata.

**Required Skills:** Java, Javascript, Angular

**Complexity:** Full time

***

### Participant Dashboard

**Mentors**: nivemaham, mpgxvii, blootvoets

**Overview**: The platform collects active and passive data from the participants which is stored for researchers to access. There are data completeness visualisations which researchers also have access to. Currently the participants are not able to see their own data (apart from third-party dashboards, e.g. Fitbit). 

**Goal:** The goal is to develop a web-based & mobile-friendly visualisation tool for both passive and active data. This would complete the loop of collecting data and feeding the processed/aggregated versions of the data back to the participant. (Can also reuse previous developments done for H2O)

**Required Skills:** Javascipt, Typescript, Angular, ChartJS

**Complexity:** Full time
***

### Grafana Plugin Dashboards

**Mentors**: nivemaham, mpgxvii

**Overview**: The platform uses Grafana to visualise the data coming from the devices and apps. A TimescaleDB Kafka connector delivers both active and passive data from the Kafka topics to a TimescaleDB database. Data from the database is then used to visualise data completeness through various dashboards in Grafana. Currently, the dashboards that have been created are specific to the studies running them (with specific devices and requirements). For example, one dashboard is called "Fitbit Weartime", which shows the daily number of hours the participant wore the Fitbit device. However, not all studies may be using the Fitbit device. It would be helpful to generalise the dashboards and allow easy configurations.

**Goal:** The goal is to create different Grafana dashboard configurations for different data/devices and types of visualisations needed. This would make dashboard setup easier and quicker for different studies. This would also allow easy reuse of configurations across studies.

**Required Skills:** Grafana, TimescaleDB

***

### aRMT Protocol Generator and Questionnaire Tester

**Mentors**: nivemaham, mpgxvii

**Background**: The aRMT app (also known as Questionnaire app) is an app used to deliver questionnaires to participants in a study. 

**Overview**: The app takes in a protocol.json file and uses this to generate a questionnaire schedule for the participant based on their enrolment date. The protocol requires a list of offsets which are used to calculate the timings from the enrolment date. For example: {"unit": "hour", "unitsFromZero": [9, 12]} will generate that questionnaire at 9am and 12pm (with the enrolment date as the offset). Currently, these timings and offsets are manually calculated and added to the protocol.json file. 

The protocol also contains urls of the questionnaire definitions json files. These files can be automatically generated from Redcap (survey management application) or can be manually written. Currently the files have to be added to the protocols, which then have to be configured with the app, in order to test them. 

**Goals:** 
- One of the goals is to create a simple application that will take in questionnaires and human-readable timings (for example 'everyday at 9am') and generate a protocol.json file according to this.
- A sample schedule (a list of questionnaires with timestamps) will also need to be generated so that the user can review this.
- In the same application, it would be good to have a questionnaire testing UI that takes in a questionnaire definition file and displays a sample of what it would look like in the aRMT UI.

**Required Skills:** Javascript, Typescript, React/Angular

**Complexity:** Full time
***


### pRMT App iOS version (through HealthKit)

**Mentors**: peyman-mohtashami, blootvoets

**Background**: The RADAR-base Passive Mobile App (pRMT App) is the hub for collecting background sensor data and provides data streams from both on-phone sensors and the capability to collect data from a number of wearable devices. 

**Overview**: Currently, the platform is able to collect passive data through Android phones. We want to develop and extend the iOS version of pRMT to collect data from HealthKit and send it to RADAR-base server. For this purpose, because in iOS devices we couldn't collect HealthKit data in background, we need a notification mechanism (via App Config) to provide configurations to periodically send notifications to start the app for data collection. 

**Current Status**: The app is in initial state and with it the participant can sign in and collect her/his step count data from HealthKit.

**Source Code**: https://github.com/RADAR-base/radar-prmt-ios/tree/feature-hk-step-count

**Goal:** 
- Develop an iOS version of the pRMT app by integrating with `HealthKit`.
- Develop and integrate the app to `App Config` to receive notifications for collecting the data from HealthKit and send it to RADAR-base server.

**Required Skills:** Swift

**Complexity:** Full time

***

### IoT Production-Ready Framework

**Overview:**
The [RADAR-IoT](https://github.com/RADAR-base/RADAR-IoT) is a lightweight, flexible, configurable and highly extensible framework for IoT devices (like a raspberry pi)
that allows for capturing sensor data (and potentially other devices) and consuming it in different ways
including sending it to the [RADAR-base mHealth platform](https://radar-base.org/) backend. The gateway framework is highly decoupled and extensible. The architecture is shown below.


![RADAR-IoT Single device multi sensorSample flow](https://user-images.githubusercontent.com/11093544/154696409-2db70900-cd86-4af1-8b6f-e80f40890452.jpg)



Presently, the RADAR-base platform focuses on personal sensing, these devices are typically battery powered and carried on the user. 
Wearable devices available for integration are limited by the vendor availability of SDKs and REST-APIs, 
however, for static IoT sensors there is a very large range of sensor modalities and providers, a significant improvement to the RADAR-base platform
would enable the use of these sensors opening up a wide array of use cases within the health and other domains. 
A single platform to collect, and analyse in real-time, ambulatory personal data (phone active/passive RMT, wearable data) 
in parallel with static IoT sensor data provides a holistic 360° view of both personal and environmental state previously not possible.

The IoT gateway framework for RADAR-base differentiates itself from related work by being device, sensor and programming language agnostic, 
supporting all types of common IoT input-output protocols, being open-source, modular and easily extensible, providing support for multiple data sinks 
(like mHealth platform, on-device AI and ML, dashboard and more), interoperability, providing industry-leading security and medical level privacy, 
and providing integration to a well established open-source mHealth cloud platform for data collection, aggregation, 
transformation and heavyweight analytics with different types of data sources like wearables, IoT sensors, mobile apps, eCRFs.

**Current Status:**
The framework is currently in the Proof-Of-Concept (POC) stage and has been tested working in a staging environment. There are various integrations including [GrovePi](https://www.dexterindustries.com/grovepi/) and the array of [sensors](https://github.com/RADAR-base/RADAR-IoT/wiki/Supported-Sensors) compatible with it. For more information take a look at the [wiki](https://github.com/RADAR-base/RADAR-IoT/wiki).

We want to finalise the framework and make it production-ready. 
This will involve working on core aspects of the framework like sensor states machines, M2M communication protocols and 
implementing advanced visibility into the framework.

**Goals:**


| Goals                                                                                                   | Related Issues                                                                                                                                                             | Requirements                                                                                                                                                                                                                                            |
|---------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Extend support for industry-standard IoT protocols.                                                     | [#21](https://github.com/RADAR-base/RADAR-IoT/issues/21)                                                                                                                   | - Implement an MQTT producer and a consumer to capture and utilise sensor data. - Deploy an MQTT broker locally using docker and build and test the implementations using Mock sensor.                                                                  |
| Provide visibility and insight into the framework and sensors allowing for more robust fault isolation. | [#5](https://github.com/RADAR-base/RADAR-IoT/issues/5), [#8](https://github.com/RADAR-base/RADAR-IoT/issues/8)                                                             | - Add State machine to the sensor to capture and track sensor events lifecycle. - Publish device/sensor events and logs to pubsub system                                                                                                                |
| Making the framework easier to develop and deploy.                                                      | [#1](https://github.com/RADAR-base/RADAR-IoT/issues/1), [#14](https://github.com/RADAR-base/RADAR-IoT/issues/14), [#16](https://github.com/RADAR-base/RADAR-IoT/issues/16) | - Continuous Integration using Github Actions - Build and test the code, Build Docker images (on arm architectures) and push to Dockerhub - Improve Unit testing in the project - Make configurations needed for deployment easier and well documented. |
| Add more abstractions and extensions to the framework.                                                  | [#4](https://github.com/RADAR-base/RADAR-IoT/issues/4)                                                                                                                     | - Add a new abstraction layer in the form of DeviceHandlers to support new types of devices alongside traditional sensors. - Add support for new sensors                                                                                                |
| Make the framework production-ready and to be used in various research studies.                         | [#19](https://github.com/RADAR-base/RADAR-IoT/issues/19), [#17](https://github.com/RADAR-base/RADAR-IoT/issues/17)                                                         | - Improve the production deployment docker-compose stack. - Make minor updates and fix bugs reported in the issues.                                                                                                                                     |


Apart from the goals above, the following general tasks are expected:
- General understanding of the RADAR-IoT framework architecture
- Understand the association of classes and modules in the code with the components in the architecture.
- Build and run the RADAR-IoT framework with Mock Sensor on your local machine. 

**Mentors**: [yatharth](https://github.com/yatharthranjan), [heet](https://github.com/Hsankesara)

**Skills:** 

- *Must have:* IoT, Python
- *Good-to-have:* Kotlin/Java, Docker, Automation, I/O protocols like GPIO

**Complexity:** Full time

***

### Fitbit Web API Subscription and Extension

**Overview:**
This [RADAR-REST-Connector](https://github.com/RADAR-base/RADAR-REST-Connector) contains a Kafka Connect source connector for a general REST API, and one for Fitbit in particular. This allows for pulling the wearable data from Fitbit servers using their [Web API](https://dev.fitbit.com/build/reference/web-api/). 

**Current Status:**
Currently, the implementation is using a PULL based approach where we make requests chronologically without any knowledge of presence of data on Fitbit's servers. This however comes with caveats:
- There is no way of knowing if there is data present (for a particular time range) on the Fitbit servers or not. 
- This makes it hard to keep track of late arriving (or out of order) data since the application needs to keep making requests backwards in time to check. This results in loss of data.
- This also makes the system not real-time.

The solution is to implement the [Fitbit Subscriptions API](https://dev.fitbit.com/build/reference/web-api/developer-guide/using-subscriptions/) (a PUSH based mechanism). In this case, the Fitbit API will send a notification to an endpoint on our application informing when there is new data available. On receiving this notification, we can make request for the specific data provided in the notification hence mitigating the issue stated above.

Another part of extension to this application would be support for new types of data from the Fitbit API.

**Goals:**


| Goals                                                                                                   | Related Issues                                                                                                                                                             | Requirements                                                                                                                                                                                                                                            |
|---------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Complete implementation for Fitbit Subscription API                                                     | [#88](https://github.com/RADAR-base/RADAR-REST-Connector/issues/88)                                                                                                                   | - This is a [work in pogress](https://github.com/RADAR-base/RADAR-REST-Connector/pull/90) - Complete the steps listed in PR description. - Use the [steps provided by fitbit](https://dev.fitbit.com/build/reference/web-api/developer-guide/using-subscriptions/#Implementing-the-Subscription-API) and integrate into the application.                                                                 |
| Add support for [Fitbit Nutrition API](https://dev.fitbit.com/build/reference/web-api/nutrition/) | [#91](https://github.com/RADAR-base/RADAR-REST-Connector/issues/91)                                                             | - Read the specifications provided by Fitbit - Create [Schemas](https://github.com/RADAR-base/RADAR-Schemas) for the new data types - Implement new [Config](https://github.com/RADAR-base/RADAR-REST-Connector/blob/master/kafka-connect-fitbit-source/src/main/java/org/radarbase/connect/rest/fitbit/FitbitRestSourceConnectorConfig.java), [Routes](https://github.com/RADAR-base/RADAR-REST-Connector/tree/master/kafka-connect-fitbit-source/src/main/java/org/radarbase/connect/rest/fitbit/route) and [Converters](https://github.com/RADAR-base/RADAR-REST-Connector/tree/master/kafka-connect-fitbit-source/src/main/java/org/radarbase/connect/rest/fitbit/converter) to pull and store these data types - Add tests for new endpoints.                                                                                                                |
| Extend timeseries data support for heart rate and sleep                                                      | [#89](https://github.com/RADAR-base/RADAR-REST-Connector/issues/89) | - Fitbit provides additional calculated fields like Resting heart rate in [Heart Rate timeseries](https://dev.fitbit.com/build/reference/web-api/heart-rate/#heart-rate-time-series) and important summaries like efficiency in [sleep data ](https://dev.fitbit.com/build/reference/web-api/sleep/#get-sleep-logs). These will be useful from an analysis point of view. - Update [Schemas](https://github.com/RADAR-base/RADAR-Schemas) to include new Fields - Make updates to the existing Routes and Converters to include these new fields - Create new Route and Converter wherever necessary - Extend tests to support these new implementations. |

Apart from the goals above, the following general tasks are expected:
- General understanding of REST APIs, Apache Kafka and the Kafka Connect architecture
- Understand the association of classes and modules in the code with the components in the architecture.
- Understand the specification provided by Fitbit Web API and design implementations based on that.
- Build and run the RADAR-Fitbit-Connector on your local machine. 

**Mentors**: [yatharth](https://github.com/yatharthranjan), [blootsvoets](https://github.com/blootsvoets)

**Skills:** 

- *Must have:* Java, REST API
- *Good-to-have:* Docker, CI, Microservices, Kafka, Distributed Systems

**Complexity:** Full time

***
