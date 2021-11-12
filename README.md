# CI-CD_Demo

- [CI-CD_Demo](#ci-cd_demo)
  - [Continuous Integration / Continuous Delivery / Continuous Deployment](#continuous-integration--continuous-delivery--continuous-deployment)
    - [Continuous Integration](#continuous-integration)
    - [Continuous Delivery](#continuous-delivery)
    - [Continuous Deployment](#continuous-deployment)
    - [Going from Continuous Integration to Continuous Deployment](#going-from-continuous-integration-to-continuous-deployment)
  - [Tools & Frameworks](#tools--frameworks)

## Continuous Integration / Continuous Delivery / Continuous Deployment

### Continuous Integration

Developers practicing continuous integration merge their changes back to the main branch as often as possible. The developer's changes are validated by creating a build and running automated tests against the build. By doing so, you avoid integration challenges that can happen when waiting for release day to merge changes into the release branch.

Continuous integration puts a great emphasis on testing automation to check that the application is not broken whenever new commits are integrated into the main branch.

### Continuous Delivery

Continuous delivery is an extension of continuous integration since it automatically deploys all code changes to a testing and/or production environment after the build stage.

This means that on top of automated testing, you have an automated release process and you can deploy your application any time by clicking a button.

In theory, with continuous delivery, you can decide to release daily, weekly, fortnightly, or whatever suits your business requirements. However, if you truly want to get the benefits of continuous delivery, you should deploy to production as early as possible to make sure that you release small batches that are easy to troubleshoot in case of a problem.

### Continuous Deployment

Continuous deployment goes one step further than continuous delivery. With this practice, every change that passes all stages of your production pipeline is released to your customers. There's no human intervention, and only a failed test will prevent a new change to be deployed to production.

Continuous deployment is an excellent way to accelerate the feedback loop with your customers and take pressure off the team as there isn't a Release Day anymore. Developers can focus on building software, and they see their work go live minutes after they've finished working on it.

![CI/CD](resources/continuous_diagram.jpg)

### Going from Continuous Integration to Continuous Deployment

If you're just getting started on a new project with no users yet, it might be easy for you to deploy every commit to production. You could even start by automating your deployments and release your alpha version to a production with no customers. Then you would ramp up your testing culture and make sure that you increase code coverage as you build your application. By the time you're ready to onboard users, you will have a great continuous deployment process where all new changes are tested before being automatically released to production.

But if you already have an existing application with customers you should slow things down and start with continuous integration and continuous delivery. Start by implementing basic unit tests that get executed automatically, no need to focus yet on having complex end-to-end tests running. Instead, you should try automating your deployments as soon as possible and get a to a stage where deployments to your staging environments are done automatically. The reason is that by having automatic deployments, you will be able to focus your energy on improving your tests rather than having periodically to stop things to coordinate a release.

Once you can start releasing software on a daily basis, you can look into continuous deployment, but make sure that the rest of your organization is ready as well. Documentation, support, QA. These functions will need to adapt to the new cadence of releases, and it is important that they do not miss on significant changes that can impact customers.

## Tools & Frameworks

- [GitHub Actions](resources/GitHubActions.md)
- [Docker](resources/Docker.md)
- [Azure Pipelines](resources/AzurePipelines.md)
- [Kubernetes](resources/Kubernetes.md)
