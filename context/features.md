# Quix Features & Benefits

This document outlines Quix's key features, benefits, and differentiators to inform content creation that drives trial conversions and customer acquisition.

---

## Start Here by Role

Different personas care about different parts of this document. Start with the sections most relevant to the audience you're writing for.

| Persona | Primary VPs | Use Case Section |
|---------|------------|-----------------|
| **R&D Director** | #1 (Config linking), #7 (Self-service), #10 (Proactive expertise) | R&D Directors |
| **Systems Engineer** | #1 (Config linking), #4 (Data warehouse), #7 (Self-service), #8 (Open architecture) | Systems Engineers |
| **Software/Data Engineer** | #2 (Infrastructure), #3 (Python), #5 (Git), #6 (Environments), #8 (Open), #9 (BYOC) | Software and Data Engineers |
| **Test Engineer** | #1 (Config linking), #7 (Self-service) | Test Engineers |

---

## Core Value Propositions

### 1. **Know exactly what configuration produced every test result** *(Configuration Context Linking)*
- **Feature**: Every test run is automatically tagged with its full hardware configuration, software version, calibration state, and maintenance context at the point of data ingestion — not as a retrospective step
- **Benefit**: Engineers can immediately answer "what produced this data?" without cross-referencing spreadsheets, chasing the test operator, or waiting on someone who has since left the team. If equipment was at the edge of its duty cycle or maintenance was overdue, that context is part of the record — so engineers know whether to trust a reading before acting on it
- **Conversion Angle**: "Know exactly what configuration produced every test run — automatically, at ingestion, with no separate tagging step"

### 2. **Production-grade infrastructure without a platform team** *(Managed Production Infrastructure)*
- **Feature**: Fully managed Kafka, Kubernetes, and Docker infrastructure — provisioning, deployment, observability, and security all handled by Quix
- **Benefit**: A single software or data engineer can stand up what would normally require a team of three to five, without opening an IT ticket
- **Conversion Angle**: "Get production-grade streaming infrastructure running in weeks — without a dedicated platform team"

### 3. **Build in Python. Own every line of code.** *(Python-Native Development)*
- **Feature**: Engineers build pipelines in Python using the Quix Streams library. AI agents can write pipeline logic automatically based on what the engineer specifies; all generated code is fully visible, reviewable, and owned by the team
- **Benefit**: Engineers stay in the language they already use. No proprietary scripting language, no black-box configuration. Code is auditable and portable
- **Conversion Angle**: "Build in Python, own your code — no vendor lock-in, no black box"

### 4. **Query your entire test history in plain English** *(Built-In Data Warehouse)*
- **Feature**: Integrated data warehouse optimised for low-latency queries across very large datasets — including high-frequency time-series data at 100kHz and above. Engineers access data via SQL, REST API, Jupyter notebooks, or purpose-built dashboards — no external data warehouse required. The Query Engine supports SQL queries, a data catalogue, targeted deletion, repartitioning, and manual compaction. A natural language SQL agent lets systems engineers query the warehouse without writing SQL themselves
- **Benefit**: Teams get a single place to store, discover, and query test history at the data resolutions they actually work with — not down-sampled approximations. Domain engineers who aren't SQL-fluent can get answers directly using natural language. No separate warehousing tool to procure, integrate, or maintain
- **Conversion Angle**: "Ask a question about your test data in plain English and get an answer — no SQL, no analyst, no waiting"

### 5. **Pipeline code lives in Git, versioned like product code** *(Git Integration)*
- **Feature**: Pipeline code lives in Git alongside test configuration — versioned, auditable, and portable. Projects in Quix correspond directly to Git repositories; environments correspond to branches
- **Benefit**: Engineers treat data pipelines like software: version-controlled, peer-reviewed, and deployable from a known state. Changes are traceable
- **Conversion Angle**: "Your pipeline code lives in Git — versioned and auditable, the same way your product code is"

### 6. **Promote changes safely from dev to production** *(Environment Isolation)*
- **Feature**: Create fully isolated development, staging, and production environments within Quix without leaving the platform
- **Benefit**: Engineers test pipeline changes safely before they affect production data streams, with no additional infrastructure to manage
- **Conversion Angle**: "Promote changes from dev to production the way you do with software — full isolation, no infrastructure work"

