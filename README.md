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
        container: swissgrc/azure-pipelines-dotnet:7
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
| 7          | Latest stable release (from `main` branch)                                                      | swissgrc/azure-piplines-git:2.45.1 | 7.0.409  | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-dotnet/latest?style=flat-square)     |
| 7-unstable | Latest unstable release (from `develop` branch)                                                 | swissgrc/azure-piplines-git:2.45.2 | 7.0.409  | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-dotnet/unstable?style=flat-square)   |
| 7.0.302    | [.NET SDK 7.0.302](https://github.com/dotnet/core/blob/main/release-notes/7.0/7.0.5/7.0.302.md) | swissgrc/azure-piplines-git:2.39.2 | 7.0.302  | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-dotnet/7.0.302?style=flat-square)    |
| 7.0.304    | [.NET SDK 7.0.304](https://github.com/dotnet/core/blob/main/release-notes/7.0/7.0.7/7.0.7.md)   | swissgrc/azure-piplines-git:2.39.2 | 7.0.304  | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-dotnet/7.0.304?style=flat-square)    |
| 7.0.305    | [.NET SDK 7.0.305](https://github.com/dotnet/core/blob/main/release-notes/7.0/7.0.8/7.0.8.md)   | swissgrc/azure-piplines-git:2.39.2 | 7.0.305  | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-dotnet/7.0.305?style=flat-square)    |
| 7.0.306    | [.NET SDK 7.0.306](https://github.com/dotnet/core/blob/main/release-notes/7.0/7.0.9/7.0.9.md)   | swissgrc/azure-piplines-git:2.39.2 | 7.0.306  | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-dotnet/7.0.306?style=flat-square)    |
| 7.0.400    | [.NET SDK 7.0.400](https://github.com/dotnet/core/blob/main/release-notes/7.0/7.0.10/7.0.10.md) | swissgrc/azure-piplines-git:2.39.2 | 7.0.400  | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-dotnet/7.0.400?style=flat-square)    |
| 7.0.401    | [.NET SDK 7.0.401](https://github.com/dotnet/core/blob/main/release-notes/7.0/7.0.11/7.0.11.md) | swissgrc/azure-piplines-git:2.39.2 | 7.0.401  | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-dotnet/7.0.401?style=flat-square)    |
| 7.0.402    | [.NET SDK 7.0.402](https://github.com/dotnet/core/blob/main/release-notes/7.0/7.0.12/7.0.12.md) | swissgrc/azure-piplines-git:2.39.2 | 7.0.402  | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-dotnet/7.0.402?style=flat-square)    |
| 7.0.403    | [.NET SDK 7.0.403](https://github.com/dotnet/core/blob/main/release-notes/7.0/7.0.13/7.0.13.md) | swissgrc/azure-piplines-git:2.42.0 | 7.0.403  | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-dotnet/7.0.403?style=flat-square)    |
| 7.0.404    | [.NET SDK 7.0.404](https://github.com/dotnet/core/blob/main/release-notes/7.0/7.0.14/7.0.14.md) | swissgrc/azure-piplines-git:2.42.1 | 7.0.404  | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-dotnet/7.0.404?style=flat-square)    |
| 7.0.405    | [.NET SDK 7.0.405](https://github.com/dotnet/core/blob/main/release-notes/7.0/7.0.15/7.0.15.md) | swissgrc/azure-piplines-git:2.43.0 | 7.0.405  | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-dotnet/7.0.405?style=flat-square)    |
| 7.0.406    | [.NET SDK 7.0.406](https://github.com/dotnet/core/blob/main/release-notes/7.0/7.0.16/7.0.16.md) | swissgrc/azure-piplines-git:2.43.1 | 7.0.406  | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-dotnet/7.0.406?style=flat-square)    |
| 7.0.407    | [.NET SDK 7.0.407](https://github.com/dotnet/core/blob/main/release-notes/7.0/7.0.17/7.0.17.md) | swissgrc/azure-piplines-git:2.44.0 | 7.0.407  | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-dotnet/7.0.407?style=flat-square)    |
| 7.0.408    | [.NET SDK 7.0.408](https://github.com/dotnet/core/blob/main/release-notes/7.0/7.0.18/7.0.18.md) | swissgrc/azure-piplines-git:2.44.0 | 7.0.408  | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-dotnet/7.0.408?style=flat-square)    |
| 7.0.409    | [.NET SDK 7.0.409](https://github.com/dotnet/core/blob/main/release-notes/7.0/7.0.19/7.0.19.md) | swissgrc/azure-piplines-git:2.45.1 | 7.0.409  | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-dotnet/7.0.409?style=flat-square)    |

[Azure Pipelines container jobs]: https://docs.microsoft.com/en-us/azure/devops/pipelines/process/container-phases
