# Awesome DevOps and AWS [![Awesome](https://awesome.re/badge.svg)](https://awesome.re) [<img src="https://raw.githubusercontent.com/aws/aws-cdk/master/logo/default-128-dark.png" align="right" alt="CDK">](https://github.com/aws/aws-cdk)

A collection of awesome things related to DevOps and AWS

# DevOps on AWS

## Methodology

* Follow [The Twelve-Factor App](https://12factor.net/) principles. See also [Applying  the Twelve-Factor App Methodology to Serverless Applications](https://aws.amazon.com/blogs/compute/applying-the-twelve-factor-app-methodology-to-serverless-applications/)
* Create a release branch and apply hotfixes first to master and cherrypick to release branch. This is a [Trunk-Based Development](https://trunkbaseddevelopment.com/) model, which Amazon strongly encourages internally - see “before we begin” in [Implementing GitFlow Using AWS CodePipeline, AWS CodeCommit, AWS CodeBuild, and AWS CodeDeploy](https://aws.amazon.com/blogs/devops/implementing-gitflow-using-aws-codepipeline-aws-codecommit-aws-codebuild-and-aws-codedeploy/). Some exceptions are when a fix was already introduced to master branch somewhere, so in this case it’s faster to temporarily open the release branch for direct pull request (the “temporarily” can be enforced through JIRA and a CI system for example)
* Consider [Branch by Abstraction](https://www.branchbyabstraction.com/) for major changes that take time and continue using Feature Toggles for deciding when to release
* Test upstream dependencies based on their production at the least. A shift left approach would be to test upstream dependencies based on their staging environment (would incur additional costs for each service to support this)
* Separate [Continuous **Delivery**](https://continuousdelivery.com/) and [Continuous] Deployment processes - implement as 2 pipelines. This will enable a decision point as to which regions to deploy instead of all or nothing
    *  **Continuous Delivery** pipeline will build the artifacts, run unit/integration tests (to keep development cycle fast with short feedback loop for developers if something fails at this stage), run system tests, capacity tests, performance tests and promote to staging for manual tests (e.g. manual QA and UAT)
    * **[Continuous] Deployment** pipeline will deploy to specified regions or all at once in rolling manner (to reduce blast radius of failed change), depending on the need. A central database is needed to track deployments and keep versions across regions in sync (e.g. do not deploy newer version in region B, while region A has an older one - upgrade region A first). Deployment might be triggered manually or automatically following the Continuous Delivery pipeline

* ThoughtWorks Technology Radar - [Techniques](https://www.thoughtworks.com/radar/techniques). Specifically, **"Four key metrics"**: The thorough State of DevOps reports have focused on data-driven and statistical analysis of high-performing organizations. The result of this multiyear research, published in Accelerate, demonstrates a direct link between organizational performance and software delivery performance. The researchers have determined that only four key metrics differentiate between low, medium and high performers: **lead time**, **deployment frequency**, **mean time to restore** (MTTR) and **change fail percentage**. Indeed, we've found that these four key metrics are a simple and yet powerful tool to help leaders and teams focus on measuring and improving what matters. A good place to start is to instrument the build pipelines so you can capture the four key metrics and make the software delivery value stream visible
* Use multiple accounts for different Software Development Life Cycle (SDLC) stages to reduce blast radius of configuration changes, security breaches, account or regional quotas (a.k.a. limits) and more. See [Establishing your best practice AWS environment](https://aws.amazon.com/organizations/getting-started/best-practices/) for more motivation and details

## References

* [Amazon CISO Jeff Carter - Securing Amazon.com and Migrating Databases to the Cloud](https://www.youtube.com/watch?v=5xuCQJzv7eM)

## Mindset

* Towards Operational Excellence blog post series:
    * [Part 1 — Customers, Culture, and why you should care](https://medium.com/@adhorn/towards-operational-excellence-35ba6298b12f)
    * [Part 2 —On the importance of tools](https://medium.com/@adhorn/towards-operational-excellence-c9fe298e27e7)
    * [Part 3 — Mechanisms](https://medium.com/@adhorn/towards-operational-excellence-part-3-8b727f06a4b6)
* AWS re:Invent 2019: [REPEAT 1] Amazon’s approach to failing successfully (DOP208-R1) ([video](https://www.youtube.com/watch?v=yQiRli2ZPxU), [slides](https://d1.awsstatic.com/events/reinvent/2019/REPEAT_1_Amazon%E2%80%99s_approach_to_failing_successfully_DOP208-R1.pdf))
* AWS re:Invent 2018: [REPEAT 1] Releasing Mission-Critical Software at Amazon (DEV209-R1) ([video](https://www.youtube.com/watch?v=I61KKO1rAQ8&feature=youtu.be), [slides](https://www.slideshare.net/AmazonWebServices/releasing-missioncritical-software-at-amazon-dev209r1-aws-reinvent-2018))
* AWS re:Invent 2019: [REPEAT 1] Amazon's approach to high-availability deployment (DOP404-R1) ([video](https://www.youtube.com/watch?v=bCgD2bX1LI4), [slides](https://d1.awsstatic.com/events/reinvent/2019/REPEAT_1_Amazon's_approach_to_high-availability_deployment_DOP404-R1.pdf.pdf))
* [Failing successfully: The AWS approach to resilient design](https://d1.awsstatic.com/events/reinvent/2019/REPEAT_2_Failing_successfully_The_AWS_approach_to_resilient_design_ARC303-R2.pdf)
* [Fireside Chat: DevOps at Amazon with Ken Exner, GM of AWS Developer Tools - AWS Online Tech Talks](https://www.youtube.com/watch?v=FlZm3nFMIAM&feature=youtu.be)

## IDE

* [AWS Toolkit for Visual Studio Code Adds New CDK Explorer in Preview](https://aws.amazon.com/about-aws/whats-new/2019/11/aws-toolkit-for-vs-code-adds-new-cdk-explorer-in-preview/)
* [Announcing Cloud Debugging (beta) for Debugging Your Applications Running in the Cloud with JetBrains IDEs](https://aws.amazon.com/about-aws/whats-new/2019/11/announcing-cloud-debugging-beta/)

## Infrastructure as Code

* [Managing resources using AWS CloudFormation Resource Types](https://aws.amazon.com/blogs/mt/managing-resources-using-aws-cloudformation-resource-types/)

## CI/CD

* [CDK Pipelines: Continuous delivery for AWS CDK applications](https://aws.amazon.com/blogs/developer/cdk-pipelines-continuous-delivery-for-aws-cdk-applications/)
* [Continuous Delivery for CDK Apps](https://github.com/aws/aws-cdk-rfcs/blob/master/text/0049-continuous-delivery.md) (AWS CDK RFC)
* [Building a cross-account continuous delivery pipeline for database migrations](https://aws.amazon.com/blogs/database/building-a-cross-account-continuous-delivery-pipeline-for-database-migrations/)
* [Automating cross-account actions with an AWS CDK credential plugin](https://aws.amazon.com/blogs/devops/cdk-credential-plugin/)
* [Serverless CI/CD for the Enterprise on AWS](https://aws.amazon.com/quickstart/architecture/serverless-cicd-for-enterprise/)
* Best practices for CI/CD using AWS Fargate and Amazon ECS ([video](https://www.youtube.com/watch?v=7FVK0i9edyg), [slides](https://d1.awsstatic.com/events/reinvent/2019/REPEAT_2_Best_practices_for_CICD_using_AWS_Fargate_and_Amazon_ECS_CON333-R2.pdf))
* Amazon CI/CD Practices for Software Development Teams ([video](https://youtu.be/3HKbXz0RwSg), [slides](https://www.slideshare.net/AmazonWebServices/amazon-cicd-practices-for-software-development-teams))
* [AWS re:Invent 2015: DevOps at Amazon: A Look at Our Tools and Processes (DVO202)](https://www.youtube.com/watch?v=esEFaY0FDKc)
* [Best  Practices for CI/CD with AWS Lambda and Amazon API Gateway](https://www.slideshare.net/AmazonWebServices/best-practices-for-cicd-with-aws-lambda-and-amazon-api-gateway-srv355r1-aws-reinvent-2018)
* [Ensuring rollback safety during deployments](https://aws.amazon.com/builders-library/ensuring-rollback-safety-during-deployments/)
* [Building and testing polyglot applications using AWS CodeBuild](https://aws.amazon.com/blogs/devops/building-and-testing-polyglot-applications-using-aws-codebuild/)
* [Deploying GitOps with Weave Flux and Amazon EKS](https://aws.amazon.com/blogs/compute/deploying-gitops-with-weave-flux-and-amazon-eks/)
* [Include CloudFormation templates in the CDK](https://docs.aws.amazon.com/cdk/api/latest/docs/cloudformation-include-readme.html)
* [Validating AWS CodeCommit Pull Requests with AWS CodeBuild and AWS Lambda](https://aws.amazon.com/blogs/devops/validating-aws-codecommit-pull-requests-with-aws-codebuild-and-aws-lambda/)
* [Running end-to-end Cypress tests for your fullstack CI/CD deployment with Amplify Console](https://aws.amazon.com/blogs/mobile/running-end-to-end-cypress-tests-for-your-fullstack-ci-cd-deployment-with-amplify-console/)
* [Test Reports with AWS CodeBuild](https://aws.amazon.com/blogs/devops/test-reports-with-aws-codebuild/)
* [New – Building a Continuous Integration Workflow with Step Functions and AWS CodeBuild](https://aws.amazon.com/blogs/aws/new-building-a-continuous-integration-workflow-with-step-functions-and-aws-codebuild/)
* [Using AWS Step Functions State Machines to Handle Workflow-Driven AWS CodePipeline Actions](https://aws.amazon.com/blogs/devops/using-aws-step-functions-state-machines-to-handle-workflow-driven-aws-codepipeline-actions/)

## Observability

* [AWS X-Ray](https://docs.aws.amazon.com/xray/latest/devguide/aws-xray.html) (see also [Integrating  AWS X-Ray with Other AWS Services](https://docs.aws.amazon.com/xray/latest/devguide/xray-services.html))
* [AWS  X-Ray Now Supports Amazon API Gateway and New Sampling Rules API](https://aws.amazon.com/blogs/aws/apigateway-xray/) (not  a methodology, but an important FYI for observability)
* [Visualize and Monitor Highly Distributed Applications with Amazon CloudWatch ServiceLens](https://aws.amazon.com/blogs/aws/visualize-and-monitor-highly-distributed-applications-with-amazon-cloudwatch-servicelens/)
* [Debugging with Amazon CloudWatch Synthetics and AWS X-Ray](https://aws.amazon.com/blogs/devops/debugging-with-amazon-cloudwatch-synthetics-and-aws-x-ray/)
* [Amazon CloudWatch Now Includes Contributor Insights - in Preview](https://aws.amazon.com/about-aws/whats-new/2019/11/amazon-cloudwatch-now-includes-contributor-insights-preview/)
* [Container monitoring for Amazon ECS, EKS, and Kubernetes is now available in Amazon CloudWatch](https://aws.amazon.com/about-aws/whats-new/2019/08/container-monitoring-for-amazon-ecs-eks-and-kubernetes-is-now-available-in-amazon-cloudwatch/)
* [Using Prometheus Metrics in Amazon CloudWatch](https://aws.amazon.com/blogs/containers/using-prometheus-metrics-in-amazon-cloudwatch/)
* [AWS observability workshop](https://observability.workshop.aws/en/)
* [Building dashboards for operational visibility](https://aws.amazon.com/builders-library/building-dashboards-for-operational-visibility/)