### 7. **Domain engineers build without waiting for IT** *(Self-Service)*
- **Feature**: Domain engineers build, deploy, and iterate on data pipelines without opening an IT ticket or waiting for a central data platform team
- **Benefit**: Eliminates the multi-year backlog that accumulates when R&D tooling requests are routed through corporate IT or data science teams with other priorities
- **Conversion Angle**: "Build what your team needs this week — without a Jira ticket and a six-month queue"

### 8. **Your code, your data, your standards** *(Open Architecture)*
- **Feature**: Engineers own their code, their configuration, and their data. Quix runs on open standards (Kafka, Python, Docker). Data is not locked into proprietary formats
- **Benefit**: Teams avoid the dependency risk common with enterprise platforms — if they ever leave Quix, their pipelines and data go with them
- **Conversion Angle**: "No black box, no lock-in — your code and data are yours"

### 9. **Data stays in your cloud account** *(Bring Your Own Cloud — BYOC)*
- **Feature**: Deploy the Quix data plane inside the customer's own cloud account (AWS, GCP, or Azure) while Quix manages the control plane
- **Benefit**: Data never leaves the customer's infrastructure — satisfies security, compliance, and data sovereignty requirements without sacrificing the managed service experience
- **Conversion Angle**: "Keep data inside your own cloud account — with all the operational benefits of a managed service"

### 10. **We propose solutions you haven't thought to ask for yet** *(Proactive Expertise)*
- **Feature**: Quix engineers bring domain knowledge of R&D and test data workflows — not just platform knowledge. They identify problems the customer hasn't named and propose solutions proactively, based on experience across dozens of engineering programmes
- **Benefit**: Customers get a partner who shapes the solution based on deep understanding of their environment — not a vendor who executes exactly to spec and stops there
- **Conversion Angle**: "We gave you the problem. You said, okay, we have an idea. That was completely new for us — all the others did more or less what we said." — Viessmann

---

## Technical Features

### Data Infrastructure
- **Managed Kafka**: Production-grade message streaming without self-hosting or managing brokers
- **Kubernetes orchestration**: Container scheduling, scaling, and fault recovery — fully managed
- **Docker-native deployment**: Pipeline services run in containers; consistent behaviour across all environments
- **Built-in observability**: Pipeline health, throughput, and error monitoring included from day one
- **Auto-scaling**: Infrastructure scales with data volume without manual intervention
- **Horizontal scaling**: Distribute workloads across multiple consumer replicas for high-throughput scenarios

### Configuration Management
- **Configuration context tagging**: Hardware state, software version, calibration state, and maintenance history linked to every test run at ingestion
- **Configuration snapshot**: Point-in-time capture of configuration state at the moment of test execution
- **Configuration validation**: Checks that configuration makes logical sense before it is used
- **Dynamic Configuration**: Real-time configuration management allowing updates without restarting pipelines
- **Delta configuration**: Track and query differences between configuration versions over time
- **Configuration join**: Merge configuration data with measurement data in real time during ingestion

### Data Management
- **Built-in data warehouse**: Store, query, and retrieve historical test data without external tools
- **SQL access**: Query test history using standard SQL from notebooks, BI tools, or direct API calls
- **REST API**: Programmatic access to all data and pipeline management functions
- **Jupyter notebook integration**: Analyse test data directly in notebooks connected to the warehouse
- **Schemaless ingestion**: Write data without a predefined table structure; schema evolves with the data. Test rig outputs change with firmware updates and hardware swaps — Quix ingests without requiring schema migrations, breaking changes, or maintenance windows
- **High-frequency data support**: Warehouse is optimised for low-latency queries across very large, high-resolution datasets — including 100kHz time-series data at full resolution, without down-sampling
- **Reprocessing**: Re-analyse historical data with new configurations or updated processing logic
- **Replay**: Replay historical test data through pipelines as if it were live — enables debugging, validation, and model development without access to a test rig

### Pipeline Development
- **Quix Streams**: Open-source Python client library for building stream processing applications
- **StreamingDataFrame (SDF)**: DataFrame-like API for real-time data — familiar to engineers who use pandas
- **AI-assisted code generation**: Describe the transformation logic; AI agents write the Python — all code is visible and editable
- **Source / Transform / Destination pattern**: Standard pipeline component model; pre-built code samples available for common connectors
- **Dynamic topic routing**: Route messages to different Kafka topics based on message content at runtime — no hardcoded pipeline logic
- **Stateful operators**: Operations that maintain state across messages for windowing, aggregation, and complex event detection
- **Windowing**: Group stream data into tumbling or sliding time windows for aggregation

