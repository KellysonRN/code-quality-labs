# Code Quality Labs

![Build](https://github.com/kellysonrn/code-quality-labs/actions/workflows/main.yaml/badge.svg)
![badge](https://img.shields.io/endpoint?url=https://gist.githubusercontent.com/kellysonrn/fed13a1a020191c0cd65c7396adad4e2/raw/code-coverage.json)

## Overview

Learn Time: Experiments with [Coverlet](https://github.com/coverlet-coverage/coverlet) to generate code coverage reports.

## Features

 - C#
 - XUnit
 - GitHub Actions
 - [Coverlet Coverage](https://github.com/coverlet-coverage/coverlet)
 - [ReportGenerator](https://github.com/danielpalme/ReportGenerator)
 - SonarCloud

## Requirements

The project requires [.NET 6.0](https://dotnet.microsoft.com/en-us/download/dotnet/6.0).

## Compatible IDEs

Tested on:

- Visual Studio Code (1.76.2)

## Useful commands

From the terminal/shell/command line tool, use the following commands to build, test and run the API.

- ### Build the project

```shell
dotnet build
```

- ### Run the tests

```shell
# Note: During my experiments ( March, 2023 ) the .NET7 had issues to execute this command.
dotnet test /p:CollectCoverage=true /p:CoverletOutputFormat=cobertura
```

### Code Coverage report

```shell
# Install the ReportGenerator
dotnet tool install -g dotnet-reportgenerator-globaltool
```

```shell
# Generate reports
reportgenerator -reports:"**/**/coverage.cobertura.xml" -targetdir:"coveragereport" -reporttypes:Html
```
