# GitHub Actions

GitHub Actions help you automate tasks within your software development life cycle. GitHub Actions are event-driven, meaning that you can run a series of commands after a specified event has occurred. For example, every time someone creates a pull request for a repository, you can automatically run a command that executes a software testing script.

> View the [github-actions-demo.yml](.github/workflows/github-actions-demo.yml) to see an example of a GitHub actions workflow.
>
> GitHub Actions Documentation: <https://docs.github.com/en/actions>

## YAML Ain't Markup Language (YAML)

The first thing to know about GitHub actions is that it uses YAML files to define it's workflows. YAML is a serialization language that has steadily increased in popularity over the last few years. It's often used as a format for configuration files, but its object serialization abilities make it a viable replacement for languages like JSON. YAML has broad language support and maps easily into native data structures. It's also easy to for humans to read, which is why it's a good choice for configuration.

> YAML Documentation: <https://yaml.org/spec/1.2.2/>
>
> Getting Started: <https://www.cloudbees.com/blog/yaml-tutorial-everything-you-need-get-started>

## Workflows

The workflow is an automated procedure that you add to your repository. Workflows are made up of one or more jobs and can be scheduled or triggered by an event. The workflow can be used to build, test, package, release, or deploy a project on GitHub. You can reference a workflow within another workflow.

> View the [dotnet.yml](.github/workflows/dotnet.yml) to see an example of various .NET pipelines for testing, building and deploying.
>
> GitHub provides workflow templates for various projects at <https://github.com/actions/starter-workflows>

## Events

An event is a specific activity that triggers a workflow. For example, activity can originate from GitHub when someone pushes a commit to a repository or when an issue or pull request is created. You can also use the repository dispatch webhook to trigger a workflow when an external event occurs.

## Jobs

A job is a set of steps that execute on the same runner. By default, a workflow with multiple jobs will run those jobs in parallel. You can also configure a workflow to run jobs sequentially. For example, a workflow can have two sequential jobs that build and test code, where the test job is dependent on the status of the build job. If the build job fails, the test job will not run.

## Steps

A step is an individual task that can run commands in a job. A step can be either an action or a shell command. Each step in a job executes on the same runner, allowing the actions in that job to share data with each other.

## Actions

Actions are standalone commands that are combined into steps to create a job. Actions are the smallest portable building block of a workflow. You can create your own actions, or use actions created by the GitHub community. To use an action in a workflow, you must include it as a step.

> GitHub Marketplace: <https://github.com/marketplace?type=actions>
>
> Actions on GitHub Enterprise: <https://docs.github.com/en/enterprise-server@2.22/admin/github-actions/managing-access-to-actions-from-githubcom/about-using-actions-in-your-enterprise>

## Runners

A runner is a server that has the GitHub Actions runner application installed. You can use a runner hosted by GitHub, or you can host your own. A runner listens for available jobs, runs one job at a time, and reports the progress, logs, and results back to GitHub. GitHub-hosted runners are based on Ubuntu Linux, Microsoft Windows, and macOS, and each job in a workflow runs in a fresh virtual environment. If you need a different operating system or require a specific hardware configuration, you can host your own runners.

> Self-Hosted Runners: <https://docs.github.com/en/actions/hosting-your-own-runners/about-self-hosted-runners>