### Infrastructure as Code
- **quix.yaml**: Single file defining the entire pipeline — deployments, topics, and variables — checked into Git
- **app.yaml**: Per-application configuration file defining inputs, outputs, and settings
- **YAML synchronisation**: Quix Cloud stays in sync with the Git repository; changes in Git propagate to the platform

### Deployment & Operations
- **Environment management**: Dev, staging, and production environments isolated within the platform
- **One-click deployment**: Push pipeline changes from Git to production without additional infrastructure steps
- **Rolling updates**: Deploy new pipeline versions without downtime
- **Secrets management**: API keys and credentials stored securely, not in pipeline code
- **Audit trail**: Complete history of configuration changes, deployments, and data access
- **Logs and metrics**: Real-time application logs, CPU, and memory monitoring for all deployments
- **Data explorer / Topic explorer**: UI for viewing live data flowing through any Kafka topic
- **Multi-cloud**: Deploy to AWS, GCP, or Azure; or use Quix Cloud's managed hosting
- **On-premises support**: Deploy in on-premises environments where data cannot leave the facility

### Security & Compliance

**Current certifications:**
- **ISO 27001 certified**: Information security management certification
- **SOC 2 in progress**: Security, availability, and confidentiality controls audit underway
- **GDPR compliant**: GDPR requirements are met through ISO 27001 and SOC 2 controls — no separate GDPR certification

**Not currently certified** (for content accuracy — do not claim these): HIPAA, PCI-DSS, FedRAMP, TISAX, HITRUST, CCPA, IRAP, UK Cyber Essentials Plus. These are held by competitors like Databricks. Note: TISAX would be strategically valuable for automotive OEM customers.

**Data residency:**
- Self-hosting (BYOC on public clouds) and on-premises deployment with multi-cluster, multi-region support — customers can meet their own data residency requirements without Quix holding the data
- In BYOC deployments, data never leaves the customer's own cloud account or facility

**Platform security:**
- **BYOC data isolation**: Data stays within the customer's own infrastructure in all BYOC and on-premises deployments
- **Air-gapped deployments**: Available on Critical plan — fully isolated from public internet
- **Secrets management**: Credentials stored securely outside pipeline code, accessible to deployments at runtime
- **PAT tokens and permission system**: Granular access control for users, projects, and environments
- **User audit system**: Full audit trail of portal actions (Critical plan) for compliance reporting
- **Custom security controls**: Available on Critical plan for mission-critical programmes

---

## Integrations & Ecosystem

### The Core Framing: Integrate with Anything

Quix provides open Python frameworks — the Sources API and Sinks API in Quix Streams — for building connectors to any data source or destination. Both follow simple base class patterns: implement a handful of methods, and you have a production-ready connector. This is the correct framing for content:

**The integration story is not "here is our connector list." It is: Quix integrates with anything, because the framework is open and Quix AI builds the connectors.**

With Quix AI, an engineer describes what they need to connect to — a proprietary instrument, an internal database, a legacy system with no documented API — and the AI writes the connector. The framework handles subprocess management, Kafka topic wiring, batching, backpressure, and state management. The engineer describes the system; Quix AI builds the integration.

This means the answer to "can you connect to X?" is always yes.

### Built-In Source Connectors
Ready-made connectors available without custom code:
- **DACQ systems**: Acromag, Crystal Instruments, Dewesoft, Dewetron, Gantner Instruments, HBK, Keysight, Kistler, Measurement Computing, National Instruments
- **MQTT**: Ingest from MQTT brokers (common in test rig and IoT environments)
- **Telegraf**: Collect metrics from systems, servers, and devices
- **RabbitMQ**: Ingest from RabbitMQ queues
- **MATLAB/Simulink**: Ingest simulation model outputs directly into pipelines
- **File listener**: Monitor network drives or directories for new DACQ output files
- **Amazon Kinesis, Google Pub/Sub**: Cloud messaging sources
- **InfluxDB**: Ingest from InfluxDB time-series databases
- **File-based sources**: S3, Azure Blob Storage, local filesystem

**Supported measurement file formats**: All binary and measurement file formats are supported — MDF4/MF4 (ASAM standard, dominant in automotive), BLF (Vector CANalyzer), TDMS (National Instruments), HDF5 (aerospace/scientific), MAT (MATLAB), Parquet, CSV. If it comes out of a test rig, Quix can ingest it.

