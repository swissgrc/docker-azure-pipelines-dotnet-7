# Docker image for running .NET 7 in an Azure Pipelines container job

<!-- markdownlint-disable MD013 -->
[![License](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](https://github.com/swissgrc/docker-azure-pipelines-dotnet-7/blob/main/LICENSE) [![Build](https://img.shields.io/github/actions/workflow/status/swissgrc/docker-azure-pipelines-dotnet-7/publish.yml?branch=develop&style=flat-square)](https://github.com/swissgrc/docker-azure-pipelines-dotnet-7/actions/workflows/publish.yml) [![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=swissgrc_docker-azure-pipelines-dotnet-7&metric=alert_status)](https://sonarcloud.io/summary/new_code?id=swissgrc_docker-azure-pipelines-dotnet-7) [![Pulls](https://img.shields.io/docker/pulls/swissgrc/azure-pipelines-dotnet.svg?style=flat-square)](https://hub.docker.com/r/swissgrc/azure-pipelines-dotnet) [![Stars](https://img.shields.io/docker/stars/swissgrc/azure-pipelines-dotnet.svg?style=flat-square)](https://hub.docker.com/r/swissgrc/azure-pipelines-dotnet)
<!-- markdownlint-restore -->

🐳 Docker image to run .NET 7 in [Azure Pipelines container jobs].
The image contains also Docker CLI to access Docker engine on the agent.

## Usage

This image can be used to run .NET 7 in [Azure Pipelines container jobs].

### Azure Pipelines Container Job

To use the image in an Azure Pipelines Container Job, add one of the following example tasks and use it with the `container` property.

The following example shows the container used for a deployment step which shows .NET version:

```yaml
  - stage: deploy
    jobs:
      - deployment: runDotNet
        container: swissgrc/azure-pipelines-dotnet:latest
        environment: smarthotel-dev
        strategy:
          runOnce:
            deploy:
              steps:
                - bash: |
                    dotnet --version
```

### Tags

| Tag        | Description                                     | Base Image                         | .NET SDK | Size                                                                                                                            |
|------------|-------------------------------------------------|------------------------------------|----------|---------------------------------------------------------------------------------------------------------------------------------|
| 7-unstable | Latest unstable release (from `develop` branch) | swissgrc/azure-piplines-git:2.39.2 | 7.0.302  | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-dotnet/unstable?style=flat-square) |

[Azure Pipelines container jobs]: https://docs.microsoft.com/en-us/azure/devops/pipelines/process/container-phases
