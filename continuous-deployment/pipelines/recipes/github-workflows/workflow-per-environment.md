# GitHub Workflows

A workflow is a configurable automated process made up of one or more jobs where each of these jobs can be an action in GitHub. Currently a YAML file format is supported for defining a workflow in GitHub.

Additional information on GitHub actions and GitHub Workflows in the links posted in the [references](#References) section below. 

## Environments

Environments can be used for different reasons, like some environments are used for development and testing while others are used for production. 

Specific environments are protected to prevent unauthorized users from affecting them, since deployments can be executed by different users with different roles. Thus protected environment ensures safety by only letting users with the required privileges, deploy to an environment.

Continuous deployment pipelines help promote changes through automated testing and deployment cycles, out to staging environments and finally to production. The more detailed and comprehensive a testing pipeline is, there is more confidence that the changes wont introduce issues in your production deployment. Since the change must go through the entire process of being tested and deployed, keeping pipelines and deployment environments fast and dependable is of utmost importance.

To understand more about deployment environments, and their differences, please refer to the link in the [references](#References) section below.

## Workflow Per Environment

The general approach is to have one pipeline, where the code is built, tested and deployed and the artifact is then promoted to the next environment, eventually to be deployed into production. 

There are multiple ways in GitHub that an environment setup can be achieved. The way it can be done is to have one workflow for multiple environments, which does not mean it cannot be done, but the complexity increases as additional processes and jobs are added to a workflow. One way to get around the complexity is to have separate workflows for different environments, making sure that the artifacts from each workflow are independent, as well as, the workflow is small enough to debug any issues seen in any of the workflows.

This also helps to keep the deployments to the environments independent thus reducing the time to deploy and find issues earlier than later in the process. Also sine the environments are independent of each other, any failures in deploying to one environment does not block deployments to other environments.

<!-- An example of initializing workflows to deploy, in an automated way, for each environment can be seen [here](https://github.com/microsoft/github-workflow-initialization) -->

## References

- [GitHub Actions](https://docs.github.com/en/actions)
- [GitHub Workflows](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions)
- [Deployment Environment](https://en.wikipedia.org/wiki/Deployment_environment)