### Built-In Sink Connectors
Ready-made connectors for sending processed data downstream:
- **InfluxDB** (v1 and v3): Time-series storage for dashboarding
- **Google BigQuery**: Analytics data warehouse
- **Amazon S3 / S3 Iceberg**: Object storage and open table format
- **Azure Blob Storage**: Cloud object storage
- **Apache Iceberg**: Open table format for data lakes
- **Amazon Kinesis**: Stream to AWS downstream consumers
- **Google Cloud Pub/Sub**: Publish to GCP services
- **PostgreSQL**: Relational database
- **MongoDB**: NoSQL document database
- **Neo4j**: Graph database
- **MQTT**: Publish to MQTT brokers
- **CSV / Local File**: File-based output
- **Jupyter notebooks / SQL clients**: Direct query access via the built-in warehouse

### Custom Connectors via the Framework
When a built-in connector does not exist, engineers build one using the Quix Streams Sources API or Sinks API. The base classes handle the hard parts — Kafka topic wiring, subprocess management, batching, backpressure signalling, and state persistence. Engineers implement the system-specific fetch or write logic. With Quix AI, even this step is automated: describe the target system, and the AI writes the connector code.

### Managed Kafka Options
- **Quix-managed Kafka**: Kafka cluster operated entirely by Quix — no broker management required
- **Self-hosted Kafka**: Connect Quix pipelines to an existing customer-operated Kafka cluster
- **Confluent Cloud**: Use Confluent's managed Kafka as the message broker with Quix for pipeline management

### Development Tools
- **Quix CLI**: Command-line tool for local development, testing, and deployment from a terminal
- **Quix IDE**: Online integrated development environment for Python pipeline development
- **Local development with Docker Desktop**: Build and test pipelines on a local machine before deploying to cloud
- **CI/CD integration**: Automated build and deployment pipelines built into the Git workflow

---

## Competitive Differentiators

### vs. Enterprise Platforms (Siemens Polarion, Dassault Enovia, dSPACE, ETAS)
- **No process standardisation required**: Enterprise platforms impose uniform workflows across deliberately diverse R&D programmes; Quix adapts to existing processes
- **Python-native, not proprietary scripting**: Enterprise tools use vendor-specific interfaces; Quix engineers work in Python they already know
- **Weeks to value, not months**: Enterprise deployments typically take 6–18 months; Quix teams are running in weeks
- **Engineers self-serve**: Enterprise platforms require vendor support or dedicated internal teams to make changes; Quix is self-service for domain engineers
- **Proactive expertise**: "We gave you the problem. You said, okay, we have an idea. That was completely new for us — all the others did more or less what we said." (Viessmann)

### vs. Custom IT Builds
- **Domain knowledge built in**: Generic IT vendors build to spec but don't understand R&D workflows; Quix was built by engineers who worked in this environment
- **Production-grade from day one**: Custom builds accumulate technical debt; Quix provides managed infrastructure that doesn't require ongoing maintenance by the customer
- **Faster iteration**: Custom builds require IT involvement for every change; Quix engineers iterate independently
- **Not order-taking**: Quix proposes solutions beyond what was specified — a fundamentally different experience from vendors who deliver exactly what they were asked for

### vs. Corporate Data Science Teams
- **Available now**: Data science teams have competing priorities; R&D tooling requests often wait years
- **R&D-specific**: Corporate data science teams build general-purpose infrastructure; Quix is built for test and measurement data workflows
- **Engineer-operated**: Data science teams create dependencies; Quix is self-service for domain engineers who want to build autonomously

---

## Use Cases by Customer Segment

### Systems Engineers and Development Engineers

**Works alongside existing tools**: Quix does not replace DACQ software, LabVIEW, Dewesoft, National Instruments, or existing test management systems. It connects to them. Test operators change nothing about how they run tests; Quix captures configuration and data at ingestion automatically. The integration is invisible to the people running tests.

- Find specific historical test runs matching a configuration or scenario in seconds, not hours — no manual search across network drives, spreadsheets, or SharePoint folders
- Know whether a sensor reading is real: hardware state, calibration history, and maintenance records are linked to every test run at the point of capture. If equipment was at the edge of its duty cycle, had not been serviced, or was operating outside spec, that context is part of the record before anyone asks
- Protect the configuration record: if a technician who ran a test leaves the organisation, the hardware state, software version, and calibration state for that run are already captured in Quix. A Garrett team avoided rerunning an 800,000-euro wire harness test because the configuration record was preserved after the original operator left
- Compare current results against historical baselines with full configuration traceability — distinguish whether a difference comes from changed hardware, changed software, or genuine system behaviour
- Validate supplier data: bring in test and simulation data from external suppliers and check it against configuration and measurement standards before acting on it
- Build custom dashboards and visualisations directly on top of test data without involving IT
- *Coming soon*: Query the data warehouse in plain English — ask "which test runs used firmware version 3.2 on rig 4?" and get a direct answer, without writing SQL or waiting on a data engineer

