- [Continuous Integration / Continuous Delivery / Continuous Deployment](#continuous-integration--continuous-delivery--continuous-deployment)
  - [Continuous Integration](#continuous-integration)
  - [Continuous Delivery](#continuous-delivery)
  - [Continuous Deployment](#continuous-deployment)
  - [Going from Continuous Integration to Continuous Deployment](#going-from-continuous-integration-to-continuous-deployment)
- [GitHub Actions](#github-actions)
  - [YAML Ain't Markup Language (YAML)](#yaml-aint-markup-language-yaml)
  - [Workflows](#workflows)
  - [Events](#events)
  - [Jobs](#jobs)
  - [Steps](#steps)
  - [Actions](#actions)
  - [Runners](#runners)
- [Azure Pipelines](#azure-pipelines)
- [Docker](#docker)
- [Kubernetes](#kubernetes)

# Continuous Integration / Continuous Delivery / Continuous Deployment

## Continuous Integration

Developers practicing continuous integration merge their changes back to the main branch as often as possible. The developer's changes are validated by creating a build and running automated tests against the build. By doing so, you avoid integration challenges that can happen when waiting for release day to merge changes into the release branch.

Continuous integration puts a great emphasis on testing automation to check that the application is not broken whenever new commits are integrated into the main branch.

## Continuous Delivery

Continuous delivery is an extension of continuous integration since it automatically deploys all code changes to a testing and/or production environment after the build stage. 

This means that on top of automated testing, you have an automated release process and you can deploy your application any time by clicking a button.

In theory, with continuous delivery, you can decide to release daily, weekly, fortnightly, or whatever suits your business requirements. However, if you truly want to get the benefits of continuous delivery, you should deploy to production as early as possible to make sure that you release small batches that are easy to troubleshoot in case of a problem.

## Continuous Deployment

Continuous deployment goes one step further than continuous delivery. With this practice, every change that passes all stages of your production pipeline is released to your customers. There's no human intervention, and only a failed test will prevent a new change to be deployed to production.

Continuous deployment is an excellent way to accelerate the feedback loop with your customers and take pressure off the team as there isn't a Release Day anymore. Developers can focus on building software, and they see their work go live minutes after they've finished working on it.

![CI/CD](resources/continuous_diagram.jpg)

## Going from Continuous Integration to Continuous Deployment

If you're just getting started on a new project with no users yet, it might be easy for you to deploy every commit to production. You could even start by automating your deployments and release your alpha version to a production with no customers. Then you would ramp up your testing culture and make sure that you increase code coverage as you build your application. By the time you're ready to onboard users, you will have a great continuous deployment process where all new changes are tested before being automatically released to production.

But if you already have an existing application with customers you should slow things down and start with continuous integration and continuous delivery. Start by implementing basic unit tests that get executed automatically, no need to focus yet on having complex end-to-end tests running. Instead, you should try automating your deployments as soon as possible and get a to a stage where deployments to your staging environments are done automatically. The reason is that by having automatic deployments, you will be able to focus your energy on improving your tests rather than having periodically to stop things to coordinate a release.

Once you can start releasing software on a daily basis, you can look into continuous deployment, but make sure that the rest of your organization is ready as well. Documentation, support, QA. These functions will need to adapt to the new cadence of releases, and it is important that they do not miss on significant changes that can impact customers.

# GitHub Actions

GitHub Actions help you automate tasks within your software development life cycle. GitHub Actions are event-driven, meaning that you can run a series of commands after a specified event has occurred. For example, every time someone creates a pull request for a repository, you can automatically run a command that executes a software testing script.

> View the [github-actions-demo.yml](.github/workflows/github-actions-demo.yml) to see an example of a GitHub actions workflow.
> 
> GitHub Actions Documentation: https://docs.github.com/en/actions

## YAML Ain't Markup Language (YAML)

The first thing to know about GitHub actions is that it uses YAML files to define it's workflows. YAML is a serialization language that has steadily increased in popularity over the last few years. It's often used as a format for configuration files, but its object serialization abilities make it a viable replacement for languages like JSON. YAML has broad language support and maps easily into native data structures. It's also easy to for humans to read, which is why it's a good choice for configuration.

> YAML Documentation: https://yaml.org/spec/1.2.2/
> 
> Getting Started: https://www.cloudbees.com/blog/yaml-tutorial-everything-you-need-get-started

##  Workflows

The workflow is an automated procedure that you add to your repository. Workflows are made up of one or more jobs and can be scheduled or triggered by an event. The workflow can be used to build, test, package, release, or deploy a project on GitHub. You can reference a workflow within another workflow.

> View the [dotnet.yml](.github/workflows/dotnet.yml) to see an example of various .NET pipelines for testing, building and deploying.
> 
> GitHub provides workflow templates for various projects at https://github.com/actions/starter-workflows

## Events

An event is a specific activity that triggers a workflow. For example, activity can originate from GitHub when someone pushes a commit to a repository or when an issue or pull request is created. You can also use the repository dispatch webhook to trigger a workflow when an external event occurs.

##  Jobs

A job is a set of steps that execute on the same runner. By default, a workflow with multiple jobs will run those jobs in parallel. You can also configure a workflow to run jobs sequentially. For example, a workflow can have two sequential jobs that build and test code, where the test job is dependent on the status of the build job. If the build job fails, the test job will not run.

## Steps

A step is an individual task that can run commands in a job. A step can be either an action or a shell command. Each step in a job executes on the same runner, allowing the actions in that job to share data with each other.

##  Actions

Actions are standalone commands that are combined into steps to create a job. Actions are the smallest portable building block of a workflow. You can create your own actions, or use actions created by the GitHub community. To use an action in a workflow, you must include it as a step.

> GitHub Marketplace: https://github.com/marketplace?type=actions
> 
> Actions on GitHub Enterprise: https://docs.github.com/en/enterprise-server@2.22/admin/github-actions/managing-access-to-actions-from-githubcom/about-using-actions-in-your-enterprise

##  Runners

A runner is a server that has the GitHub Actions runner application installed. You can use a runner hosted by GitHub, or you can host your own. A runner listens for available jobs, runs one job at a time, and reports the progress, logs, and results back to GitHub. GitHub-hosted runners are based on Ubuntu Linux, Microsoft Windows, and macOS, and each job in a workflow runs in a fresh virtual environment. If you need a different operating system or require a specific hardware configuration, you can host your own runners.

> Self-Hosted Runners: https://docs.github.com/en/actions/hosting-your-own-runners/about-self-hosted-runners

# Azure Pipelines

- https://azure.microsoft.com/en-us/services/devops/pipelines/
- Comparison: https://docs.microsoft.com/en-us/dotnet/architecture/devops-for-aspnet-developers/actions-vs-pipelines

![Azure Removal Note](resources/azure-pipelines-removed-note.png)
 > https://docs.microsoft.com/en-us/azure/devops/pipelines/agents/hosted?view=azure-devops&tabs=yaml#use-a-microsoft-hosted-agent

# Docker

- https://www.docker.com/

# Kubernetes

- https://kubernetes.io/
