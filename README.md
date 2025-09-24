# Awesome Architecture ![Awesome](https://awesome.re/badge.svg)

This document starts with a list of concepts, mindset and foundations, followed by [jobs-to-be-done](https://strategyn.com/jobs-to-be-done/).

## Concepts
* [Architecturally significant requirements](https://en.wikipedia.org/wiki/Architecturally_significant_requirements) criteria: business value/risk, stakeholder concern, quality level, external dependencies, cross-cutting, first-of-a-kind, source of problems on past projects.
* [Architectural decision records (ADRs)](https://docs.aws.amazon.com/prescriptive-guidance/latest/architectural-decision-records/appendix.html): Records that support team alignment, document strategic directions for a project or product, and reduce recurring and time-consuming decision-making efforts.
* [Continuous Configuration](https://www.allthingsdistributed.com/2021/08/continuous-configuration-on-aws.html): 1/ Operational behavior of an application (e.g., throttling, limits, connection limits, logging verbosity) 2/ Feature access control (e.g., feature flags, A/B testing, user allow/deny lists).
* [Coupling](https://architectelevator.com/cloud/cloud-decoupling-cost/): Coupling describes the independent variability of connected systems, i.e., whether a change in System A has an effect on System B. If it does, A and B are coupled.
* Coupling facets ([video](https://youtu.be/w9a7eI6BlVc?t=1487), [post](https://www.enterpriseintegrationpatterns.com/ramblings/coupling_facets.html)): 1/ Technology (Java vs. C++, Kubernetes, PostgreSQL) 2/ Location (IP addresses, DNS) 3/ Data Format (Binary, XML, JSON, protobuf, Avro) 4/ Data Type (int16, int32, string, UTF-8, null, empty) 5/ Semantic (Name, Middlename, ZIP) 6/ Temporal (sync, async) 7/ Interaction Style (messaging, RPC, query, GraphQL) 8/ Conversation (pagination, caching, retries).
* Declarative Provisioning != Declarative Language ([video](https://www.youtube.com/watch?v=ttJAIQf7cTw&t=2077s), [slides](https://d1.awsstatic.com/events/reinvent/2021/Building_modern_cloud_applications_Think_integration_API308%20.pdf#page=42))
* [Easy Approach to Requirements Syntax (EARS)](https://alistairmavin.com/ears/) patterns: "While [optional pre-condition], when [optional trigger], the [system name] shall [system response]" (e.g., "While the user is signed-in, when the user asks to change the password, the application shall re-authenticate the user").
* [Event-Driven Architecture](https://martinfowler.com/articles/201701-event-driven.html) patterns: 1/ Event Notification 2/ Event-carried State Transfer 3/ Event Sourcing 4/ Command and Query Responsibility Segregation.
* [Feature Flags](https://launchdarkly.com/blog/what-are-feature-flags/)
* [GitOps](https://opengitops.dev/): 1/ Declarative 2/ Versioned and Immutable 3/ Pulled Automatically 4/ Continuously Reconciled.
* [Message](https://www.enterpriseintegrationpatterns.com/patterns/messaging/Message.html) patterns: 1/ Event 2/ Document 3/ Command. 
* [Platform](https://youtu.be/eMrmAn3bYiI?t=1524): a set of standardized elements that provide value but do not presuppose all problems.
* [SaaS Architecture Fundamentals](https://docs.aws.amazon.com/whitepapers/latest/saas-architecture-fundamentals/saas-architecture-fundamentals.html)
* [Software Boundaries or "Fracture Planes"](https://blog.matthewskelton.net/about/): 1/ Business Domain Bounded Context 2/ Regulatory Compliance 3/ Change Cadence 4/ Team Location 5/ Risk 6/ Performance Isolation 7/ Technology 8/ User Personas.
* [Software delivery performance four key metrics](https://www.thoughtworks.com/radar/techniques/four-key-metrics): 1/ Cycle Time (Change Lead Time) 2/ Deployment Frequency 3/ Change Failure Rate (CFR) 4/ Mean Time to Recovery (MTTR).
* [Stories](https://martinfowler.com/bliki/UserStory.html): 1/ User story – "As a [type of user] I [want this thing] so that [I can accomplish this goal]" (e.g., "As a site visitor, I want to see new content when I come to the site, so I come back more often") 2/ Job story – "When [situation], I want to [motivation], so I can [expected outcome]" (e.g., "When it’s dinner time tonight, I want to have pizza so I can easily feed my friends" 3/ Feature-driven development – "[Action] the [result] [by/for/of/to] a(n) [object]" (e.g., "Generate a unique identifier for a transaction").
* [Frugal Architecture](https://www.thefrugalarchitect.com/): 1/ Make Cost a Non-functional Requirement 2/ Systems that Last Align Cost to Business 3/ Architecting is a Series of Trade-offs 4/ Unobserved Systems Lead to Unknown Costs 5/ Cost Aware Architectures Implement Cost Controls 6/ Cost Optimization is Incremental 7/ Unchallenged Success Leads to Assumptions.

## Mindset
* Abstraction in the cloud: a service with higher-level vocabulary that shields from the complexity, security and operations of the underlying implementation ([Alex Pulver](https://www.linkedin.com/in/alexpulver/))
* A system is only evolvable if you can easily understand it and you can safely change it. ([Rebecca Parsons](https://www.infoq.com/podcasts/evolutionary-architecture-evolution/))
* Cloud automation tools like AWS CDK, CDK for Terraform and Pulumi allow you to implement application’s resources configuration and business logic using the same programming language. ([Alex Pulver](https://www.linkedin.com/in/alexpulver/))
* Build thoughtfully, and fail fast. ([Nadiya Amlani](https://www.linkedin.com/pulse/7-years-amazon-lesson-learned-nadiya-amlani-nqrcc/))
* Don’t look for a great Idea, find a good Problem to solve. (Someone)
* Feature branching implies a lower bound to the size of a change-set - you can't be smaller than a cohesive feature. ([Martin Fowler](https://martinfowler.com/articles/branching-patterns.html))
* Increasing the frequency of integration is an important reason to reduce the size of features. ([Martin Fowler](https://martinfowler.com/articles/branching-patterns.html))
* Requirements are the things that you should discover before starting to build your product. Discovering the requirements during construction, or worse, when you client starts using your product, is so expensive and so inefficient, that we will assume that no right-thinking person would do it, and will not mention it again. ([Suzanne and James Robertson](https://martinfowler.com/bliki/ObservedRequirement.html))
* To achieve modularity we need to constantly watch our system as it grows and tend it in a more modular direction. Refactoring is the key to achieving this, and refactoring requires high-frequency integration. Modularity and rapid integration thus support each other in a healthy codebase. ([Martin Fowler](https://martinfowler.com/articles/branching-patterns.html))
* You won’t be agile by focusing on agile frameworks. Agility requires changing everything we do, beginning with engineering our systems for lower delivery friction. ([Bryan Finster](https://www.infoq.com/articles/replace-process-dogma-engineering/))

## Foundations

### Business and technology alignment
* [Architecture Independent Value Streams](https://www.youtube.com/watch?v=LdhFf_I-pRA)
* [Domain-Driven Cloud: Aligning Your Cloud Architecture to Your Business Model](https://www.infoq.com/articles/domain-driven-cloud/)
* [Modernizing Technology and Mindset with ‘Enabling Teams’](https://medium.com/cyberark-engineering/modernizing-technology-and-mindset-with-enabling-teams-52e8dc45a261)
* [SaaS Cost Attribution: How to Align Technology with Business](https://aws.amazon.com/blogs/apn/saas-cost-attribution-how-to-align-technology-with-business/)
* [Start Your Architecture Modernization with Domain-Driven Discovery](https://www.infoq.com/articles/architecture-modernization-domain-driven-discovery/)
* [Strategies for investment in Tech Debt vs Product Debt when building new software products](https://medium.com/stackpulse/strategies-for-investment-in-tech-debt-vs-product-debt-when-building-new-software-428de5680070)
* [The Builder’s Guide to Better Mousetraps](https://brooker.co.za/blog/2024/03/04/mousetrap.html)
* [Using domain analysis to model microservices](https://learn.microsoft.com/en-us/azure/architecture/microservices/model/domain-analysis)
* [Why I Never Want to Build Another MVP](https://www.digit.fyi/comment-why-i-never-want-to-build-another-mvp/)

### Business metrics
* [B2B SaaS benchmarks: What metrics do VCs look at for signs of product-market fit?](https://www.airtree.vc/open-source-vc/b2b-saas-benchmarks-what-metrics-do-vcs-looking-at-for-signs-of-product-market-fit)
* [Product metrics that matter the most: A flywheel framework for cloud business leaders](https://nextbigteng.substack.com/p/product-metrics-that-matter-the-most)
* [SaaS and the Rule of 40: Keys to the critical value creation metric](https://www.mckinsey.com/industries/technology-media-and-telecommunications/our-insights/saas-and-the-rule-of-40-keys-to-the-critical-value-creation-metric)

### Compliance
* [Compliance in a DevOps Culture](https://martinfowler.com/articles/devops-compliance.html)
* [Importance and Impact of Compliance for SaaS Solutions on AWS](https://aws.amazon.com/blogs/apn/importance-and-impact-of-compliance-for-saas-solutions-on-aws/)

### Cross-cutting concerns
* [Aligning SaaS and Service Planes Definitions](https://softwhat.com/aligning-saas-and-service-planes-definitions/)
* [Architect multitenant solutions on Azure](https://docs.microsoft.com/en-us/azure/architecture/guide/multitenant/overview)
* Are you integrating or building distributed applications? ([video](https://youtu.be/Zrj7RD7G24Q), [slides](https://d1.awsstatic.com/events/Summits/reinvent2022/API308_Are-you-integrating-or-building-distributed-applications.pdf))
* [AWS Decision Guides](https://aws.amazon.com/getting-started/decision-guides/)
* [Building ClickHouse Cloud From Scratch in a Year](https://clickhouse.com/blog/building-clickhouse-cloud-from-scratch-in-a-year)
* [Cloud Automation à la DDD: From stringly typed to affordances](https://architectelevator.com/cloud/ddd-technical-domains/)
* [Cloud design patterns, architectures, and implementations](https://docs.aws.amazon.com/prescriptive-guidance/latest/cloud-design-patterns/introduction.html)
* [Choreography vs Orchestration in the land of serverless](https://theburningmonk.com/2020/08/choreography-vs-orchestration-in-the-land-of-serverless/)
* [Failing successfully: The AWS approach to resilient design](https://d1.awsstatic.com/events/reinvent/2019/REPEAT_2_Failing_successfully_The_AWS_approach_to_resilient_design_ARC303-R2.pdf)
* [Good abstractions are obvious but difficult to find, even in the cloud](https://architectelevator.com/cloud/abstractions-difficult/)
* [How we ended up with microservices](https://philcalcado.com/2015/09/08/how_we_ended_up_with_microservices.html)
* [I’m sorry, but the way you adopt serverless is wrong](https://theburningmonk.com/2024/07/im-sorry-but-the-way-you-adopt-serverless-is-wrong/)
* [Introducing the Journey to SaaS Guide to Help You Build, Launch, and Operate SaaS Solutions on AWS](https://aws.amazon.com/blogs/apn/introducing-the-journey-to-saas-guide-to-help-you-build-launch-and-operate-saas-solutions-on-aws/)
* [Kubernetes as a platform vs. Kubernetes as an API](https://aws.amazon.com/blogs/containers/kubernetes-as-a-platform-vs-kubernetes-as-an-api-2/)
* [Minimizing Design Time Coupling in a Microservice Architecture](https://www.infoq.com/presentations/microservices-design-time-coupling/)
* Modern cloud applications: Do they lock you in? ([video](https://www.youtube.com/watch?v=Ud9h1hJgoKk&list=WL&index=1), [slides](https://d1.awsstatic.com/events/Summits/reinvent2022/ARC207_Modern-cloud-applications-Do-they-lock-you-in.pdf))
* [Monoliths are not dinosaurs](https://www.allthingsdistributed.com/2023/05/monoliths-are-not-dinosaurs.html)
* [On Designing and Deploying Internet-Scale Services](https://mvdirona.com/jrh/talksAndPapers/JamesRH_Lisa.pdf)
* SaaS architecture patterns: From concept to implementation ([video](https://www.youtube.com/watch?v=xlAXldBt7I0), [slides](https://d1.awsstatic.com/events/Summits/reinvent2022/SAS305-R_SaaS-architecture-patterns-From-concept-to-implementation_NO-NOTES.pdf))
* [Serverless or Kubernetes on AWS](https://aws.amazon.com/getting-started/decision-guides/serverless-or-kubernetes-on-aws-how-to-choose/)
* [Takeaways of building a business-critical low-latency microservice at scale](https://medium.com/teads-engineering/takeaways-of-building-a-business-critical-low-latency-microservice-at-scale-97e79ce3ec78)
* [The Serverless Illusion](https://architectelevator.com/cloud/serverless-illusion/)
* [You Want Modules, Not Microservices](http://blogs.newardassociates.com/blog/2023/you-want-modules-not-microservices.html)
* [What's so bad about sidecars, anyway?](https://www.cerbos.dev/blog/whats-so-bad-about-sidecars-anyway)

### Frameworks
* [Application Design Framework (ADF)](https://applicationdesignframework.com)
* [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html) pillars: 1/ Operational excellence 2/ Security 3/ Reliability 4/ Performance efficiency 5/ Cost optimization
* [Operational Readiness Reviews (ORR)](https://docs.aws.amazon.com/wellarchitected/latest/operational-readiness-reviews/wa-operational-readiness-reviews.html)
* [SaaS Lens for the AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/saas-lens/saas-lens.html)

### Landing zone
* [Establishing your best practice AWS environment](https://aws.amazon.com/organizations/getting-started/best-practices/)

### Organizational culture, structure, and processes
* [7 tell-tale signs of fake DevOps](https://www.cio.com/article/419248/7-tell-tale-signs-of-fake-devops.html)
* [Agile Rehab: Replacing Process Dogma with Engineering to Achieve True Agility](https://www.infoq.com/articles/replace-process-dogma-engineering/)
* [DevOps at Amazon: A Look at Our Tools and Processes](https://www.youtube.com/watch?v=esEFaY0FDKc)
* [DevOps Topologies](https://web.devopstopologies.com/index.html)
* [Fireside Chat: DevOps at Amazon with Ken Exner, GM of AWS Developer Tools - AWS Online Tech Talks](https://www.youtube.com/watch?v=FlZm3nFMIAM&feature=youtu.be)
* Leadership Session: Developer Tools on AWS ([video](https://www.youtube.com/watch?v=p9IybVJp5QM), [slides](https://d1.awsstatic.com/events/reinvent/2019/Leadership_Session_Developer_Tools_on_AWS_DOP210-L.pdf))
* [Linking Modular Architecture to Development Teams](https://martinfowler.com/articles/linking-modular-arch.html)
* [Pattern-based process for making design decisions](https://microservices.io/post/architecture/2023/03/13/better-decision-making-with-patterns.html)
* [Seven Shipping Principles](https://37signals.com/seven-shipping-principles)
* [Software Architecture: the Hard Parts](https://www.infoq.com/podcasts/software-architecture-hard-parts/)
* [Team Interaction Modeling with Team Topologies](https://teamtopologies.com/key-concepts-content/team-interaction-modeling-with-team-topologies)
* [The Away Team Model at Amazon](https://pedrodelgallego.github.io/blog/amazon/operating-model/away-team-model/)
* The problems with MVPs in legacy replacement ([Part 1](https://www.thoughtworks.com/insights/blog/part-1-problems-mvps-legacy-replacement), [Part 2](https://www.thoughtworks.com/insights/blog/part-2-problems-mvps-legacy-replacement))
* Two-pizza teams: Organizing for innovation ([video](https://www.youtube.com/watch?v=XavPl5t9dS8), [slides](https://d1.awsstatic.com/events/reinvent/2020/TwoPizza_Teams_Building_innovative_teams_that_scale_INO207.pdf))
* [Would you like architects with your architecture?](https://architectelevator.com/architecture/organizing-architecture/)

### Platform
* [Building Infrastructure Platforms](https://martinfowler.com/articles/building-infrastructure-platform.html)
* [Integrating Backstage at DAZN](https://medium.com/dazn-tech/integrating-backstage-at-dazn-b8ef5268b347)
* [Platform Product Management Versus Platform Engineering](https://www.forrester.com/blogs/platform-product-management-versus-platform-engineering/)
* [The Magic of Platforms • Gregor Hohpe • PlatformCon 2022](https://www.youtube.com/watch?v=WaL3ZbLgMuI)

### Product
* [How Detailed Should a User Story Be?](https://www.mountaingoatsoftware.com/blog/what-level-of-detail-should-be-captured-in-a-user-story)
* [Product Backlog Building Canvas](https://martinfowler.com/articles/product-backlog-building-canvas.html)
* Product requirements: User/actor, Functional, Non-Functional, Technical (not usually in the story)
* [Product Requirements Document](https://www.productplan.com/glossary/product-requirements-document/)
* [Product requirements documents, downsized](https://www.atlassian.com/agile/product-management/requirements)
* [Shape Up: Mapping the Scopes](https://basecamp.com/shapeup/3.3-chapter-12)
* Story types:
   * User Story – _“As a [type of user] I [want this thing] so that [I can accomplish this goal]”_. Example: _“As a site visitor, I want to see new content when I come to the site, so I come back more often”_.
   * Job Story – _“When [situation], I want to [motivation], So I can [expected outcome]”_. Example: _“When it’s dinner time tonight, I want to have pizza so I can easily feed my friends”_.
   * Feature-Driven Development (FDD) – _“[action] the [result] [by|for|of|to] a(n) [object]”_. Example: _“Generate a unique identifier for a transaction”_.
* [Why the Three-Part User Story Template Works So Well](https://www.mountaingoatsoftware.com/blog/why-the-three-part-user-story-template-works-so-well)

### Product-market fit
* [Box’s Aaron Levie on navigating SaaS’ several stages of growth](https://www.mckinsey.com/industries/technology-media-and-telecommunications/our-insights/boxs-aaron-levie-on-navigating-saas-several-stages-of-growth)
* [Managing growth and value creation in SaaS: An interview with a software leader](https://www.mckinsey.com/industries/technology-media-and-telecommunications/our-insights/managing-growth-and-value-creation-in-saas)

### Profitable growth
* [A CEO’s tactical guide to driving profitable growth](https://www.bvp.com/atlas/a-ceo-s-tactical-guide-to-driving-profitable-growth)

### Security
* [AWS Security Maturity Model](https://maturitymodel.security.aws.dev/en/model/)
* [AWS Startup Security Baseline (AWS SSB)](https://docs.aws.amazon.com/prescriptive-guidance/latest/aws-startup-security-baseline/welcome.html)

### Technology landscape
* [ThoughtWorks Technology Radar](https://www.thoughtworks.com/radar)

### Working backwards
* [Amazon’s Not So Secret Weapon - The magic of Working Backwards: a real-world case study](https://medium.com/nerd-for-tech/how-i-grew-an-engineering-productivity-tool-to-impact-thousands-of-engineers-at-amazon-and-how-28a990091207)
* [HEY Bubble Up: From kickoff to launch](https://updates.basecamp.com/post/hey-bubble-up)

## Jobs-to-be-done
### Access control and isolation
* [A Rails Multi-Tenant Strategy That's ~30 Lines and "Just Works"](https://dev.to/kolide/a-rails-multi-tenant-strategy-thats-30-lines-and-just-works-58cd)
* [Amazon CodeWhisperer Customizations architecture case study](https://aws.amazon.com/blogs/devops/generative-ai-meets-aws-security/)
* [Building Multi-Tenant Solutions with Amazon OpenSearch Service](https://www.youtube.com/watch?v=FswkQ8YfZyc)
* [How to implement SaaS tenant isolation with ABAC and AWS IAM](https://aws.amazon.com/blogs/security/how-to-implement-saas-tenant-isolation-with-abac-and-aws-iam/)
* [How to secure CI/CD roles without burning production to the ground](https://theburningmonk.com/2024/02/how-to-secure-ci-cd-roles-without-burning-production-to-the-ground/)
* [Implementing SaaS Tenant Isolation Using Amazon SageMaker Endpoints and IAM](https://aws.amazon.com/blogs/apn/implementing-saas-tenant-isolation-using-amazon-sagemaker-endpoints-and-iam/)
* [Performance isolation in a multi-tenant database environment](https://blog.cloudflare.com/performance-isolation-in-a-multi-tenant-database-environment/)
* [SaaS tenant isolation with ABAC using AWS STS support for tags in JWT](https://aws.amazon.com/blogs/security/saas-tenant-isolation-with-abac-using-aws-sts-support-for-tags-in-jwt/)
* [Secure data movement across Amazon S3 and Amazon Redshift using role chaining and ASSUMEROLE](https://aws.amazon.com/blogs/big-data/secure-data-movement-across-amazon-s3-and-amazon-redshift-using-role-chaining-and-assumerole/)
* [Securing Multi-Tenant Kubernetes Clusters at Scale](https://www.youtube.com/watch?v=WS2Qgx0qgCM)
* Solving large-scale data access challenges with Amazon S3 ([video](https://www.youtube.com/watch?v=BOz2_hgoob4), [slides](https://d1.awsstatic.com/events/Summits/reinvent2022/STG328_Solving-large-scale-data-access-challenges-with-Amazon-S3.pdf))

### API
* [APIs as infrastructure: future-proofing Stripe with versioning](https://stripe.com/blog/api-versioning)
* [Architecture patterns for consuming private APIs cross-account](https://aws.amazon.com/blogs/compute/architecture-patterns-for-consuming-private-apis-cross-account/)
* [Best practices for working with the Apache Velocity Template Language in Amazon API Gateway](https://aws.amazon.com/blogs/compute/best-practices-for-working-with-the-apache-velocity-template-language-in-amazon-api-gateway/)
* How Netflix Scales its API with GraphQL Federation ([Part 1](https://netflixtechblog.com/how-netflix-scales-its-api-with-graphql-federation-part-1-ae3557c187e2), [Part 2](https://netflixtechblog.com/how-netflix-scales-its-api-with-graphql-federation-part-2-bbe71aaec44a))
* [Should you use a Lambda Monolith, aka Lambdalith, for your API?](https://rehanvdm.com/blog/should-you-use-a-lambda-monolith-lambdalith-for-the-api)

### Authentication and authorization
* A day in the life of a billion requests ([slides](https://d1.awsstatic.com/events/Summits/reinvent2022/SEC404_A-day-in-the-life-of-a-billion-requests.pdf), [video](https://www.youtube.com/watch?v=tPr1AgGkvc4))
* [DynamoDB now supports resource-based policies. But is that a good idea?](https://theburningmonk.com/2024/03/dynamodb-now-supports-resource-based-policies-but-is-that-a-good-idea/)
* [Edge Authentication and Token-Agnostic Identity Propagation](https://netflixtechblog.com/edge-authentication-and-token-agnostic-identity-propagation-514e47e0b602)
* [Enhancing Amazon DynamoDB single-table design with AWS AppSync access and security features](https://aws.amazon.com/blogs/mobile/enhancing-dynamodb-single-table-design-with-appsync-access-and-security-features/)
* [Entitlements: Architecting Authorization](https://www.styra.com/blog/entitlements-architecting-authorization/)
* [How to Persist JWT Tokens for Your SaaS Application](https://frontegg.com/blog/how-to-persist-jwt-tokens-for-your-saas-application)
* [Amazon DocumentDB (with MongoDB compatibility) user-defined roles for access control](https://aws.amazon.com/blogs/database/introducing-amazon-documentdb-with-mongodb-compatibility-user-defined-roles-for-access-control/)
* [JSON Web Token (JWT) Profile for OAuth 2.0 Access Tokens](https://datatracker.ietf.org/doc/html/rfc9068)
* [On The Nature of OAuth2’s Scopes](https://auth0.com/blog/on-the-nature-of-oauth2-scopes/)

### Configuration
* [Continuous Configuration at the Speed of Sound](https://www.allthingsdistributed.com/2021/08/continuous-configuration-on-aws.html)

### Data lake
* [Building and scaling Notion’s data lake](https://www.notion.so/blog/building-and-scaling-notions-data-lake)

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
* [Continuous Delivery: Anatomy of the Deployment Pipeline](https://www.informit.com/articles/article.aspx?p=1621865)
* [Continuous Delivery of Amazon EKS Clusters Using AWS CDK and CDK Pipelines](https://aws.amazon.com/blogs/containers/continuous-delivery-of-amazon-eks-clusters-using-aws-cdk-and-cdk-pipelines/)
* [Deploying GitOps with Weave Flux and Amazon EKS](https://aws.amazon.com/blogs/compute/deploying-gitops-with-weave-flux-and-amazon-eks/)
* [Deployment Pipelines Reference Architecture and Reference Implementations](https://aws.amazon.com/blogs/aws/new_deployment_pipelines_reference_architecture_and_-reference_implementations/)
* [Ensuring rollback safety during deployments](https://aws.amazon.com/builders-library/ensuring-rollback-safety-during-deployments/)
* Migrating Critical Traffic At Scale with No Downtime ([Part 1](https://netflixtechblog.com/migrating-critical-traffic-at-scale-with-no-downtime-part-1-ba1c7a1c7835), [Part 2](https://netflixtechblog.com/migrating-critical-traffic-at-scale-with-no-downtime-part-2-4b1c8c7155c1))
* [My CI/CD pipeline is my release captain](https://aws.amazon.com/builders-library/cicd-pipeline/)
* [Overview of Deployment Options on AWS](https://docs.aws.amazon.com/whitepapers/latest/overview-deployment-options/welcome.html)
* [Parallel and dynamic SaaS deployments with AWS CDK Pipelines](https://aws.amazon.com/blogs/devops/parallel-and-dynamic-saas-deployments-with-cdk-pipelines/)
* [Practicing Continuous Integration and Continuous Delivery on AWS](https://docs.aws.amazon.com/whitepapers/latest/practicing-continuous-integration-continuous-delivery/welcome.html)
* Releasing Mission-Critical Software at Amazon ([video](https://www.youtube.com/watch?v=I61KKO1rAQ8&feature=youtu.be), [slides](https://www.slideshare.net/AmazonWebServices/releasing-missioncritical-software-at-amazon-dev209r1-aws-reinvent-2018))
* [Rolling Forward and other Deployment Myths](https://dzone.com/articles/rolling-forward-and-other)
* [Seamless branch deploys with Kubernetes](https://m.signalvnoise.com/seamless-branch-deploys-with-kubernetes/)
* [Serverless CI/CD for the Enterprise on AWS](https://aws.amazon.com/quickstart/architecture/serverless-cicd-for-enterprise/)
* [The Scary Thing About Automating Deploys](https://slack.engineering/the-scary-thing-about-automating-deploys/)
* [Using AWS Step Functions State Machines to Handle Workflow-Driven AWS CodePipeline Actions](https://aws.amazon.com/blogs/devops/using-aws-step-functions-state-machines-to-handle-workflow-driven-aws-codepipeline-actions/)
* [Validating AWS CodeCommit Pull Requests with AWS CodeBuild and AWS Lambda](https://aws.amazon.com/blogs/devops/validating-aws-codecommit-pull-requests-with-aws-codebuild-and-aws-lambda/)

### Development
* [Applying  the Twelve-Factor App Methodology to Serverless Applications](https://aws.amazon.com/blogs/compute/applying-the-twelve-factor-app-methodology-to-serverless-applications/)
* [Branch by Abstraction](https://www.branchbyabstraction.com/) for major changes that take time
* Building production-ready prototypes ([video](https://www.youtube.com/watch?v=-_Zl9u9i1KI), [slides](https://d1.awsstatic.com/events/reinvent/2021/Building_productionready_prototypes_ARC330.pdf))
* [Deploy AWS Organizations resources by using CloudFormation](https://aws.amazon.com/blogs/security/deploy-aws-organizations-resources-by-using-cloudformation/)
* [IAC Adoption Monitor](https://github.com/aws-samples/monitor-your-iac-adoption-using-aws-cloudformation-iac-generator)
* [Include CloudFormation templates in the CDK](https://docs.aws.amazon.com/cdk/api/latest/docs/cloudformation-include-readme.html)
* [Managing resources using AWS CloudFormation Resource Types](https://aws.amazon.com/blogs/mt/managing-resources-using-aws-cloudformation-resource-types/)
* [Running bash commands in AWS CloudFormation templates](https://aws.amazon.com/blogs/mt/running-bash-commands-in-aws-cloudformation-templates/)
* [The Twelve-Factor App](https://12factor.net/)
* [This is why you should keep stateful and stateless resources together](https://theburningmonk.com/2023/01/this-is-why-you-should-keep-stateful-and-stateless-resources-together/)
* [Trunk-Based Development](https://trunkbaseddevelopment.com/)

### Encryption
* [AWS KMS: How many keys do I need?](https://aws.amazon.com/blogs/security/aws-kms-how-many-keys-do-i-need/)
* [Control Access to Your Data with Slack Enterprise Key Management and AWS KMS](https://aws.amazon.com/blogs/apn/control-access-to-your-data-with-slack-enterprise-key-management-and-aws-kms/)

### Extensibility
* Supporting extensibility in SaaS environments ([video](https://www.youtube.com/watch?v=uzRrEWzqD0Y), [slides](https://d1.awsstatic.com/events/Summits/reinvent2022/SAS302_Supporting-extensibility-in-SaaS-environments.pdf))

### Frontend
* [How Capital One Builds Micro-Frontends At Scale](https://www.capitalone.com/tech/software-engineering/loosely-coupled-micro-frontends-with-nodejs/)

### Hybrid architecture
* [Build a Hybrid Architecture for Local Compliance and Global Scalability](https://aws.amazon.com/blogs/startups/build-a-hybrid-architecture-for-local-compliance-and-global-scalability/)

### Integration patterns
* [Architecture patterns for consuming private APIs cross-account](https://aws.amazon.com/blogs/compute/architecture-patterns-for-consuming-private-apis-cross-account/)
* [Implementing the transactional outbox pattern with Amazon EventBridge Pipes](https://aws.amazon.com/blogs/compute/implementing-the-transactional-outbox-pattern-with-amazon-eventbridge-pipes/)
* [Starbucks Does Not Use Two-Phase Commit](https://www.enterpriseintegrationpatterns.com/ramblings/18_starbucks.html)

### Internet of Things (IoT)
* [How BISSELL migrated a million vacuum devices to a scalable IoT Platform on AWS](https://aws.amazon.com/blogs/iot/how-bissell-migrated-a-million-vacuum-devices-to-a-scalable-iot-platform-on-aws/)

### Machine learning
* [Engineering Practices for LLM Application Development](https://martinfowler.com/articles/engineering-practices-llm.html)
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
* [Streamline and secure access to shared services and resources with Amazon VPC Lattice](https://aws.amazon.com/blogs/networking-and-content-delivery/streamline-and-secure-access-to-shared-services-and-resources-with-amazon-vpc-lattice/)
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
    * [Part 1: Customers, Culture, and why you should care](https://medium.com/@adhorn/towards-operational-excellence-35ba6298b12f)
    * [Part 2: On the importance of tools](https://medium.com/@adhorn/towards-operational-excellence-c9fe298e27e7)
    * [Part 3: Mechanisms](https://medium.com/@adhorn/towards-operational-excellence-part-3-8b727f06a4b6)
* [ZEN and the art of Reliability](https://zendesk.engineering/zen-and-the-art-of-reliability-f42fa7e64849)

### Reliability
* [Enhancing Netflix Reliability with Service-Level Prioritized Load Shedding](https://netflixtechblog.com/enhancing-netflix-reliability-with-service-level-prioritized-load-shedding-e735e6ce8f7d)

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
   * [Part 1: The Data Model](https://www.etsy.com/il-en/codeascraft/scaling-etsy-payments-with-vitess-part-1--the-data-model)
   * [Part 2: The “Seamless” Migration](https://www.etsy.com/il-en/codeascraft/scaling-etsy-payments-with-vitess-part-2--the-seamless-migration)
   * [Part 3: Reducing Cutover Risk](https://www.etsy.com/il-en/codeascraft/scaling-etsy-payments-with-vitess-part-3--reducing-cutover-risk)

### Tenant costs
* [Calculating Tenant Costs in SaaS Environments](https://aws.amazon.com/blogs/apn/calculating-tenant-costs-in-saas-environments/)
* [Calculating SaaS Cost Per Tenant: A PoC Implementation in an AWS Kubernetes Environment](https://aws.amazon.com/blogs/apn/calculating-saas-cost-per-tenant-a-poc-implementation-in-an-aws-kubernetes-environment/)

### Tenant management
* [How CyberArk Built a Tenant Management Service for its SaaS Offering](https://aws.amazon.com/blogs/apn/how-cyberark-built-tenant-management-service-for-its-saas-offering/)

### Testing
* [Running end-to-end Cypress tests for your fullstack CI/CD deployment with Amplify Console](https://aws.amazon.com/blogs/mobile/running-end-to-end-cypress-tests-for-your-fullstack-ci-cd-deployment-with-amplify-console/)
* [Test Reports with AWS CodeBuild](https://aws.amazon.com/blogs/devops/test-reports-with-aws-codebuild/)
* [The Practical Test Pyramid](https://martinfowler.com/articles/practical-test-pyramid.html)