### R&D Directors and Heads of Engineering

**What changes**: R&D cycle time falls without adding headcount or lab capacity. Redundant tests get replaced by searches. Data infrastructure stops being a dependency on IT, a data science team, or a preferred vendor that executes to spec without proposing anything.

**Evidence**: Viessmann reduced testing time by a factor of 2.5, achieved 50% faster feature development, and cut software testing time by 75% — through automated engineering workflows that freed engineers to focus on performance and innovation. Separately, a Garrett engineer identified that a test had run for three weeks without recording any data because a USB connector had been knocked loose and the LabVIEW error appeared on an unmonitored screen. When a wire harness test configuration record was lost after a technician left, rerunning the test would have cost 800,000 euros and taken 18 months. The configuration context Quix had captured made it recoverable.

- Eliminate redundant testing: every historical test run is searchable by hardware state, software version, and test scenario — engineers check the archive before booking a rig
- Reduce R&D cycle time without adding headcount or lab capacity — Viessmann: 50% faster feature development, 75% reduction in software testing time, 2.5x cheaper testing
- End the wait: domain engineers build data capabilities themselves, without routing requests through IT, a central data science team, or a vendor who needs to be briefed before anything changes
- Coordinate test data, configuration, and workflows across multiple sites, rigs, and simulation environments — without moving data across jurisdictions or requiring uniform processes at each location
- Start with one rig, prove the value before committing full budget — most teams have their first pipeline running in weeks, not months
- Get visibility into lab utilisation, data throughput, and where bottlenecks are forming across the programme

### Software and Data Engineers

**The goal**: systems engineers and development engineers get data capabilities and self-service access without routing every request back through you. Here is what that requires, and what Quix handles.

- Stand up production-grade streaming infrastructure (Kafka, Kubernetes, observability) without building or managing a platform team — one engineer runs what normally requires three to five
- Connect diverse test rigs and data sources without writing custom integration code from scratch — Quix AI builds connectors for any system, including proprietary instruments and legacy setups with no documented API
- Stop being the schema migration bottleneck: Quix ingests without a predefined schema, so firmware updates and hardware changes in test rigs don't create migration work or maintenance windows
- Domain engineers query the data warehouse themselves, in plain English, without coming back to you for every ad hoc question. *Coming soon*: the natural language SQL agent turns engineering questions into direct answers
- Build the internal business case with named outcomes: Viessmann achieved 50% faster feature development, 75% reduction in software testing time, and 2.5x cheaper testing — specific numbers for an R&D Director budget conversation
- Manage dev, staging, and production environments cleanly within the platform — promote pipeline changes the way you do with product software
- Build and iterate in Python without learning proprietary scripting languages; all code lives in your own Git repositories and is portable if you ever move off the platform

### Test Engineers

**Invisible by design**: Quix works in the background. Test operators do not change how they run tests, what tools they use, or how they interact with test rigs. Whatever format the DAQ system or instrument outputs — MDF4, TDMS, MATLAB, CSV, binary — it goes in automatically. No export step, no format conversion, no manual file transfer at the end of a run.

**A typical day, before and after**: Previously, a test engineer would finish a run, manually copy output files to a network drive or SharePoint folder, label them in a spreadsheet, and email the team. With Quix, data flows upstream automatically at the point of capture. Configuration is recorded at execution. The engineer runs the next test.

- Every test run automatically captures the full configuration at the point of execution — no manual logging required, no separate tagging step after the fact
- Test data is immediately available downstream without export, format conversion, or manual handoff steps
- Configuration lag (delay between test execution and config availability) is eliminated by joining configuration to data at ingestion
- Live data monitoring during test execution — if a sensor drops, a connection is lost, or data stops flowing, it is visible immediately rather than discovered days or weeks later (customer evidence: a Garrett engineer discovered a test had run for three weeks without recording any data because a USB connector had been knocked and the LabVIEW error appeared on an unmonitored screen)
- Automatic upstream data flow to cloud or on-premises storage — no manual file transfers between test runs
- Configuration context is answerable retroactively — "what was the hardware state on test run 47?" has an answer, even after the technician who ran it has left the organisation (see also: R&D Director section — the Garrett wire harness configuration recovery)
- High-volume, high-frequency data handled at full resolution — millisecond-precision ingestion at 2TB/day or more, with the ability to zoom into any 100ms window for root cause investigation (customer evidence: Jakub at Garrett needed 10 data points per second on 25 channels for three months — no standard tool could open the resulting files)
- Root cause investigation compressed from days to hours — when something goes wrong during a test, relevant data is already structured, tagged, and queryable; engineers go directly to the data rather than into a 10-person brainstorm meeting

