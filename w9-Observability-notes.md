# w9-Observability — Notes

## Slide 1
- Cloud Services 2
- Amazon Web Services

## Slide 2
- Observability

## Slide 3
- (OCR missing for image5.jpg)

## Slide 4
- (OCR missing for image6.jpg)

## Slide 5
- Modern Application Development Architectural Patterns
- Microservices: Componentization, business capabilities, products not projects, infrastructure automation
- Serverless: No provisioning/management, automatic scaling, pay for value billing, availability and resiliency
- DevOps: Cultural philosophies, cross-disciplinary teams, CI/CD, automation tools

## Slide 6
- Approaches to Modern Application Development
- Simplify environment management
- Reduce impact of code changes
- Automate operations
- Accelerate delivery of new, high-quality services
- Gain insight across resources and applications
- Protect customers and the business

## Slide 7
- Approaches to Modern Application Development
- Simplify environment management with serverless technologies
- Reduce impact of code changes with microservice architectures
- Automate operations by modeling applications & infrastructure as code
- Accelerate delivery with CI/CD
- Gain insight across resources and applications by enabling observability
- Protect customers and business with end-to-end security & compliance

## Slide 8
- Approaches to Modern Application Development
- Gain insight across resources and applications by enabling observability

## Slide 9
- Microservices Increase Release Agility
- Monolithic application vs Microservices comparison
- Microservices allow independent deployment

## Slide 10
- (OCR missing for image10.jpg)

## Slide 11
- Microservices Architecture Components
- Services: Notes, Database
- Teams: Service Ownership
- Node.js services with separate databases

## Slide 12
- Microservices with Node.js and Databases
- Service teams own their Node.js services
- Infrastructure team manages core resources
- Multiple databases across services

## Slide 13
- Containers in Microservices Architecture
- Container-based deployment
- Services in containers with associated databases
- Database per service pattern

## Slide 14
- Proactive Operations Helps Mitigate Issues
- Timeline showing outage, latency, degraded state
- Time measurement (ms)
- Faster detection and response

## Slide 15
- Operational Excellence
- (Visual diagram, details not captured)

## Slide 16
- Observability Definition
- In control theory, observability is a measure of how well internal states of a system can be inferred from knowledge of its external outputs
- Source: https://en.wikipedia.org/wiki/Observability

## Slide 17
- Levels of Observability
- Network level
- System level
- Application level

## Slide 18
- The Three Pillars of Observability
- Distributed Systems Observability by Cindy Sridharan
- Logs, Metrics, Traces

## Slide 19
- The Three Pillars of Observability
- Logs: Event records and system information
- Metrics: Quantifiable measurements over time
- Traces: Request flow through systems

## Slide 20
- Using Observability
- (Visual content not fully captured)

## Slide 21
- Observability on AWS
- Dashboard: ServiceGraph visual representation
- AWS X-Ray for tracing
- Traces collection and visualization

## Slide 22
- CloudWatch API PutMetricData
- MetricData with: MetricName, Dimensions, Timestamp, Value, Namespace
- Example: 'My Business Metric' with Location='Paris' dimension
- Custom metric recording

## Slide 23
- Add Correlation IDs to Logs
- CloudWatch Logs + Insights
- Trace requests across services with correlation IDs

## Slide 24
- End-to-End Tracing
- AWS X-Ray Traces
- Full request tracing through services

## Slide 25
- AWS X-Ray Key Concepts
- Segments: Top-level trace units
- Subsegments: Component-level details

## Slide 26
- End-to-End Tracing
- AWS X-Ray Service Map
- Visualize service dependencies and communication

## Slide 27
- Understand Performance
- Systems Performance by Brendan Gregg
- Performance analysis and monitoring

## Slide 28
- Understand Performance and Latency
- Event latency measurements from CPU cycles (0.3ns) to full system reboot (40s)
- Context: 1 CPU cycle = 1s, Level 1 cache access = 3s, Memory access = 6 minutes, Disk IO = 26 days
- Network latency: San Francisco to UK = 3 years, San Francisco to Australia = 19 years
- Critical timeouts: TCP retransmit = 105-317 years, System reboot = 3-32 millennia
- Source: Systems Performance by Brendan Gregg

## Slide 29
- Understand Performance, Latency, and Percentiles
- P90, P95, P99, P100 percentile measurement
- Distribution of response times
- Understand tail latencies

## Slide 30
- What is Needed for Observability
- Consistent communications management
- Complete visibility and protection
- Failure isolation
- Fine-grained deployment controls

## Slide 31
- Client-Side Traffic Management
- Traffic Shaping
- Service discovery
- Retries and Timeouts
- Circuit breakers
- Health checks
- Routing Controls
- Protocol support: Header-based, Cookie-based, Path-based, Host-based routing

## Slide 32
- Application Observability
- CloudWatch and X-Ray for observability
- Faster troubleshooting
- Consistent data across services
- Existing tools with more metrics/logs
- Distinguish service vs network issues

## Slide 31
- (Last slide visual reference)
