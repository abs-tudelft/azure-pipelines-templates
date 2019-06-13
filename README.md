# azure-pipelines-templates

This is a collection of [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) [templates](https://docs.microsoft.com/azure/devops/pipelines/process/templates) used and maintained by the [Accelerated Big Data Systems group](https://github.com/abs-tudelft).

## Templates

## Usage

Add a `Github` service connection to your project (Project settings > Service connections > New service connection) and name it `github`.

Add this repository as resource to your `azure-pipelines.yml`.

```yaml
resources:
  repositories:
  - repository: abs-tudelft
    type: github
    endpoint: github
    name: abs-tudelft/azure-pipelines-templates
```

Include job or step templates using the `@abs-tudelft` suffix.

```yaml
jobs:
- template: jobs/some-job-template.yml@abs-tudelft

- job: Linux
  pool:
    vmImage: 'ubuntu-16.04'
  steps:
  - template: steps/some-step-template.hml@abs-tudelft
```
