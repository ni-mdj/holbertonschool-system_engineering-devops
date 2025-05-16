## Web Infrastructure Design

Introduction

This project focuses on designing and understanding various web infrastructure setups, ranging from simple web stacks to secured and monitored distributed systems. You will explore key concepts related to servers, DNS, load balancing, monitoring, and more. The goal is to gain practical knowledge in building resilient and scalable web architectures.

Learning Objectives

By the end of this project, you will be able to:

Draw and explain the web stack you built.

Explain the role of each component in the web infrastructure.

Understand system redundancy and identify potential SPOFs (Single Point of Failure).

Recognize and explain the acronyms LAMP, SPOF, and QPS.

Requirements

A README.md file at the root of the project folder is mandatory.

Complete and whiteboard each task, then take a screenshot.

Submit screenshots via image hosting and include links in the answer file.

Manual QA review is required for project validation.

Keep explanations concise, focusing on the task requirements.

Solutions

0. Simple Web Stack

architecture:
  domain: foobar.com
  dns_record: A record with www pointing to IP 8.8.8.8
  server:
    web_server: nginx
    application_server: backend logic
    database: MySQL
    protocol: HTTP over TCP/IP

issues:
  - single_point_of_failure: true
  - downtime_during_updates: true
  - scalability_limitations: true

1. Distributed Web Infrastructure

architecture:
  load_balancer:
    type: HAproxy
    algorithm: round-robin
  servers:
    - nginx_server_1: web and application server
    - nginx_server_2: web and application server
  database:
    type: MySQL
    replication: primary-replica

benefits:
  - redundancy: true
  - scalability: improved

issues:
  - load_balancer_spof: true
  - no_firewall_https: true
  - no_monitoring: true

2. Secured and Monitored Web Infrastructure

architecture:
  load_balancer:
    type: HAproxy
    ssl_termination: true
  firewalls:
    - server_1: protected
    - server_2: protected
    - database_server: protected
  https:
    enabled: true
  monitoring:
    tool: Sumologic
    role: performance and health checks

benefits:
  - secured_data_transmission: true
  - monitored_infrastructure: true

issues:
  - ssl_termination_risk: true
  - single_writeable_mysql: true

3. Scale Up

architecture:
  load_balancer_cluster:
    - haproxy_1: active
    - haproxy_2: standby
  servers:
    - web_server: isolated
    - application_server: isolated
    - database_server: isolated

benefits:
  - performance: improved
  - redundancy: enhanced

Resources

Network Basics

Web Server Concepts

DNS Concepts

Load Balancer Concepts

Monitoring Concepts

Database Concepts

Usage and Submission

Complete tasks as specified, including creating diagrams.

Submit answers with screenshots via the project GitHub repository:

Repository: holbertonschool-system_engineering-devops

Directory: web_infrastructure_design

Author

Sylvain Kalache

License

This project is licensed under the Holberton School's guidelines.

