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

| Tag        | Description                                                                                     | Base Image                         | .NET SDK | Size                                                                                                                              |
|------------|-------------------------------------------------------------------------------------------------|------------------------------------|----------|-----------------------------------------------------------------------------------------------------------------------------------|
| latest     | Latest stable release (from `main` branch)                                                      | swissgrc/azure-piplines-git:2.39.2 | 7.0.306  | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-dotnet/latest?style=flat-square)     |
| 7          | Identical to `latest` tag                                                                       |                                    |          | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-dotnet/7?style=flat-square)          |
| unstable   | Latest unstable release (from `develop` branch)                                                 | swissgrc/azure-piplines-git:2.39.2 | 7.0.400  | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-dotnet/unstable?style=flat-square)   |
| 7-unstable | Identical to `unstable` tag                                                                     |                                    |          | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-dotnet/7-unstable?style=flat-square) |
| 7.0.302    | [.NET SDK 7.0.302](https://github.com/dotnet/core/blob/main/release-notes/7.0/7.0.5/7.0.302.md) | swissgrc/azure-piplines-git:2.39.2 | 7.0.302  | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-dotnet/7.0.302?style=flat-square)    |
| 7.0.304    | [.NET SDK 7.0.304](https://github.com/dotnet/core/blob/main/release-notes/7.0/7.0.7/7.0.7.md)   | swissgrc/azure-piplines-git:2.39.2 | 7.0.304  | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-dotnet/7.0.304?style=flat-square)    |
| 7.0.305    | [.NET SDK 7.0.305](https://github.com/dotnet/core/blob/main/release-notes/7.0/7.0.8/7.0.8.md)   | swissgrc/azure-piplines-git:2.39.2 | 7.0.305  | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-dotnet/7.0.305?style=flat-square)    |
| 7.0.306    | [.NET SDK 7.0.306](https://github.com/dotnet/core/blob/main/release-notes/7.0/7.0.9/7.0.9.md)   | swissgrc/azure-piplines-git:2.39.2 | 7.0.306  | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-dotnet/7.0.306?style=flat-square)    |

[Azure Pipelines container jobs]: https://docs.microsoft.com/en-us/azure/devops/pipelines/process/container-phases
