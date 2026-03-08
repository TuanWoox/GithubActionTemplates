# GitHub Actions Templates

This repository contains reusable GitHub Actions workflow templates and custom actions that can be referenced across my software engineering projects, eliminating the need to write workflows from scratch.

## 📁 Repository Structure

```
.github/
├── workflows/          # Reusable workflow templates
└── actions/           # Custom composite actions (coming soon)
```

## 🔄 Reusable Workflows

### Build .NET

**File:** `.github/workflows/BuildDotnet.yaml`

A reusable workflow for building .NET applications with standard CI steps.

**Inputs:**
- `dotnet_version` (required, string): The .NET SDK version to use (e.g., `8.0.x`)
- `build_context` (required, string): Path to the .csproj or .sln file to build

**Usage Example:**

```yaml
name: CI Build
on:
  push:
    branches: [main]
  pull_request:

jobs:
  build:
    uses: TuanWoox/GithubActionTemplates/.github/workflows/BuildDotnet.yaml@main
    with:
      dotnet_version: '8.0.x'
      build_context: './src/MyProject.sln'
```

## 🎯 Custom Actions

Coming soon...

## 📝 How to Use

### Using Reusable Workflows

1. Reference this repository in your workflow using the `uses` keyword
2. Specify the path to the workflow file
3. Provide required inputs via the `with` parameter

**Syntax:**
```yaml
jobs:
  job-name:
    uses: TuanWoox/GithubActionTemplates/.github/workflows/[WORKFLOW-NAME].yaml@[REF]
    with:
      input-name: value
```

Where:
- `[WORKFLOW-NAME]` is the workflow file name (e.g., `BuildDotnet`)
- `[REF]` is a branch, tag, or commit SHA (e.g., `main`, `v1.0.0`)

### Using Custom Actions

Coming soon...

## 🚀 Contributing

This is a personal template repository. Feel free to fork and customize for your own needs.

## 📄 License

This project is available for personal use.