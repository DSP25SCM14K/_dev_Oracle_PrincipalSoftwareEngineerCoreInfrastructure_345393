# Oracle Principal Software Engineer, Core Infrastructure — 345393
Research completed October 10, 2026, using the exact careers posting and official Oracle documentation.

## Verified role
The posting is a regular individual contributor position in Nashville, Product and Research, posted September 14, 2026. It asks engineers to lead and begin architecting scalable distributed components, optimize high-throughput data paths, define scaling requirements, and operate production cloud services. Core concerns include state management, replication, partition policies, recovery, in-service upgrades, fault injection, brownouts, telemetry, security remediation and infrastructure automation. Programming options include Java, Python, Go, C++ and C#. Education/experience routes include eight years’ software development, or degree-based alternatives. The metadata’s 6–10+ years is distinct from these detailed alternatives. [Oracle careers: 345393](https://eeho.fa.us2.oraclecloud.com/hcmUI/CandidateExperience/en/sites/jobsearch/job/345393/)

**Interpretation:** This is a component architecture and operational ownership role. The strongest portfolio narrative connects state correctness, scalable data paths and recovery behavior. Hardware/NPI appears in the resume but is not an explicit emphasis in the verified job description; it remains in experience without dominating the hero.

## Oracle and OCI context
Oracle offers compute, networking, storage, databases, containers, integration, and security/management services within OCI, with public, dedicated, hybrid and multicloud deployment choices. [Oracle Cloud Infrastructure](https://www.oracle.com/cloud/)

**Interpretation:** Infrastructure primitives support many workloads and service dependencies. Availability and performance decisions should be explained as operational trade-offs, not presented as isolated language or cloud badges. The public site uses an original architectural visual rather than Oracle branding or claims of Oracle employment.

## Technical research

### Resource lifecycle and compute boundaries
OCI provides bare metal and virtual-machine instances. Bare metal offers dedicated physical resources; virtualization supports isolated environments sharing physical hardware. Attached volume changes survive instance termination, while local-drive changes do not. Compute capacity availability and service limits are separate concerns. [Compute service overview](https://docs.oracle.com/en-us/iaas/Content/Compute/Concepts/computeoverview.htm)

**Design implication:** A service architecture must distinguish compute lifecycle from durable state. The portfolio depicts state and data paths separately and highlights safe upgrades rather than treating a host’s continued existence as the durability strategy.

### Failure domains and regional recovery
OCI regions contain one or more availability domains. Availability domains isolate power, cooling and internal network infrastructure. Regions are independent and may be far apart. Cross-domain and cross-region placement can address different failure risks, with locality affecting latency. Oracle documents that many regions have one availability domain; designs should not assume every region has three. [Regions and availability domains](https://docs.oracle.com/en-us/iaas/Content/General/Concepts/regions.htm)

**Design implication:** Replication topology should follow actual failure boundaries and latency requirements. The resume’s RPO and RTO remain candidate-reported results from drills, not generic guarantees. The concept map illustrates relationships without inventing a real deployment topology.

### Metrics that support recovery
OCI Monitoring supports service resource metrics and custom metrics, querying aggregated data with intervals, statistics and dimensions. Metrics describe health, capacity and performance; alarms notify configured destinations when conditions are met. Application availability, latency, transaction outcomes and failure rates can help relate infrastructure behavior to service commitments. [Monitoring overview](https://docs.oracle.com/en-us/iaas/Content/Monitoring/Concepts/monitoringoverview.htm)

**Design implication:** Telemetry needs a decision attached to it: diagnose a constraint, change capacity, halt a rollout, or begin recovery. The site’s operations narrative connects measurements to action. Moving diagram packets and bars are illustrative animation, not live service metrics.

### Repeatable infrastructure changes
Oracle Resource Manager uses declarative Terraform configurations, stacks and jobs, with state management and drift detection. Its documented workflow produces a plan, reviews it, then applies the desired changes. Drift describes differences between actual resources and the stack’s last executed configuration. [Resource Manager overview](https://docs.oracle.com/en-us/iaas/Content/ResourceManager/Concepts/resourcemanager.htm)

**Design implication:** The resume’s staged rollouts and IaC support a story of intentional, recoverable changes. The website’s lifecycle finishes with telemetry, health checks and rollback decisions. It does not imply that Terraform alone makes software updates safe.

## Resume-to-role analysis
All career results below originate in the supplied resume and have not been independently verified as employment facts.

| Role concern | Candidate evidence | Portfolio treatment |
|---|---|---|
| Availability and state | 99.99% on 12K+ control/data-plane nodes | Hero and fleet metrics |
| Data-path scale | 3x throughput; 50K+ RPS; p99 under 80 ms | Throughput chip and exact experience bullet |
| In-service change | 3,000+ upgrades without customer maintenance windows | Career metric and lifecycle |
| Observability and incidents | MTTR reduced 45%; incidents reduced 40% | Operations node and full bullet |
| Recovery design | RPO under 5 seconds; RTO under 2 minutes | Full DR experience bullet |
| Fault behavior | 30+ resilience defects surfaced preproduction | Failure exercise lifecycle stage |
| IaC and patching | Failed changes reduced 70%; deployment time reduced 60% | Full experience bullet |
| Security | Critical vulnerabilities closed within SLA | Full encryption/access/remediation bullet |
| Durable metadata | Keystone validated across 41 injected faults | Featured project with source |
| Storage data plane | Strata WAL, replica sync and throttling | Featured project with source |
| Hardware breadth | NPI yield and firmware/device diagnostics | Preserved in work experience |
| Mentoring | Six engineers at Sprouts; five at Tata | Preserved in exact work bullets |

## Engineering narrative and design
The hero introduces scale and recovery. The background is an animated architectural image of a state leader, replica, data path and recovery tooling. The central concept diagram connects control plane, data plane, replication and operations. The lifecycle explains boundaries, profiling, failure exercises and in-service changes. These are original conceptual illustrations, not claimed diagrams of an employer’s internal architecture.

Curiosity is expressed through questions about lagging replicas, slow dependencies and unexpected rollout behavior. The narrative connects those questions to code, evidence and clearer runbooks without explicitly mentioning job targeting.

All 15 experience bullets are retained verbatim. Keystone and Strata descriptions follow this resume. All 23 distinct supplied projects are included, with duplicate EXPOS entries merged. “Technical Demo” appears only on the four provided demo URLs. Paper and certificate use their own labels. No LinkedIn and no footer are included.

## Useful discussion topics
These are preparation suggestions inferred from the role, not claimed Oracle interview questions:
- Explain a partition policy and the availability/correctness trade-off behind it.
- Show how request-rate and tail-latency targets guided a data-path change.
- Explain how throttling or load shedding prevents a dependency failure from spreading.
- Describe a rolling upgrade’s readiness, stop and rollback criteria.
- Connect a fault-injection scenario to a specific invariant or recovery objective.
- Explain how telemetry and incident findings changed the next design.

## Limits
The resume is the authority for personal claims. The job posting is the authority for role expectations. Product documentation supplies company and technical context. Research does not establish Oracle’s internal topology, specific interview process, or independent correctness of the project implementations.

