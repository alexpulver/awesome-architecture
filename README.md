# Awesome Architecture ![Awesome](https://awesome.re/badge.svg)

This document starts with a list of concepts and foundations, followed by [jobs-to-be-done](https://strategyn.com/jobs-to-be-done/).

## Concepts
* [Application Lifecycle Management (ALM)](https://aws.amazon.com/what-is/application-lifecycle-management/)
* [Architecturally significant requirements](https://en.wikipedia.org/wiki/Architecturally_significant_requirements) criteria: business value/risk, stakeholder concern, quality level, external dependencies, cross-cutting, first-of-a-kind, source of problems on past projects
* [Architectural decision records (ADRs)](https://docs.aws.amazon.com/prescriptive-guidance/latest/architectural-decision-records/appendix.html): Records that support team alignment, document strategic directions for a project or product, and reduce recurring and time-consuming decision-making efforts
* [Continuous Configuration](https://www.allthingsdistributed.com/2021/08/continuous-configuration-on-aws.html) values often fall into two groups: those that modify operational behavior of an application—such as throttling, limits, connection limits, or logging verbosity—and those that control FAC (Feature Access Control), including feature flags, A/B testing, and user allow/deny lists
* [Coupling](https://architectelevator.com/cloud/cloud-decoupling-cost/): Coupling describes the independent variability of connected systems, i.e., whether a change in System A has an effect on System B. If it does, A and B are coupled
* [Coupling facets](https://youtu.be/w9a7eI6BlVc?t=1487): 1/ Technology (Java vs. C++, Kubernetes, PostgreSQL) 2/ Location (IP addresses, DNS) 3/ Data Format (Binary, XML, JSON, protobuf, Avro) 4/ Data Type (int16, int32, string, UTF-8, null, empty) 5/ Semantic (Name, Middlename, ZIP) 6/ Temporal (sync, async) 7/ Interaction Style (messaging, RPC, query, GraphQL) 8/ Conversation (pagination, caching, retries)
* [Declarative provisioning not equal to Declarative language](https://www.youtube.com/watch?v=ttJAIQf7cTw&t=2077s)
* [Event-Driven Architecture](https://www.youtube.com/watch?v=STKCRSUsyP0&feature=share) patterns: 1/ Event Notification 2/ Event-carried State Transfer 3/ Event Sourcing 4/ Command and Query Responsibility Segregation
* [Feature Flags](https://launchdarkly.com/blog/what-are-feature-flags/)
* [GitOps](https://opengitops.dev/): 1/ Declarative 2/ Versioned and Immutable 3/ Pulled Automatically 4/ Continuously Reconciled
* [Platform](https://youtu.be/eMrmAn3bYiI?t=1524): a set of standardized elements that provide value but do not presuppose all problems
* [SaaS Architecture Fundamentals](https://docs.aws.amazon.com/whitepapers/latest/saas-architecture-fundamentals/saas-architecture-fundamentals.html)
* [Software Boundaries or "Fracture Planes"](https://blog.matthewskelton.net/about/): 1/ Business Domain Bounded Context 2/ Regulatory Compliance 3/ Change Cadence 4/ Team Location 5/ Risk 6/ Performance Isolation 7/ Technology 8/ User Personas
* [Software delivery performance four key metrics](https://www.thoughtworks.com/radar/techniques/four-key-metrics): 1/ Cycle Time (Change Lead Time) 2/ Deployment Frequency 3/ Change Failure Rate (CFR) 4/ Mean Time to Recovery (MTTR)

## Foundations
### Organizational culture, structure, and processes
* [7 tell-tale signs of fake DevOps](https://www.cio.com/article/419248/7-tell-tale-signs-of-fake-devops.html)
* [DevOps at Amazon: A Look at Our Tools and Processes](https://www.youtube.com/watch?v=esEFaY0FDKc)
* [DevOps Topologies](https://web.devopstopologies.com/index.html)
* [Fireside Chat: DevOps at Amazon with Ken Exner, GM of AWS Developer Tools - AWS Online Tech Talks](https://www.youtube.com/watch?v=FlZm3nFMIAM&feature=youtu.be)
* Leadership Session: Developer Tools on AWS ([video](https://www.youtube.com/watch?v=p9IybVJp5QM), [slides](https://d1.awsstatic.com/events/reinvent/2019/Leadership_Session_Developer_Tools_on_AWS_DOP210-L.pdf))
* [Pattern-based process for making design decisions](https://microservices.io/post/architecture/2023/03/13/better-decision-making-with-patterns.html)
* [Seven Shipping Principles](https://37signals.com/seven-shipping-principles)
* [The Away Team Model at Amazon](https://pedrodelgallego.github.io/blog/amazon/operating-model/away-team-model/)
* Two-pizza teams: Organizing for innovation ([video](https://www.youtube.com/watch?v=XavPl5t9dS8), [slides](https://d1.awsstatic.com/events/reinvent/2020/TwoPizza_Teams_Building_innovative_teams_that_scale_INO207.pdf))
* [Would you like architects with your architecture?](https://architectelevator.com/architecture/organizing-architecture/)

### Working backwards
* [Amazon’s Not So Secret Weapon - The magic of Working Backwards: a real-world case study](https://medium.com/nerd-for-tech/how-i-grew-an-engineering-productivity-tool-to-impact-thousands-of-engineers-at-amazon-and-how-28a990091207)
* [HEY Bubble Up: From kickoff to launch](https://updates.basecamp.com/post/hey-bubble-up)

### Product-market fit
* [Box’s Aaron Levie on navigating SaaS’ several stages of growth](https://www.mckinsey.com/industries/technology-media-and-telecommunications/our-insights/boxs-aaron-levie-on-navigating-saas-several-stages-of-growth)
* [Managing growth and value creation in SaaS: An interview with a software leader](https://www.mckinsey.com/industries/technology-media-and-telecommunications/our-insights/managing-growth-and-value-creation-in-saas)

### Profitable growth
* [A CEO’s tactical guide to driving profitable growth](https://www.bvp.com/atlas/a-ceo-s-tactical-guide-to-driving-profitable-growth)

### Business metrics
* [B2B SaaS benchmarks: What metrics do VCs look at for signs of product-market fit?](https://www.airtree.vc/open-source-vc/b2b-saas-benchmarks-what-metrics-do-vcs-looking-at-for-signs-of-product-market-fit)
* [Product metrics that matter the most: A flywheel framework for cloud business leaders](https://nextbigteng.substack.com/p/product-metrics-that-matter-the-most)
* [SaaS and the Rule of 40: Keys to the critical value creation metric](https://www.mckinsey.com/industries/technology-media-and-telecommunications/our-insights/saas-and-the-rule-of-40-keys-to-the-critical-value-creation-metric)

### Business and technology alignment
* [Modernizing Technology and Mindset with ‘Enabling Teams’](https://medium.com/cyberark-engineering/modernizing-technology-and-mindset-with-enabling-teams-52e8dc45a261)
* [SaaS Cost Attribution: How to Align Technology with Business](https://aws.amazon.com/blogs/apn/saas-cost-attribution-how-to-align-technology-with-business/)
* [Strategies for investment in Tech Debt vs Product Debt when building new software products](https://medium.com/stackpulse/strategies-for-investment-in-tech-debt-vs-product-debt-when-building-new-software-428de5680070)
* [Why I Never Want to Build Another MVP](https://www.digit.fyi/comment-why-i-never-want-to-build-another-mvp/)

### Compliance
* [Compliance in a DevOps Culture](https://martinfowler.com/articles/devops-compliance.html)

### Technology landscape
* [ThoughtWorks Technology Radar](https://www.thoughtworks.com/radar)

### Frameworks
* [Application Design Framework (ADF)](https://github.com/alexpulver/adf)
* [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html) pillars: 1/ Operational excellence 2/ Security 3/ Reliability 4/ Performance efficiency 5/ Cost optimization
* [Operational Readiness Reviews (ORR)](https://docs.aws.amazon.com/wellarchitected/latest/operational-readiness-reviews/wa-operational-readiness-reviews.html)
* [SaaS Lens for the AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/saas-lens/saas-lens.html)

### Cross-cutting concerns
* [Aligning SaaS and Service Planes Definitions](https://softwhat.com/aligning-saas-and-service-planes-definitions/)
* [Architect multitenant solutions on Azure](https://docs.microsoft.com/en-us/azure/architecture/guide/multitenant/overview)
* Are you integrating or building distributed applications? ([video](https://youtu.be/Zrj7RD7G24Q), [slides](https://d1.awsstatic.com/events/Summits/reinvent2022/API308_Are-you-integrating-or-building-distributed-applications.pdf))
* [Building ClickHouse Cloud From Scratch in a Year](https://clickhouse.com/blog/building-clickhouse-cloud-from-scratch-in-a-year)
* [Failing successfully: The AWS approach to resilient design](https://d1.awsstatic.com/events/reinvent/2019/REPEAT_2_Failing_successfully_The_AWS_approach_to_resilient_design_ARC303-R2.pdf)
* [How we ended up with microservices](https://philcalcado.com/2015/09/08/how_we_ended_up_with_microservices.html)
* [Kubernetes as a platform vs. Kubernetes as an API](https://aws.amazon.com/blogs/containers/kubernetes-as-a-platform-vs-kubernetes-as-an-api-2/)
* [Minimizing Design Time Coupling in a Microservice Architecture](https://www.infoq.com/presentations/microservices-design-time-coupling/)
* Modern cloud applications: Do they lock you in? ([video](https://www.youtube.com/watch?v=Ud9h1hJgoKk&list=WL&index=1), [slides](https://d1.awsstatic.com/events/Summits/reinvent2022/ARC207_Modern-cloud-applications-Do-they-lock-you-in.pdf))
* [On Designing and Deploying Internet-Scale Services](https://mvdirona.com/jrh/talksAndPapers/JamesRH_Lisa.pdf)
* [Takeaways of building a business-critical low-latency microservice at scale](https://medium.com/teads-engineering/takeaways-of-building-a-business-critical-low-latency-microservice-at-scale-97e79ce3ec78)
* [You Want Modules, Not Microservices](http://blogs.newardassociates.com/blog/2023/you-want-modules-not-microservices.html)

### Landing zone
* [Establishing your best practice AWS environment](https://aws.amazon.com/organizations/getting-started/best-practices/)

### Platform
* [Building Infrastructure Platforms](https://martinfowler.com/articles/building-infrastructure-platform.html)
* [Integrating Backstage at DAZN](https://medium.com/dazn-tech/integrating-backstage-at-dazn-b8ef5268b347)
* [The Magic of Platforms • Gregor Hohpe • PlatformCon 2022](https://www.youtube.com/watch?v=WaL3ZbLgMuI)

## Jobs-to-be-done
### Access control and isolation
* [A Rails Multi-Tenant Strategy That's ~30 Lines and "Just Works"](https://dev.to/kolide/a-rails-multi-tenant-strategy-thats-30-lines-and-just-works-58cd)
* [Building Multi-Tenant Solutions with Amazon OpenSearch Service](https://www.youtube.com/watch?v=FswkQ8YfZyc)
* [How to implement SaaS tenant isolation with ABAC and AWS IAM](https://aws.amazon.com/blogs/security/how-to-implement-saas-tenant-isolation-with-abac-and-aws-iam/)
* [Implementing SaaS Tenant Isolation Using Amazon SageMaker Endpoints and IAM](https://aws.amazon.com/blogs/apn/implementing-saas-tenant-isolation-using-amazon-sagemaker-endpoints-and-iam/)
* [Secure data movement across Amazon S3 and Amazon Redshift using role chaining and ASSUMEROLE](https://aws.amazon.com/blogs/big-data/secure-data-movement-across-amazon-s3-and-amazon-redshift-using-role-chaining-and-assumerole/)
* [Securing Multi-Tenant Kubernetes Clusters at Scale](https://www.youtube.com/watch?v=WS2Qgx0qgCM)
* Solving large-scale data access challenges with Amazon S3 ([video](https://www.youtube.com/watch?v=BOz2_hgoob4), [slides](https://d1.awsstatic.com/events/Summits/reinvent2022/STG328_Solving-large-scale-data-access-challenges-with-Amazon-S3.pdf))

### API
* [Architecture patterns for consuming private APIs cross-account](https://aws.amazon.com/blogs/compute/architecture-patterns-for-consuming-private-apis-cross-account/)
* [Best practices for working with the Apache Velocity Template Language in Amazon API Gateway](https://aws.amazon.com/blogs/compute/best-practices-for-working-with-the-apache-velocity-template-language-in-amazon-api-gateway/)
* How Netflix Scales its API with GraphQL Federation ([Part 1](https://netflixtechblog.com/how-netflix-scales-its-api-with-graphql-federation-part-1-ae3557c187e2), [Part 2](https://netflixtechblog.com/how-netflix-scales-its-api-with-graphql-federation-part-2-bbe71aaec44a))

### Authentication and authorization
* [Edge Authentication and Token-Agnostic Identity Propagation](https://netflixtechblog.com/edge-authentication-and-token-agnostic-identity-propagation-514e47e0b602)
* [Enhancing Amazon DynamoDB single-table design with AWS AppSync access and security features](https://aws.amazon.com/blogs/mobile/enhancing-dynamodb-single-table-design-with-appsync-access-and-security-features/)
* [Entitlements: Architecting Authorization](https://www.styra.com/blog/entitlements-architecting-authorization/)
* [How to Persist JWT Tokens for Your SaaS Application](https://frontegg.com/blog/how-to-persist-jwt-tokens-for-your-saas-application)
* [Amazon DocumentDB (with MongoDB compatibility) user-defined roles for access control](https://aws.amazon.com/blogs/database/introducing-amazon-documentdb-with-mongodb-compatibility-user-defined-roles-for-access-control/)
* [JSON Web Token (JWT) Profile for OAuth 2.0 Access Tokens](https://datatracker.ietf.org/doc/html/rfc9068)
* [On The Nature of OAuth2’s Scopes](https://auth0.com/blog/on-the-nature-of-oauth2-scopes/)

### Configuration
* [Continuous Configuration at the Speed of Sound](https://www.allthingsdistributed.com/2021/08/continuous-configuration-on-aws.html)

### Deployment
* Amazon CI/CD Practices for Software Development Teams ([video](https://youtu.be/3HKbXz0RwSg), [slides](https://www.slideshare.net/AmazonWebServices/amazon-cicd-practices-for-software-development-teams))
* Amazon's approach to high-availability deployment ([video](https://www.youtube.com/watch?v=bCgD2bX1LI4), [slides](https://d1.awsstatic.com/events/reinvent/2019/REPEAT_1_Amazon's_approach_to_high-availability_deployment_DOP404-R1.pdf.pdf))
* [Automate rollbacks for Amazon ECS rolling deployments with CloudWatch alarms](https://aws.amazon.com/blogs/containers/automate-rollbacks-for-amazon-ecs-rolling-deployments-with-cloudwatch-alarms/)
* Automating safe, hands-off deployments ([video](https://youtu.be/ngnMj1zbMPY), [article](https://aws.amazon.com/builders-library/automating-safe-hands-off-deployments/), [podcast](https://www.infoq.com/podcasts/aws-deployments/))
* Best practices for CI/CD using AWS Fargate and Amazon ECS ([video](https://www.youtube.com/watch?v=7FVK0i9edyg), [slides](https://d1.awsstatic.com/events/reinvent/2019/REPEAT_2_Best_practices_for_CICD_using_AWS_Fargate_and_Amazon_ECS_CON333-R2.pdf))
* [Best practices for CI/CD with AWS Lambda and Amazon API Gateway](https://www.slideshare.net/AmazonWebServices/best-practices-for-cicd-with-aws-lambda-and-amazon-api-gateway-srv355r1-aws-reinvent-2018)
* [Building a Continuous Integration Workflow with Step Functions and AWS CodeBuild](https://aws.amazon.com/blogs/aws/new-building-a-continuous-integration-workflow-with-step-functions-and-aws-codebuild/)
* [Building a cross-account continuous delivery pipeline for database migrations](https://aws.amazon.com/blogs/database/building-a-cross-account-continuous-delivery-pipeline-for-database-migrations/)
* [Building and testing polyglot applications using AWS CodeBuild](https://aws.amazon.com/blogs/devops/building-and-testing-polyglot-applications-using-aws-codebuild/)
* [CDK Pipelines: Continuous delivery for AWS CDK applications](https://aws.amazon.com/blogs/developer/cdk-pipelines-continuous-delivery-for-aws-cdk-applications/)
* [Continuous Delivery of Amazon EKS Clusters Using AWS CDK and CDK Pipelines](https://aws.amazon.com/blogs/containers/continuous-delivery-of-amazon-eks-clusters-using-aws-cdk-and-cdk-pipelines/)
* [Deploying GitOps with Weave Flux and Amazon EKS](https://aws.amazon.com/blogs/compute/deploying-gitops-with-weave-flux-and-amazon-eks/)
* [Ensuring rollback safety during deployments](https://aws.amazon.com/builders-library/ensuring-rollback-safety-during-deployments/)
* [My CI/CD pipeline is my release captain](https://aws.amazon.com/builders-library/cicd-pipeline/)
* [Overview of Deployment Options on AWS](https://docs.aws.amazon.com/whitepapers/latest/overview-deployment-options/welcome.html)
* [Parallel and dynamic SaaS deployments with AWS CDK Pipelines](https://aws.amazon.com/blogs/devops/parallel-and-dynamic-saas-deployments-with-cdk-pipelines/)
* [Practicing Continuous Integration and Continuous Delivery on AWS](https://docs.aws.amazon.com/whitepapers/latest/practicing-continuous-integration-continuous-delivery/welcome.html)
* Releasing Mission-Critical Software at Amazon ([video](https://www.youtube.com/watch?v=I61KKO1rAQ8&feature=youtu.be), [slides](https://www.slideshare.net/AmazonWebServices/releasing-missioncritical-software-at-amazon-dev209r1-aws-reinvent-2018))
* [Rolling Forward and other Deployment Myths](https://dzone.com/articles/rolling-forward-and-other)
* [Seamless branch deploys with Kubernetes](https://m.signalvnoise.com/seamless-branch-deploys-with-kubernetes/)
* [Serverless CI/CD for the Enterprise on AWS](https://aws.amazon.com/quickstart/architecture/serverless-cicd-for-enterprise/)
* [Using AWS Step Functions State Machines to Handle Workflow-Driven AWS CodePipeline Actions](https://aws.amazon.com/blogs/devops/using-aws-step-functions-state-machines-to-handle-workflow-driven-aws-codepipeline-actions/)
* [Validating AWS CodeCommit Pull Requests with AWS CodeBuild and AWS Lambda](https://aws.amazon.com/blogs/devops/validating-aws-codecommit-pull-requests-with-aws-codebuild-and-aws-lambda/)

### Development
* [Applying  the Twelve-Factor App Methodology to Serverless Applications](https://aws.amazon.com/blogs/compute/applying-the-twelve-factor-app-methodology-to-serverless-applications/)
* [Branch by Abstraction](https://www.branchbyabstraction.com/) for major changes that take time
* Building production-ready prototypes ([video](https://www.youtube.com/watch?v=-_Zl9u9i1KI), [slides](https://d1.awsstatic.com/events/reinvent/2021/Building_productionready_prototypes_ARC330.pdf))
* [Deploy AWS Organizations resources by using CloudFormation](https://aws.amazon.com/blogs/security/deploy-aws-organizations-resources-by-using-cloudformation/)
* [Include CloudFormation templates in the CDK](https://docs.aws.amazon.com/cdk/api/latest/docs/cloudformation-include-readme.html)
* [Managing resources using AWS CloudFormation Resource Types](https://aws.amazon.com/blogs/mt/managing-resources-using-aws-cloudformation-resource-types/)
* [Running bash commands in AWS CloudFormation templates](https://aws.amazon.com/blogs/mt/running-bash-commands-in-aws-cloudformation-templates/)
* [The Twelve-Factor App](https://12factor.net/)
* [This is why you should keep stateful and stateless resources together](https://theburningmonk.com/2023/01/this-is-why-you-should-keep-stateful-and-stateless-resources-together/)
* [Trunk-Based Development](https://trunkbaseddevelopment.com/)

### Encryption
* [Control Access to Your Data with Slack Enterprise Key Management and AWS KMS](https://aws.amazon.com/blogs/apn/control-access-to-your-data-with-slack-enterprise-key-management-and-aws-kms/)

### Extensibility
* Supporting extensibility in SaaS environments ([video](https://www.youtube.com/watch?v=uzRrEWzqD0Y), [slides](https://d1.awsstatic.com/events/Summits/reinvent2022/SAS302_Supporting-extensibility-in-SaaS-environments.pdf))

### Frontend
* [How Capital One Builds Micro-Frontends At Scale](https://www.capitalone.com/tech/software-engineering/loosely-coupled-micro-frontends-with-nodejs/)

### Hybrid architecture
* [Build a Hybrid Architecture for Local Compliance and Global Scalability](https://aws.amazon.com/blogs/startups/build-a-hybrid-architecture-for-local-compliance-and-global-scalability/)

### Integration patterns
* [Architecture patterns for consuming private APIs cross-account](https://aws.amazon.com/blogs/compute/architecture-patterns-for-consuming-private-apis-cross-account/)
* [Starbucks Does Not Use Two-Phase Commit](https://www.enterpriseintegrationpatterns.com/ramblings/18_starbucks.html)

### Internet of Things (IoT)
* [How BISSELL migrated a million vacuum devices to a scalable IoT Platform on AWS](https://aws.amazon.com/blogs/iot/how-bissell-migrated-a-million-vacuum-devices-to-a-scalable-iot-platform-on-aws/)

### Machine learning
* [How to scale machine learning inference for multi-tenant SaaS use cases](https://aws.amazon.com/blogs/machine-learning/how-to-scale-machine-learning-inference-for-multi-tenant-saas-use-cases/)

### Migrations
* [Amazon CISO Jeff Carter - Securing Amazon.com and Migrating Databases to the Cloud](https://www.youtube.com/watch?v=5xuCQJzv7eM)

### Multi-region
* [Implement Multi-Region Serverless (and Functionless) WebSocket Pub/Sub APIs with AWS AppSync and Amazon EventBridge](https://aws.amazon.com/blogs/mobile/multi-region-websocket-api/)
* [Ten tips for multi-tenant, multi-Region object replication in Amazon S3](https://aws.amazon.com/blogs/storage/ten-tips-for-multi-tenant-multi-region-object-replication-in-amazon-s3/)

### Networking
* [Addressing latency and data transfer costs on EKS using Istio](https://aws.amazon.com/blogs/containers/addressing-latency-and-data-transfer-costs-on-eks-using-istio/)
* [Building the Next Evolution of Cloud Networks at Slack – A Retrospective](https://slack.engineering/building-the-next-evolution-of-cloud-networks-at-slack-a-retrospective/)
* [Designing hyperscale Amazon VPC networks](https://aws.amazon.com/blogs/networking-and-content-delivery/designing-hyperscale-amazon-vpc-networks/)
* [How FactSet handles networking for 1000+ AWS accounts](https://aws.amazon.com/blogs/networking-and-content-delivery/how-factset-handles-networking-for-1000-aws-accounts/)
* [VPC sharing: key considerations and best practices](https://aws.amazon.com/blogs/networking-and-content-delivery/vpc-sharing-key-considerations-and-best-practices/)

### Observability
* [Amazon CloudWatch Now Includes Contributor Insights - in Preview](https://aws.amazon.com/about-aws/whats-new/2019/11/amazon-cloudwatch-now-includes-contributor-insights-preview/)
* [AWS X-Ray](https://docs.aws.amazon.com/xray/latest/devguide/aws-xray.html) (see also [Integrating  AWS X-Ray with Other AWS Services](https://docs.aws.amazon.com/xray/latest/devguide/xray-services.html))
* [AWS X-Ray Now Supports Amazon API Gateway and New Sampling Rules API](https://aws.amazon.com/blogs/aws/apigateway-xray/)
* [Container monitoring for Amazon ECS, EKS, and Kubernetes is now available in Amazon CloudWatch](https://aws.amazon.com/about-aws/whats-new/2019/08/container-monitoring-for-amazon-ecs-eks-and-kubernetes-is-now-available-in-amazon-cloudwatch/)
* [Debugging with Amazon CloudWatch Synthetics and AWS X-Ray](https://aws.amazon.com/blogs/devops/debugging-with-amazon-cloudwatch-synthetics-and-aws-x-ray/)
* [One observability workshop](https://catalog.workshops.aws/observability/)
* [Using Prometheus Metrics in Amazon CloudWatch](https://aws.amazon.com/blogs/containers/using-prometheus-metrics-in-amazon-cloudwatch/)
* [Visualize and Monitor Highly Distributed Applications with Amazon CloudWatch ServiceLens](https://aws.amazon.com/blogs/aws/visualize-and-monitor-highly-distributed-applications-with-amazon-cloudwatch-servicelens/)

### Operations
* [Accounting for the Basecamp 3 outage on June 27, 2022](https://updates.basecamp.com/post/accounting-for-the-basecamp-3-outage-on-june-27-2022)
* Amazon’s approach to failing successfully ([video](https://www.youtube.com/watch?v=yQiRli2ZPxU), [slides](https://d1.awsstatic.com/events/reinvent/2019/REPEAT_1_Amazon%E2%80%99s_approach_to_failing_successfully_DOP208-R1.pdf))
* [Building dashboards for operational visibility](https://aws.amazon.com/builders-library/building-dashboards-for-operational-visibility/)
* [Changing the Wheels on a Moving Bus — Spotify’s Event Delivery Migration](https://engineering.atspotify.com/2021/10/20/changing-the-wheels-on-a-moving-bus-spotify-event-delivery-migration/)
* [Kubernetes cluster upgrade: the blue-green deployment strategy](https://aws.amazon.com/blogs/containers/kubernetes-cluster-upgrade-the-blue-green-deployment-strategy/)
* [Resolve IT Incidents Faster with Incident Manager, a New Capability of AWS Systems Manager](https://aws.amazon.com/blogs/aws/resolve-it-incidents-faster-with-incident-manager-a-new-capability-of-aws-systems-manager/)
* Towards Operational Excellence blog post series:
    * [Part 1 — Customers, Culture, and why you should care](https://medium.com/@adhorn/towards-operational-excellence-35ba6298b12f)
    * [Part 2 —On the importance of tools](https://medium.com/@adhorn/towards-operational-excellence-c9fe298e27e7)
    * [Part 3 — Mechanisms](https://medium.com/@adhorn/towards-operational-excellence-part-3-8b727f06a4b6)
* [ZEN and the art of Reliability](https://zendesk.engineering/zen-and-the-art-of-reliability-f42fa7e64849)

### Sharding and partitioning data
* Decomposing the GitLab backend database:
   * [Part 1: Designing and planning](https://about.gitlab.com/blog/2022/08/04/path-to-decomposing-gitlab-database-part1/)
   * [Part 2: Final migration and results](https://about.gitlab.com/blog/2022/08/04/path-to-decomposing-gitlab-database-part2/)
   * [Part 3: Challenges and surprises](https://about.gitlab.com/blog/2022/08/04/path-to-decomposing-gitlab-database-part3/)
* [E-Commerce at Scale: Inside Shopify's Tech Stack - Stackshare.io](https://shopify.engineering/e-commerce-at-scale-inside-shopifys-tech-stack)
* [Herding elephants: Lessons learned from sharding Postgres at Notion](https://www.notion.so/blog/sharding-postgres-at-notion)
* [Improve performance and manageability of large PostgreSQL tables by migrating to partitioned tables on Amazon Aurora and Amazon RDS](https://aws.amazon.com/blogs/database/improve-performance-and-manageability-of-large-postgresql-tables-by-migrating-to-partitioned-tables-on-amazon-aurora-and-amazon-rds/)
* [Partitioning GitHub’s relational databases to handle scale](https://github.blog/2021-09-27-partitioning-githubs-relational-databases-scale/)
* [Scaling Datastores at Slack with Vitess](https://slack.engineering/scaling-datastores-at-slack-with-vitess/)
* Scaling Etsy Payments with Vitess:
   * [Part 1 – The Data Model](https://www.etsy.com/il-en/codeascraft/scaling-etsy-payments-with-vitess-part-1--the-data-model)
   * [Part 2 – The “Seamless” Migration](https://www.etsy.com/il-en/codeascraft/scaling-etsy-payments-with-vitess-part-2--the-seamless-migration)
   * [Part 3 – Reducing Cutover Risk](https://www.etsy.com/il-en/codeascraft/scaling-etsy-payments-with-vitess-part-3--reducing-cutover-risk)

### Tenant costs
* [Calculating Tenant Costs in SaaS Environments](https://aws.amazon.com/blogs/apn/calculating-tenant-costs-in-saas-environments/)
* [Calculating SaaS Cost Per Tenant: A PoC Implementation in an AWS Kubernetes Environment](https://aws.amazon.com/blogs/apn/calculating-saas-cost-per-tenant-a-poc-implementation-in-an-aws-kubernetes-environment/)

### Tenant management
* [How CyberArk Built a Tenant Management Service for its SaaS Offering](https://aws.amazon.com/blogs/apn/how-cyberark-built-tenant-management-service-for-its-saas-offering/)

### Testing
* [Running end-to-end Cypress tests for your fullstack CI/CD deployment with Amplify Console](https://aws.amazon.com/blogs/mobile/running-end-to-end-cypress-tests-for-your-fullstack-ci-cd-deployment-with-amplify-console/)
* [Test Reports with AWS CodeBuild](https://aws.amazon.com/blogs/devops/test-reports-with-aws-codebuild/)
* [The Practical Test Pyramid](https://martinfowler.com/articles/practical-test-pyramid.html)