---

## Pricing & Plan Benefits

### The Buying Journey

Most teams follow this path: free trial or direct POC conversation → fixed-price POC engagement (1–3 months) → Professional or Scale plan based on deployment requirements. No prospect in the customer record went from first contact to a production plan commitment without an intermediate evaluation. The POC model is not an option — it is the standard route.

### Proof of Concept (POC) Engagements

A fixed-price, time-bound engagement — typically 1–3 months — to prove Quix works with a team's specific rigs, data formats, and configuration requirements before committing to a production plan. Quix runs the POC alongside the engineering team, connecting the first data source, standing up the pipeline, and demonstrating configuration context linking with real data.

- **Duration**: 1–3 months, scoped to a single rig or data source
- **Outcome**: Working pipeline with live or historical data, configuration context captured, team has run their first queries
- **Why it works**: Every customer in the interview set (Wingcopter, Evolito, HAWE, Origen Carbon, Rolls-Royce, Modelon) cited the ability to start small and prove value as the decision factor — not feature lists or pricing tier comparisons
- **Transition**: Most teams move from POC directly to Professional. Organisations with private cloud or on-premise requirements move to Scale

### Free Trial
- 30 days, no credit card required
- Includes Professional tier resource quotas during trial
- Community Slack support, no SLA
- Target: Engineering teams evaluating Quix before committing budget or before scheduling a POC conversation

### Professional — from £4,200/month
- BYOC hosting on public clouds (AWS, GCP, Azure)
- User and project management, PAT tokens, permission system
- Private templates
- Full core platform features
- Target: Organisations with strict data governance requirements that need their data in their own cloud account. The standard post-POC plan for teams running on AWS, GCP, or Azure

### Scale — from £14,200/month
- All Professional features, plus:
- BYOC on private clouds and on-premise
- Multi-cluster support (multiple sites, isolated environments)
- Single Sign-On (SSO)
- Advanced monitoring
- Target: Large engineering organisations needing enterprise performance, compliance, on-premise deployment, or coordination across multiple sites. Typical for automotive OEMs, aerospace programmes, and multi-facility R&D organisations

### Critical — custom pricing
- All Scale features, plus:
- Air-gapped hosting on private clouds and on-premise
- Custom networking and custom security controls
- User audit system
- Target: Mission-critical programmes (aerospace, defence, safety-critical automotive) requiring the highest security and operational isolation

### Open Source — free
- Quix Streams Python library and CLI are permanently free
- Target: Individual engineers and teams building on the open-source stack

---

## Key Messaging for Conversions

### Trial / Demo Conversion Messages
- "Book a 30-minute walkthrough — see configuration linking in action with your data type"
- "Start with one rig. Prove the value before committing budget."
- "A single engineer can have this running in weeks — no IT ticket required"
- "See how engineering teams at Williams Racing and Viessmann find historical test data in seconds"

### Pain Point Solutions
- **"We can't find the right historical test data without spending hours on it"** → Quix links every test run to its full configuration at ingestion — test history is immediately searchable by hardware state, software version, or scenario
- **"We keep booking tests we've probably already run"** → Configuration traceability means you know exactly what produced every historical result — redundant tests get replaced by a search
- **"IT has been promising us data tooling for two years"** → Quix is self-service for domain engineers; no IT dependency, no queue
- **"We tried [enterprise platform] and it took 12 months to get anything running"** → Quix teams run their first pipeline in weeks; start with one rig, expand from there
- **"We don't want to be locked into a vendor"** → Engineers own their code, configuration, and data; Quix runs on open standards (Kafka, Python, Docker)
- **"Our data never leaves our infrastructure"** → BYOC deploys the data plane inside your own cloud account; Quix manages the control plane only

