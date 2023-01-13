---
title: GCP Professional Cloud Developer
tags: gcp learning cloud
---

# GCP Professional Cloud Developer
> Learning Path

---

## Section 0: Fundamentals

### Cloud Computing
- On Demand Computing (pool allocation by the provider)
- Self Service
- Access over Internet
- flexible/elastic resources (scalability)
- pay per use only

#### IaaS (Infrastructure as a Service)
- Compute
- Storage
- Network
- pay for allocation

#### PaaS (Platform as a Service)
- more abstraction than IaaS
- JRE, Database, Runtime, Development Stack
- pay for usage

#### SaaS (Software as a Service)
- Service in the Cloud
- consumed by internet users
- e.g. gmail, dropbox etc.

#### Serverless
- Servers/Infrastructure managed by others
- focus on code
- Cloud Functions / Cloud Run

### Google Network

#### Locations
- North America
- South America
- Europe
- Asia
- Australia

#### Regions
- independent geographic area
- e.g. London, Frankfurt etc.
- composed zones (1 region = 3 zones)

#### Zones
- separated spaces in one region
- location where resources are deployed

### Google Infrastructure Security

#### Hardware
- custom designed Hardware and Security Chips
- Secure Boot Stack
- Access Control for Datacenter

#### Services
- Encrypted Communication

#### User
- multi level security controls

#### Internet Communication Layer
- Front End Security
- DoS Protection

#### Operational Security Layer
- Intrusion Detection
- Reducing Insider Risks
- enforces second factor security
- Software Development best practises
- Bug Bounty Program

