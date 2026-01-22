# Docker image for running Node.js commands in an Azure Pipelines container job

<!-- markdownlint-disable MD013 -->
[![License](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](https://github.com/swissgrc/docker-azure-pipelines-node22-net9/blob/main/LICENSE) [![Build](https://img.shields.io/github/actions/workflow/status/swissgrc/docker-azure-pipelines-node22-net9/publish.yml?branch=develop&style=flat-square)](https://github.com/swissgrc/docker-azure-pipelines-node22-net9/actions/workflows/publish.yml) [![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=swissgrc_docker-azure-pipelines-node22-net9&metric=alert_status)](https://sonarcloud.io/summary/new_code?id=swissgrc_docker-azure-pipelines-node22-net9) [![Pulls](https://img.shields.io/docker/pulls/swissgrc/azure-pipelines-node.svg?style=flat-square)](https://hub.docker.com/r/swissgrc/azure-pipelines-node) [![Stars](https://img.shields.io/docker/stars/swissgrc/azure-pipelines-node.svg?style=flat-square)](https://hub.docker.com/r/swissgrc/azure-pipelines-node)
<!-- markdownlint-restore -->

🐳 Docker image to run Node.js commands in [Azure Pipelines container jobs].

## Usage

This image can be used to run Node.js commands in [Azure Pipelines container jobs].

### Azure Pipelines Container Job

To use the image in an Azure Pipelines Container Job, add one of the following example tasks and use it with the `container` property.

The following example shows the container used for a deployment step with a Azure CLI command:

```yaml
  - stage: deploy
    jobs:
      - deployment: runAzureCLI
        container: swissgrc/azure-pipelines-node:latest-22-net9
        environment: smarthotel-dev
        strategy:
          runOnce:
            deploy:
              steps:
                - bash: |
                    node --version
```

## Included Software

- [swissgrc/azure-pipelines-dotnet:9](https://github.com/swissgrc/docker-azure-pipelines-dotnet-9) as base image
- Node.js 22
- Yarn
- pnpm

## Tags

| Tag              | Description                                | Size                                                                                                                                  |
|------------------|--------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| latest-22-net9   | Latest stable release (from `main` branch) | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-node/latest-22-net9?style=flat-square)   |
| unstable-22-net9 | Latest stable release (from `main` branch) | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-node/unstable-22-net9?style=flat-square) |
| x.y.z-net9       | Image for a specific version of Node.js    |                                                                                                                                       |

[Azure Pipelines container jobs]: https://docs.microsoft.com/en-us/azure/devops/pipelines/process/container-phases