### Social Proof
- Customers cleared for public reference: Viessmann, Ju:niz, Cloud NC, Williams Racing, SMS Group, Fifer Vacuum, Alpine F1 Racing Team, Audi Formula 1 Racing Team
- **NOT cleared for public reference**: Gulfstream — do not name in published content
- **Viessmann Climate Solutions**: 50% faster feature development, 75% reduction in software testing time, 2.5x cheaper testing. "We reduced testing time by a factor of 2.5 by automating engineering workflows, freeing engineers on model performance and innovation."
- **Ju:niz**: 30TB data processed monthly, 1,500x increase in data collection capacity, 100x cheaper data storage
- **Williams Racing**: Public reference cleared
- **Alpine F1 Racing Team**: Public reference cleared
- **Audi Formula 1 Racing Team**: Public reference cleared
- **Cloud NC**: Public reference cleared
- **SMS Group**: Case study available
- **Fifer Vacuum**: Public reference cleared
- "We gave you the problem. You said, okay, we have an idea. That was completely new for us — all the others did more or less what we said." — Viessmann
- Scale signals: named customer logos (three F1 teams, Viessmann, SMS Group, Cloud NC, Fifer Vacuum) are more credible than aggregate numbers for this audience — use named references in content rather than generic volume claims

---

## Common Questions & Objections

### "How long does it take to get set up?"
**Answer**: Most teams have their first pipeline running within a few weeks. You start with one rig or data source, prove the value, then expand. Quix handles the infrastructure — engineers focus on connecting their data and building the logic they need.

### "Do we need a dedicated data engineer to run this?"
**Answer**: No. Quix is designed so domain engineers — systems engineers, development engineers — can build and operate pipelines themselves. A single software or data engineer can manage the infrastructure for a larger team. You do not need to build or hire a platform team.

### "What happens to our data and code if we stop using Quix?"
**Answer**: Pipeline code is in Python in your own Git repositories. Data is accessible via SQL and REST API and is not stored in proprietary formats. If you leave, both go with you.

### "We already have Siemens / Dassault / ETAS. Why do we need Quix?"
**Answer**: Enterprise platforms impose standardisation across R&D programmes that are deliberately diverse, and require vendor support for most changes. Quix handles the data infrastructure layer that enterprise platforms don't cover — connecting test rigs, linking configuration context at ingestion, making historical data searchable — and adapts to existing workflows rather than replacing them.

### "Can Quix handle our data volumes?"
**Answer**: Yes. Quix handles high-frequency, high-channel-count data in production. Fifer Vacuum runs 100kHz time-series data through Quix at full resolution. Formula 1 teams use Quix to process kHz-frequency data across 50,000 channels simultaneously. The data warehouse is specifically optimised for low-latency queries across datasets of this scale — full resolution, no downsampling required.

### "Can Quix connect to our existing test rigs and DACQ systems?"
**Answer**: Yes. Quix has source connectors for the most common DACQ platforms — Dewesoft, Dewetron, National Instruments, HBK, Keysight, Kistler, Gantner Instruments, Crystal Instruments, Measurement Computing, and Acromag. For systems without a dedicated connector, the file listener monitors network drives or directories for new output files and ingests them automatically. Quix supports all binary and measurement file formats used in the industry, including MDF4/MF4, BLF, TDMS, HDF5, MAT, Parquet, and CSV. If data comes out of a test rig in any format, Quix can handle it.

### "What does this cost?"
**Answer**: Quix is priced for large organisations. Plans start at £4,200/month (Professional, BYOC on public cloud) and £14,200/month (Scale, private cloud and on-premise). A 30-day free trial with no credit card is available. For enterprise deployments, custom pricing applies. See quix.io/pricing or book a walkthrough to discuss requirements.

---

## Upcoming Features

These features are in development or going live soon. Do not present them as current capabilities — use "coming soon", "in development", or confirm GA date before writing about them as available.