### Pricing and Billing
- [Online Pricing Calculator](https://cloud.google.com/products/calculator)
- defining Budgets to Account or Project level
- create Alerts for thresholds
- view reports and billing dashboards
- quotas limit erroneous applications to produce unwanted load

#### Quotas
- applied to Project level
- Rate Quotas
    - reset after specific time
    - e.g. 1000 requests/s (reset each second)
- Allocation Quotas
    - set max number of resources for project
    - e.g. max 5 VPC's

---

### GCP Hierarchy
1. Organization node (root node | overall policies)
2. Folder (assign policies | create hierarchy e.g. business departments)
3. Project (e.g. API, Billing, Collaborators, Google Services)
    - Project ID (globally unique)
    - Project Name (not unique)
    - Project Number (internally used by google)
4. Resources (belongs to one project | e.g. VM, Storage etc.)

### IAM - Identity and Access Management
- Google Account, Google Group, Service Account or Cloud Identity Domain
- Controll Permissions by using Roles

#### [Roles](https://cloud.google.com/iam/docs/understanding-roles)
> = collections of permissions
- Basic Role
    - Owner (all permissions)
    - Editor (read/write)
    - Viewer (read only)
    - Billing Admin (read only + billing)
- Predefined Role
    - typical job roles tailored to specific resources
- Custom Role
    - define custom tailored roles
    - only applicable project or organization level

### Service Accounts
- functional/service user
- Permissions defined by IAM Policies

### Interactions with GCP
- Google Cloud Console (GUI)
- Google Cloud SDK and -Shell (gcloud, gsutil, bq)
    - Cloud Shell (online shell via GUI)
- API (programmatic interaction)
- Cloud Mobile App (GUI for mobile devices)

---

### VPC - Virtual Private Cloud
> secure, individual, private cloud-computing model hosted in a public cloud

- combines scalability of public cloud and data isolation of private cloud
- segmenting networks
- using firewall rules to restrict access
- create static routes to forward traffic to specific destinations
- VPC's are global and can have subnets (regional) worldwide
- Routing Tables (forward traffic from/to instances)
- Firewall (restrict access, rules by using tags e.g. `web` = 80,443 IN allow)
- VPC Peering allows connection between VPC's to exchange traffic
- Shared VPC tied to IAM policy
- offers Load balancing

#### Connect VPC to other Networks (e.g. On Premise)
- VPN Connection
- Direct Peering over PoP (Points of Presence)
- Carrier Peering (if not already in PoP)
    - On Premise Network Connection via Service Provider's Network
    - not covered by Google SLA
- Dedicated Interconnect (direct Connection to Google)
- Partner Interconnect

### Compute Engine - VM's
- billed by second
- utomatically applies sustained-use discount
- committed-use discounts
- Preemtible/Spot VM'ss
    - Preemtible VM's up to 24h
    - Spot VM's no max runtime

### Cloud Load Balancing
- distribute traffic over instances
- managed Service by google
- cross-region load balancing

### Cloud DNS
- managed DNS Service
- low latency, highly availability

### Cloud CDN (Content Delivery Network)
- Edge Caching
- low network latency
- provide end user with content, quickly

---

### Cloud Storage
- Object Storage organized in Buckets
- stored as binary (BLOB)
- immutable
- access via URL's (integrates well with web-technologies)
- Use Cases
    - Website Content
    - Archival & Disaster Recovery
    - Direct Download
- Access Control via IAM Roles
- Lifecycle control
- Storage Types
    - Standard (frequently accessed)
    - Nearline (infrequently access data e.g. once a month)
    - Coldline Storage (low cost of Nearline, access once every 90 days)
    - Archive Storage (lowest cost, access once a year, disaster recovery)

### Cloud SQL
- fully managed relational Databases (e.g. MySQL, Postgres etc.)
- auto patch / backups

### Cloud Spanner
- fully managed relational Database
- scales horizontally
- strongly consistent
- "speaks" SQL with joins and secondary indexes
- high availability
- high IO per second

### Cloud Firestore
- NoSQL DB
- Documents organized into collections
- horizontally scalable
- mobile, web and server development

### Cloud BigTable
- NoSQL big data database
- handle massive workloads at low latency
- Use Cases
    - 1TB+ of (semi-)structured data
    - high throughput or rapidly changing data
    - NoSQL data
    - time series or semantic ordering data
    - asynchronous batch or synchronous real-time porocessing
    - machine learning algorithms on data

---

### Cloud App Engine
- Only write code in self contained workloads
- rapid scaling

### Container
- Box containing partition, code and dependencies
- portable Code and OS/Hardware of Host is a black box
- starts as quickly as a process
- requires container runtime 

### Kubernetes & Google Kubernetes Engine (GKE)
- Manage and orchestrate containers in a cluster
- Scaling, Deploying and Rollbacks
- Kubernetes Cluster contains nodes which contain pods
- Pod (smallest unit) = Running Process/App
- `kubectl` cli
- Service (load balanced pods) - stable Endpoint
- Declaration by Configuration File (deployment.yml)
- GKE = managed Kubernetes Cluster by Google


### Hybrid- or Multi-Cloud (Anthos)
- Parts of Infrastructure On-Premise and using Cloud Infrastructure
- Anthos = Googles Hybrid- or Multi-Cloud Solution
- Anthos uses Kubernetes and GKE On-Premise

---

### App Engine
- Serverless
- automatically provision servers and scale on demand
- limited Languages and Framework Support
- SDK for local development (local emulation)
- Standard Runtime: Containers (Java, Python, PHP, Node.js or Ruby), no SSH access
- Flexible Runtime: Custom Configuration (custom Docker Image) (managed Compute Engine VM), SSH access

### Google API Tools
- Cloud Endpoints
    - Distributed API management system
    - OpenAPI Specification
    - Supports Apps in App Engine, GKE and GCE)
- API Gateway
    - Secure Access to backend services via REST API
    - Clients consume REST APIs to implement standalone apps
- Apigee Edge
    - Focus on Business Functions (rate limiting, quotas, analytics)
    - often B2B
    - Backend Services don't need to be in GCP, often use to take apart legacy apps


### Cloud Run
- Serverless (for stateless containers handling web requests / pubsub events)
- build on Knative
- Autoscaling
- only charges for use
- Write Code -> Build Image -> Run Image from Artifact Registry (GCR)
- auto HTTPS traffic, SSL Certificate, Url Endpoint

---

### Deployment in the Cloud
- Cloud Source Repositories (Git in the Cloud)

### Cloud Functions
- lightweight, event based, asynchronous computing
- small, single purpose function
- support: Node.js, Python, Go, Java, .Net, Ruby, PHP

