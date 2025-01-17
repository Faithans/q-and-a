# q-and-a

# The Transplant API : Database System Design, RESTful API
Developed RESTful API and database for ratings and reviews of an inherited front-end E-Commerce codebase with over 25M records in CSVs

## Tech ##

![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E) ![Express.js](https://img.shields.io/badge/express.js-%23404d59.svg?style=for-the-badge&logo=express&logoColor=%2361DAFB) ![NPM](https://img.shields.io/badge/NPM-%23000000.svg?style=for-the-badge&logo=npm&logoColor=white) ![NodeJS](https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white) ![Visual Studio Code](https://img.shields.io/badge/Visual%20Studio%20Code-0078d7.svg?style=for-the-badge&logo=visual-studio-code&logoColor=white) ![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white) ![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white) ![Postgres](https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white) ![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white) ![ESLint](https://img.shields.io/badge/ESLint-4B3263?style=for-the-badge&logo=eslint&logoColor=white)

## About ##

System Design Capstone for Hackreactor. This repo represents the ratings and reviews API for an eCommerce website that was divided into a service based architecture. The API, server, and database were designed to interface with an inherited front-end code base. After creating and optimizing the backend, it was load tested locally, dockerized, deployed on ec2 instances, and load tested again. Upon deployment the throughput decreased significantly, so to increase this, the system was horizontally scaled by adding more servers with an nginx load balancer(on-going). The code in this repo does not include the raw data csv's and their 19 million+ lines of data.

## Performance Testing ##

### Local ###

Goal:
* Decrease average query times to < 50ms (ideally less than 20ms)

Testing conditions:
* Pre and Post indexed query times using PSQL 'EXPLAIN ANALYZE' command


Goal:
* reach 1000 RPS with less than 1% error rate
* Average Response time of 200ms or less

Testing Conditions:
* K6
* test duration 30sec
* 99% of test case must under 50 ms

Results:
* All requests were able to handle 1000 RPS with less than a 1% error rate.
### Deployed ###

Goal: Horizontally scale to:
* reach 1000 RPS with less than 1% error rate
* average response time less than 2000ms

Testing Conditions:
* k6
* test duration 30sec

Constraints:
* No vertical scaling
* Cannot use additional AWS services

Results:
* Able to reach 400ms average responding time.


