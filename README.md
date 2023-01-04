# Awesome Architecture ![Awesome](https://awesome.re/badge.svg)
A collection of awesome things related to Architecture

## API
* AWS - [Architecture patterns for consuming private APIs cross-account](https://aws.amazon.com/blogs/compute/architecture-patterns-for-consuming-private-apis-cross-account/)
* Netflix - How Netflix Scales its API with GraphQL Federation ([Part 1](https://netflixtechblog.com/how-netflix-scales-its-api-with-graphql-federation-part-1-ae3557c187e2), [Part 2](https://netflixtechblog.com/how-netflix-scales-its-api-with-graphql-federation-part-2-bbe71aaec44a))

## Authentication and authorization
* Auth0 - [On The Nature of OAuth2’s Scopes](https://auth0.com/blog/on-the-nature-of-oauth2-scopes/)
* Styra - [Entitlements: Architecting Authorization](https://www.styra.com/blog/entitlements-architecting-authorization/)
* Frontegg - [How to Persist JWT Tokens for Your SaaS Application](https://frontegg.com/blog/how-to-persist-jwt-tokens-for-your-saas-application)
* Netflix - [Edge Authentication and Token-Agnostic Identity Propagation](https://netflixtechblog.com/edge-authentication-and-token-agnostic-identity-propagation-514e47e0b602)
* AWS - [Introducing Amazon DocumentDB (with MongoDB compatibility) user-defined roles for access control](https://aws.amazon.com/blogs/database/introducing-amazon-documentdb-with-mongodb-compatibility-user-defined-roles-for-access-control/)
* AWS - [Enhancing Amazon DynamoDB single-table design with AWS AppSync access and security features](https://aws.amazon.com/blogs/mobile/enhancing-dynamodb-single-table-design-with-appsync-access-and-security-features/)
* IETF - [JSON Web Token (JWT) Profile for OAuth 2.0 Access Tokens](https://datatracker.ietf.org/doc/html/rfc9068)

## Case studies
* SoundCloud - [How we ended up with microservices](https://philcalcado.com/2015/09/08/how_we_ended_up_with_microservices.html)
* Carlos Arguelles - [Amazon’s Not So Secret Weapon - The magic of Working Backwards: a real-world case study](https://medium.com/nerd-for-tech/how-i-grew-an-engineering-productivity-tool-to-impact-thousands-of-engineers-at-amazon-and-how-28a990091207)
* DAZN - [Integrating Backstage at DAZN](https://medium.com/dazn-tech/integrating-backstage-at-dazn-b8ef5268b347)
* Amazon - [Amazon CISO Jeff Carter - Securing Amazon.com and Migrating Databases to the Cloud](https://www.youtube.com/watch?v=5xuCQJzv7eM)

## CI/CD
* AWS - [Automate rollbacks for Amazon ECS rolling deployments with CloudWatch alarms](https://aws.amazon.com/blogs/containers/automate-rollbacks-for-amazon-ecs-rolling-deployments-with-cloudwatch-alarms/)
* Jim Bird - [Rolling Forward and other Deployment Myths](https://dzone.com/articles/rolling-forward-and-other)
* Basecamp - [Seamless branch deploys with Kubernetes](https://m.signalvnoise.com/seamless-branch-deploys-with-kubernetes/)
* AWS - [Continuous Delivery of Amazon EKS Clusters Using AWS CDK and CDK Pipelines](https://aws.amazon.com/blogs/containers/continuous-delivery-of-amazon-eks-clusters-using-aws-cdk-and-cdk-pipelines/)
* Amazon - Hands-off: Automating continuous delivery pipelines at Amazon ([video](https://youtu.be/ngnMj1zbMPY), [article](https://aws.amazon.com/builders-library/automating-safe-hands-off-deployments/), [podcast](https://www.infoq.com/podcasts/aws-deployments/))
* AWS - [CDK Pipelines: Continuous delivery for AWS CDK applications](https://aws.amazon.com/blogs/developer/cdk-pipelines-continuous-delivery-for-aws-cdk-applications/)
* AWS - [Building a cross-account continuous delivery pipeline for database migrations](https://aws.amazon.com/blogs/database/building-a-cross-account-continuous-delivery-pipeline-for-database-migrations/)
* AWS - [Serverless CI/CD for the Enterprise on AWS](https://aws.amazon.com/quickstart/architecture/serverless-cicd-for-enterprise/)
* AWS - Best practices for CI/CD using AWS Fargate and Amazon ECS ([video](https://www.youtube.com/watch?v=7FVK0i9edyg), [slides](https://d1.awsstatic.com/events/reinvent/2019/REPEAT_2_Best_practices_for_CICD_using_AWS_Fargate_and_Amazon_ECS_CON333-R2.pdf))
* Amazon - Amazon CI/CD Practices for Software Development Teams ([video](https://youtu.be/3HKbXz0RwSg), [slides](https://www.slideshare.net/AmazonWebServices/amazon-cicd-practices-for-software-development-teams))
* AWS - [Best  Practices for CI/CD with AWS Lambda and Amazon API Gateway](https://www.slideshare.net/AmazonWebServices/best-practices-for-cicd-with-aws-lambda-and-amazon-api-gateway-srv355r1-aws-reinvent-2018)
* Amazon - [Ensuring rollback safety during deployments](https://aws.amazon.com/builders-library/ensuring-rollback-safety-during-deployments/)
* AWS - [Building and testing polyglot applications using AWS CodeBuild](https://aws.amazon.com/blogs/devops/building-and-testing-polyglot-applications-using-aws-codebuild/)
* AWS - [Deploying GitOps with Weave Flux and Amazon EKS](https://aws.amazon.com/blogs/compute/deploying-gitops-with-weave-flux-and-amazon-eks/)
* AWS - [Include CloudFormation templates in the CDK](https://docs.aws.amazon.com/cdk/api/latest/docs/cloudformation-include-readme.html)
* AWS - [Validating AWS CodeCommit Pull Requests with AWS CodeBuild and AWS Lambda](https://aws.amazon.com/blogs/devops/validating-aws-codecommit-pull-requests-with-aws-codebuild-and-aws-lambda/)
* AWS - [Running end-to-end Cypress tests for your fullstack CI/CD deployment with Amplify Console](https://aws.amazon.com/blogs/mobile/running-end-to-end-cypress-tests-for-your-fullstack-ci-cd-deployment-with-amplify-console/)
* AWS - [Test Reports with AWS CodeBuild](https://aws.amazon.com/blogs/devops/test-reports-with-aws-codebuild/)
* AWS - [New – Building a Continuous Integration Workflow with Step Functions and AWS CodeBuild](https://aws.amazon.com/blogs/aws/new-building-a-continuous-integration-workflow-with-step-functions-and-aws-codebuild/)
* AWS - [Using AWS Step Functions State Machines to Handle Workflow-Driven AWS CodePipeline Actions](https://aws.amazon.com/blogs/devops/using-aws-step-functions-state-machines-to-handle-workflow-driven-aws-codepipeline-actions/)

## Concepts
* [Application Lifecycle Management (ALM)](https://aws.amazon.com/what-is/application-lifecycle-management/)
* [Architecturally significant requirements](https://en.wikipedia.org/wiki/Architecturally_significant_requirements) criteria: business value/risk, stakeholder concern, quality level, external dependencies, cross-cutting, first-of-a-kind, source of problems on past projects.
* [Architecture decision records (ADRs)](https://docs.aws.amazon.com/prescriptive-guidance/latest/architectural-decision-records/appendix.html) support team alignment, document strategic directions for a project or product, and reduce recurring and time-consuming decision-making efforts
* [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html) pillars: 1/ Operational excellence 2/ Security 3/ Reliability 4/ Performance efficiency 5/ Cost optimization
* [Coupling facets](https://youtu.be/w9a7eI6BlVc?t=1487): 1/ Technology (Java vs. C++, Kubernetes, PostgreSQL) 2/ Location (IP addresses, DNS) 3/ Data Format (Binary, XML, JSON, protobuf, Avro) 4/ Data Type (int16, int32, string, UTF-8, null, empty) 5/ Semantic (Name, Middlename, ZIP) 6/ Temporal (sync, async) 7/ Interaction Style (messaging, RPC, query, GraphQL) 8/ Conversation (pagination, caching, retries)
* [Declarative provisioning not equal to Declarative language](https://www.youtube.com/watch?v=ttJAIQf7cTw&t=2077s)
* [Event-Driven Architecture](https://www.youtube.com/watch?v=STKCRSUsyP0&feature=share) patterns: 1/ Event Notification 2/ Event-carried State Transfer 3/ Event Sourcing 4/ Command and Query Responsibility Segregation.
* Software Boundaries or "Fracture Planes" ([Matthew Skelton](https://blog.matthewskelton.net/about/)): 1/ Business Domain Bounded Context 2/ Regulatory Compliance 3/ Change Cadence 4/ Team Location 5/ Risk 6/ Performance Isolation 7/ Technology 8/ User Personas
* Software delivery performance four key metrics: 1/ Cycle Time (Change Lead Time) 2/ Deployment Frequency 3/ Change Failure Rate (CFR) 4/ Mean Time to Recovery (MTTR)

## Data isolation
* AWS - [Secure data movement across Amazon S3 and Amazon Redshift using role chaining and ASSUMEROLE](https://aws.amazon.com/blogs/big-data/secure-data-movement-across-amazon-s3-and-amazon-redshift-using-role-chaining-and-assumerole/)

## Frontend
* Capital One - [How Capital One Builds Micro-Frontends At Scale](https://www.capitalone.com/tech/software-engineering/loosely-coupled-micro-frontends-with-nodejs/)

## Hybrid architecture
* AWS - [Build a Hybrid Architecture for Local Compliance and Global Scalability](https://aws.amazon.com/blogs/startups/build-a-hybrid-architecture-for-local-compliance-and-global-scalability/)

## Infrastructure as Code
* AWS - [Running bash commands in AWS CloudFormation templates](https://aws.amazon.com/blogs/mt/running-bash-commands-in-aws-cloudformation-templates/)
* AWS - Building production-ready prototypes ([video](https://www.youtube.com/watch?v=-_Zl9u9i1KI), [slides](https://d1.awsstatic.com/events/reinvent/2021/Building_productionready_prototypes_ARC330.pdf))
* AWS - [Managing resources using AWS CloudFormation Resource Types](https://aws.amazon.com/blogs/mt/managing-resources-using-aws-cloudformation-resource-types/)

## Integration patterns
* Gregor Hohpe - [Starbucks Does Not Use Two-Phase Commit](https://www.enterpriseintegrationpatterns.com/ramblings/18_starbucks.html)

## Internet of Things (IoT)
* BISSELL - [How BISSELL migrated a million vacuum devices to a scalable IoT Platform on AWS](https://aws.amazon.com/blogs/iot/how-bissell-migrated-a-million-vacuum-devices-to-a-scalable-iot-platform-on-aws/)

## Learning from failures
* 37signals - [Accounting for the Basecamp 3 outage on June 27, 2022](https://updates.basecamp.com/post/accounting-for-the-basecamp-3-outage-on-june-27-2022)

## Live migration
* Spotify - [Changing the Wheels on a Moving Bus — Spotify’s Event Delivery Migration](https://engineering.atspotify.com/2021/10/20/changing-the-wheels-on-a-moving-bus-spotify-event-delivery-migration/)

## Methodology
* Chris Richardson - [Minimizing Design Time Coupling in a Microservice Architecture](https://www.infoq.com/presentations/microservices-design-time-coupling/)
* James Hamilton - [On Designing and Deploying Internet-Scale Services](https://mvdirona.com/jrh/talksAndPapers/JamesRH_Lisa.pdf)
* Amazon - [Operational Readiness Reviews (ORR)](https://docs.aws.amazon.com/wellarchitected/latest/operational-readiness-reviews/wa-operational-readiness-reviews.html)
* martinfowler.com - [Building Infrastructure Platforms](https://martinfowler.com/articles/building-infrastructure-platform.html)
* martinfowler.com - [Compliance in a DevOps Culture](https://martinfowler.com/articles/devops-compliance.html)
* Pedro Del Gallego - [The Away Team Model at Amazon](https://pedrodelgallego.github.io/blog/amazon/operating-model/away-team-model/)
* martinfowler.com - [The Practical Test Pyramid](https://martinfowler.com/articles/practical-test-pyramid.html)
* AWS - [Overview of Deployment Options on AWS](https://docs.aws.amazon.com/whitepapers/latest/overview-deployment-options/welcome.html)
* AWS - [Practicing Continuous Integration and Continuous Delivery on AWS](https://docs.aws.amazon.com/whitepapers/latest/practicing-continuous-integration-continuous-delivery/welcome.html)
* [The Twelve-Factor App](https://12factor.net/). 
* AWS - [Applying  the Twelve-Factor App Methodology to Serverless Applications](https://aws.amazon.com/blogs/compute/applying-the-twelve-factor-app-methodology-to-serverless-applications/)
* [Trunk-Based Development](https://trunkbaseddevelopment.com/). Amazon encourages this development model - see “before we begin” section in [Implementing GitFlow Using AWS CodePipeline, AWS CodeCommit, AWS CodeBuild, and AWS CodeDeploy](https://aws.amazon.com/blogs/devops/implementing-gitflow-using-aws-codepipeline-aws-codecommit-aws-codebuild-and-aws-codedeploy/)
* [Branch by Abstraction](https://www.branchbyabstraction.com/) for major changes that take time
* LaunchDarkly - [Feature Flags](https://launchdarkly.com/blog/what-are-feature-flags/) for deciding when to release new capabilities
* ThoughtWorks - [Technology Radar](https://www.thoughtworks.com/radar)
* AWS - [Establishing your best practice AWS environment](https://aws.amazon.com/organizations/getting-started/best-practices/)
* AWS - Two-pizza teams: Organizing for innovation ([video](https://www.youtube.com/watch?v=XavPl5t9dS8), [slides](https://d1.awsstatic.com/events/reinvent/2020/TwoPizza_Teams_Building_innovative_teams_that_scale_INO207.pdf))
* [Continuous Configuration at the Speed of Sound](https://www.allthingsdistributed.com/2021/08/continuous-configuration-on-aws.html)
* Towards Operational Excellence blog post series:
    * [Part 1 — Customers, Culture, and why you should care](https://medium.com/@adhorn/towards-operational-excellence-35ba6298b12f)
    * [Part 2 —On the importance of tools](https://medium.com/@adhorn/towards-operational-excellence-c9fe298e27e7)
    * [Part 3 — Mechanisms](https://medium.com/@adhorn/towards-operational-excellence-part-3-8b727f06a4b6)
* Amazon - Amazon’s approach to failing successfully ([video](https://www.youtube.com/watch?v=yQiRli2ZPxU), [slides](https://d1.awsstatic.com/events/reinvent/2019/REPEAT_1_Amazon%E2%80%99s_approach_to_failing_successfully_DOP208-R1.pdf))
* AWS - Leadership Session: Developer Tools on AWS ([video](https://www.youtube.com/watch?v=p9IybVJp5QM), [slides](https://d1.awsstatic.com/events/reinvent/2019/Leadership_Session_Developer_Tools_on_AWS_DOP210-L.pdf))
* Amazon - Amazon's approach to high-availability deployment ([video](https://www.youtube.com/watch?v=bCgD2bX1LI4), [slides](https://d1.awsstatic.com/events/reinvent/2019/REPEAT_1_Amazon's_approach_to_high-availability_deployment_DOP404-R1.pdf.pdf))
* AWS - [Failing successfully: The AWS approach to resilient design](https://d1.awsstatic.com/events/reinvent/2019/REPEAT_2_Failing_successfully_The_AWS_approach_to_resilient_design_ARC303-R2.pdf)
* Amazon - Releasing Mission-Critical Software at Amazon ([video](https://www.youtube.com/watch?v=I61KKO1rAQ8&feature=youtu.be), [slides](https://www.slideshare.net/AmazonWebServices/releasing-missioncritical-software-at-amazon-dev209r1-aws-reinvent-2018))
* Amazon - [DevOps at Amazon: A Look at Our Tools and Processes](https://www.youtube.com/watch?v=esEFaY0FDKc)
* Amazon - [Fireside Chat: DevOps at Amazon with Ken Exner, GM of AWS Developer Tools - AWS Online Tech Talks](https://www.youtube.com/watch?v=FlZm3nFMIAM&feature=youtu.be)

## Multi-region architecture and disaster recovery
* AWS - [Implement Multi-Region Serverless (and Functionless) WebSocket Pub/Sub APIs with AWS AppSync and Amazon EventBridge](https://aws.amazon.com/blogs/mobile/multi-region-websocket-api/)

## Networking
* AWS - [Designing hyperscale Amazon VPC networks](https://aws.amazon.com/blogs/networking-and-content-delivery/designing-hyperscale-amazon-vpc-networks/)
* AWS - [Addressing latency and data transfer costs on EKS using Istio](https://aws.amazon.com/blogs/containers/addressing-latency-and-data-transfer-costs-on-eks-using-istio/)
* AWS - [VPC sharing: key considerations and best practices](https://aws.amazon.com/blogs/networking-and-content-delivery/vpc-sharing-key-considerations-and-best-practices/)
* FactSet - [How FactSet handles networking for 1000+ AWS accounts](https://aws.amazon.com/blogs/networking-and-content-delivery/how-factset-handles-networking-for-1000-aws-accounts/)
* Slack - [Building the Next Evolution of Cloud Networks at Slack – A Retrospective](https://slack.engineering/building-the-next-evolution-of-cloud-networks-at-slack-a-retrospective/)

## Observability
* Amazon - [Building dashboards for operational visibility](https://aws.amazon.com/builders-library/building-dashboards-for-operational-visibility/)
* AWS - [AWS X-Ray](https://docs.aws.amazon.com/xray/latest/devguide/aws-xray.html) (see also [Integrating  AWS X-Ray with Other AWS Services](https://docs.aws.amazon.com/xray/latest/devguide/xray-services.html))
* AWS - [AWS  X-Ray Now Supports Amazon API Gateway and New Sampling Rules API](https://aws.amazon.com/blogs/aws/apigateway-xray/)
* AWS - [Visualize and Monitor Highly Distributed Applications with Amazon CloudWatch ServiceLens](https://aws.amazon.com/blogs/aws/visualize-and-monitor-highly-distributed-applications-with-amazon-cloudwatch-servicelens/)
* AWS - [Debugging with Amazon CloudWatch Synthetics and AWS X-Ray](https://aws.amazon.com/blogs/devops/debugging-with-amazon-cloudwatch-synthetics-and-aws-x-ray/)
* AWS - [Amazon CloudWatch Now Includes Contributor Insights - in Preview](https://aws.amazon.com/about-aws/whats-new/2019/11/amazon-cloudwatch-now-includes-contributor-insights-preview/)
* AWS - [Container monitoring for Amazon ECS, EKS, and Kubernetes is now available in Amazon CloudWatch](https://aws.amazon.com/about-aws/whats-new/2019/08/container-monitoring-for-amazon-ecs-eks-and-kubernetes-is-now-available-in-amazon-cloudwatch/)
* AWS - [Using Prometheus Metrics in Amazon CloudWatch](https://aws.amazon.com/blogs/containers/using-prometheus-metrics-in-amazon-cloudwatch/)
* AWS - [One observability workshop](https://catalog.workshops.aws/observability/)

## Operations
* TheFork - [Kubernetes cluster upgrade: the blue-green deployment strategy](https://aws.amazon.com/blogs/containers/kubernetes-cluster-upgrade-the-blue-green-deployment-strategy/)
* AWS - [Resolve IT Incidents Faster with Incident Manager, a New Capability of AWS Systems Manager](https://aws.amazon.com/blogs/aws/resolve-it-incidents-faster-with-incident-manager-a-new-capability-of-aws-systems-manager/)

## Reliability
* Zendesk - [ZEN and the art of Reliability](https://zendesk.engineering/zen-and-the-art-of-reliability-f42fa7e64849)

## Sharding and partitioning data
* Slack - [Scaling Datastores at Slack with Vitess](https://slack.engineering/scaling-datastores-at-slack-with-vitess/)
* AWS - [Improve performance and manageability of large PostgreSQL tables by migrating to partitioned tables on Amazon Aurora and Amazon RDS](https://aws.amazon.com/blogs/database/improve-performance-and-manageability-of-large-postgresql-tables-by-migrating-to-partitioned-tables-on-amazon-aurora-and-amazon-rds/)
* GitHub - [Partitioning GitHub’s relational databases to handle scale](https://github.blog/2021-09-27-partitioning-githubs-relational-databases-scale/)
* GitLab - Decomposing the GitLab backend database: [Part 1: Designing and planning](https://about.gitlab.com/blog/2022/08/04/path-to-decomposing-gitlab-database-part1/), [Part 2: Final migration and results](https://about.gitlab.com/blog/2022/08/04/path-to-decomposing-gitlab-database-part2/), [Part 3: Challenges and surprises](https://about.gitlab.com/blog/2022/08/04/path-to-decomposing-gitlab-database-part3/)
* Notion - [Herding elephants: Lessons learned from sharding Postgres at Notion](https://www.notion.so/blog/sharding-postgres-at-notion)
* Shopify - [E-Commerce at Scale: Inside Shopify's Tech Stack - Stackshare.io](https://shopify.engineering/e-commerce-at-scale-inside-shopifys-tech-stack)

## Shipping
* 37signals - [HEY Bubble Up: From kickoff to launch](https://updates.basecamp.com/post/hey-bubble-up)
* 37signals - [Seven Shipping Principles](https://37signals.com/seven-shipping-principles)