### Terraform (IaC)
- Describe Template File, Apply to the Environment

---

### Monitoring
> "Collecting, Processing, Aggregating and displaying real-time quantitive data [...]"
> e.g. Query counts, Error counts, Processing times, Server lifetimes
> _Reference_: [Google's Site Reliability Engineering Book](https://landing.google.com/sre/books)

- Foundation of Application Reliability
- Build Dashboards
- Alert on SLO violation
- Metrics/ KPIs
    - Latency (e.g. Page Load, Response Time, Waiting Requests etc.)
    - Traffic (e.g. Requests, IO, Sessions, Transactions etc.)
    - Saturation - how full the service is / capacity of service (e.g. Memory, CPU, Disk etc.)
    - Errors (e.g. 400/500 HTTP Codes, Exceptions, Stack Traces etc.)

### SLI, SLO, SLA

#### SLI (Service Level Indicator)
> Monitoring Metric, measuring one aspect of service's reliability

- Number of good events / Count of all valid events

#### SLO (Service Level Objective)
> Combines SLI with target reliability

- SMART SLO's
- **S**pecific
- **M**easurable
- **A**chievable
- **R**elevant (to the user)
- **T**ime-bound

#### SLA (Service Level Agreement)
> Commitments made to your customers

- minimum level of service
- Alerting Threshhold higher than SLA

### Observability
- Signals: Metrics, Logs, Trace
- Visualize and Analyze: Dashboards, Metrics/Logs Explorer, Service Monitoring, Health Checks, Profiler
- Incidents: Alerts, Error Reporting, SLO

#### Monitoring
- Signal Data -> Aligned Data
- Predifined or Custom Metrics
- Visibility for Performance, Uptime, Overall Health
- allow creation of Alerts

#### Logging
- Examine Logs via Google's Log Explorer 
- near real-time Analyzing
- Export as
    - Files to GCS (Google Cloud Storage)
    - Messages to PubSub
    - Data into BigQuery
- Log Categories
    - Audit (Admin Activity, Data Access, System Events, Access)
    - Agent (Fluentd agent - logs from GCE, Containers etc.)
    - Network (VPC flow, Firewall rules, NAT gateway)
    - Service (StdOut/StdErr)

#### Error Reporting
- Crashes/Exceptions from Services
- Dedicated view for Errors and Stacktraces

#### Cloud Trace
- Latency from distributed Applications
- Capture Traces from the Application
- Performance insights
- Identify Changes in Performance

#### Cloud Profiler
- CPU and Heap Picture of an application
- Analyze Apps across GCP, On-Premise and other clouds
- Support for Java, Go, Python, Node.js
- Call hierarchy and resource consumption in interactive flame graph

---

## Section 1: Designing highly scalable, available, and reliable cloud-native applications

### 1.1 Designing high-performing applications and APIs. Considerations include:
#### Microservices


#### Scaling velocity characteristics/tradeoffs of IaaS (infrastructure as a service), CaaS (container as a service), PaaS (platform as a service), and FaaS (function as a service)
#### Understanding how Google Cloud services are geographically distributed (e.g., latency, regional services, zonal services)
#### User session management
#### Caching solutions
#### HTTP REST versus gRPC (Google Remote Procedure Call)
#### Designing API services with API Gateway and Cloud Endpoints
#### Loosely coupled asynchronous applications (e.g., Apache Kafka, Pub/Sub, Eventarc)
#### Instrumenting code to produce metrics, logs, and traces
#### Graceful shutdown of applications on platform termination
#### Writing fault-tolerant code  

### 1.2 Designing secure applications. Considerations include:

#### Implementing data lifecycle and residency requirements relevant for applicable regulations
#### Security mechanisms that protect services and resources
#### Security mechanisms that secure/scan application binaries and manifests
#### Storing, accessing, and rotating application secrets and keys (e.g., Secret Manager, Cloud Key Management Service)
#### Authenticating to Google Cloud services (e.g., application default credentials, JSON Web Token (JWT), OAuth 2.0)
#### End-user account management and authentication using Identity Platform
#### IAM roles for users, groups, and service accounts
#### Securing service-to-service communications (e.g., service mesh, Kubernetes Network Policies, and Kubernetes namespaces)
#### Running services with least privileged access (e.g., Workload Identity)
#### Certificate-based authentication (e.g., SSL, mTLS)

### 1.3 Managing application data. Considerations include:

#### Defining database schemas for Google-managed databases (e.g., Firestore, Cloud Spanner, Bigtable, Cloud SQL)
#### Defining a data storage key structure for high-write applications
#### Choosing data storage options based on use case considerations, such as:
```
- Time-limited access to objects
- Data retention requirements
- Structured versus unstructured data
- Strong versus eventual consistency
- Data volume
- Data access patterns
- Online transaction processing (OLTP) versus data warehousing
```
##### Time-limited access to objects
##### Data retention requirements
##### Structured versus unstructured data
##### Strong versus eventual consistency
##### Data volume
##### Data access patterns
##### Online transaction processing (OLTP) versus data warehousing

---

## Section 2: Building and testing applications

### 2.1 Setting up your local development environment. Considerations include:

#### Emulating Google Cloud services for local application development
#### Using the Google Cloud Console, Google Cloud SDK, and Cloud Shell tools
#### Using developer tooling (e.g., Cloud Code, Skaffold)

### 2.2 Building. Considerations include:

#### Source control management
#### Creating secure container images from code
#### Developing a continuous integration pipeline using services (e.g., Cloud Build, Artifact Registry) that construct deployment artifacts
#### Code and test build optimization

### 2.3 Testing. Considerations include:

#### Unit testing (e.g., emulators)
#### Integration testing
#### Performance testing
#### Load testing
#### Failure testing/chaos engineering

---

## Section 3: Deploying applications

### 3.1 Adopting appropriate feature rollout strategies. Considerations include:

#### A/B testing
#### Feature flags
#### Backward compatibility

### 3.2 Deploying applications to a serverless computing environment. Considerations include:

#### Sizing and scaling serverless environments
#### Deploying from source code
#### Invocation via triggers
#### Configuring event receivers
#### Exposing and securing application APIs (e.g., API Gateway, Cloud Endpoints)

### 3.3 Deploying applications and services to Google Kubernetes Engine (GKE). Considerations include:

#### Deploying a containerized application to GKE
#### Integrating Kubernetes RBAC with Identity and Access Management (IAM)
#### Configuring Kubernetes namespaces
#### Defining workload specifications (e.g., resource requirements)
#### Building a container image using Cloud Build
#### Configuring application accessibility to user traffic and other services
#### Managing container lifecycle

---

## Section 4: Integrating Google Cloud services

### 4.1 Integrating an application with data and storage services. Considerations include:

#### Managing connections to data stores (e.g., Cloud SQL, Cloud Spanner, Firestore, Bigtable, Cloud Storage)
#### Reading/writing data to/from various data stores
#### Writing an application that publishes/consumes data asynchronously (e.g., from Pub/Sub)

### 4.2 Integrating an application with compute services. Considerations include:

#### Using service discovery (e.g., Service Directory)
#### Reading instance metadata to obtain application configuration
#### Graceful application startup and shutdown

### 4.3 Integrating Cloud APIs with applications. Considerations include:

#### Enabling a Cloud API
#### Making API calls using supported options (e.g., Cloud Client Library, REST API or gRPC, API Explorer) taking into consideration:
```
- Batching requests
- Restricting return data
- Paginating results
- Caching results
- Error handling (e.g., exponential backoff)
```
##### Batching requests
##### Restricting return data
##### Paginating results
##### Caching results
##### Error handling (e.g., exponential backoff)
#### Using service accounts to make Cloud API calls

---

## Section 5: Managing deployed applications

### 5.1 Managing cloud compute services (e.g., Google Kubernetes Engine, serverless). Considerations include:

#### Analyzing lifecycle events
#### Using external metrics and corresponding alerts
#### Configuring workload autoscaling

### 5.2 Troubleshooting applications. Considerations include:

#### Using Debugger
#### Using Cloud Logging
#### Using Cloud Monitoring
#### Using Cloud Profiler
#### Using Cloud Trace
#### Using Error Reporting
#### Using documentation, forums, and Google Cloud support