### Data Warehouse — Query Engine & Advanced Capabilities
- **Query Engine**: Core engine enabling SQL queries directly against the Quix data warehouse — engineers can query test history, measurement data, and configuration records without an external analytics tool
- **Catalogue**: Browse and discover what data is available in the warehouse — datasets, schemas, and stored test runs — so engineers can find what they need before querying
- **Delete**: Remove specific data from the warehouse — individual test runs, datasets, or records — giving teams control over what is retained
- **Repartition**: Reorganise stored data by a new key for more efficient querying — for example, repartitioning by vehicle ID or test campaign rather than ingest time
- **Manual Compaction**: Merge and consolidate historical data files to reduce storage footprint and improve query performance over time
- **Natural Language to SQL Agent**: A data analytics engineer agent that accepts natural language questions and writes the SQL query — systems engineers and domain experts can interrogate the data warehouse without knowing SQL. Ask "which test runs used firmware version 3.2 on rig 4?" and get an answer directly
- **Portal API V2** (REST, authenticated with secure tokens): A complete REST API covering every operation available in the Quix Cloud portal. Key capability groups: application lifecycle (create, configure, version, export, import), deployment management (deploy, stop, update, rollback), environment and workspace administration, project and organisation management, data lake catalogue and storage tier configuration, cluster and Kafka broker management, Git integration, container registry management, secrets management, and a full audit trail for compliance. If you can do it in the portal, you can automate it via API. Intended consumers: CI/CD pipelines, internal tooling, IT/ops teams integrating Quix into existing infrastructure management workflows, and customers building on top of the Quix platform.

### Quix AI — Agentic Application Builder (coming soon)
An AI assistant embedded directly in the Quix portal, designed to let engineers describe what they want to build and have it built — without leaving the platform.

**How it works**:
- Engineers interact via a chat interface inside the Quix portal
- Quix AI is context-aware: it knows which page the engineer is on, which environment and pipeline they're working in, and what topics and deployments exist
- For simple queries and planning tasks, Quix AI responds directly using platform context injected via MCPs (Model Context Protocol) — giving the AI access to platform capabilities like listing topics, reading environment details, and visualising pipeline architecture without expensive token-heavy reasoning
- For tasks that require code generation or deployment — building a Python application, writing to a topic, restructuring a pipeline — Quix AI spawns an **AI Dev Session**: a secure, isolated agent running Claude Code in the deployments cluster that works on the task and streams progress back to the engineer in real time
- The AI Dev Session runs with full Quix platform knowledge injected, and respects any project-specific skills or knowledge the engineer has added as markdown files in their Git repository (domain knowledge, architecture patterns, team conventions)
- Once the dev session completes its task, the engineer is prompted to sync the changes into their environment

**What engineers can do with it**:
- Describe a Python application in natural language — Quix AI plans it, then builds and deploys it
- Generate architecture diagrams (Mermaid) from the current pipeline state
- Ask questions about the current workspace, environment, or pipeline
- Plan and validate architectural changes before implementation
- Build domain-specific intelligence into the agent by adding knowledge files to their repository — e.g., team-specific ICD formats, calibration workflows, application design patterns

**Production-ready by design**:
- Centralized API key management: companies use a single Quix-managed key; individual users do not need their own LLM licenses or accounts
- Prompt injection protection: credentials are never exposed through the agent interface
- Token rate limiting per user to prevent runaway usage
- Full decision traceability: all agent tool calls and reasoning steps are logged — important for aerospace and other regulated environments
- Secure credential storage for user-brought keys

**Primary persona**: Systems engineers and R&D leads — the domain experts who understand the engineering problem deeply but don't have the software or data engineering background to build data pipelines, analytics applications, or complex database queries themselves. Quix AI gives them the ability to build and query without depending on a software engineer or data engineer to do it for them.

**Content note**: Position this as "AI that works like a senior software and data engineer" — not a chatbot, not a code generator, but an agent that lets a systems engineer build data infrastructure, data pipelines, analytics applications, and run complex data queries on their own. The value is self-sufficiency: the engineer who understands the problem can now also build the solution, without waiting for someone else's help or availability.

---

## Content Creation Guidelines

When writing about Quix features:

1. **Lead with the engineering problem, not the feature name**: Don't say "configuration context linking" — explain "you can immediately see what hardware state, software version, and calibration produced any test result"
2. **Use customer evidence**: "Gulfstream engineers" beats "our customers"; "reduced time from hours to minutes" beats "faster insights"
3. **Acknowledge what's been tried**: This audience has usually failed with enterprise platforms, IT builds, or data science teams first — acknowledging that history builds credibility
4. **Address the failed alternatives explicitly**: Viessmann language is available and cleared; use it. Do not reference Gulfstream in published content — not cleared for public reference
5. **One CTA per piece**: "Book a 30-minute walkthrough of the configuration linking demo" — not three options
6. **No pressure language**: "See how it works" not "Don't miss out" — this audience makes decisions methodically

---

*Update this document when new features ship, pricing changes, customer references are cleared, or specific integration support is confirmed. Keep social proof current — named customers and specific numbers carry far more weight than claimed benefits.*
