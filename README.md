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
- `dotnet_version` (optional, string, default: `8.0.x`): The .NET SDK version to use (e.g., `8.0.x`, `7.0.x`)
- `build_context` (optional, string, default: `.`): Path to the .csproj or .sln file to build

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

### Build Next.js

**File:** `.github/workflows/BuildNextJS.yaml`

A reusable workflow for building Next.js applications with dependency installation, linting, and build steps.

**Inputs:**
- `node_version` (required, string): The Node.js version to use (e.g., `20.x`, `18.x`)
- `build_context` (optional, string, default: `.`): Path to the Next.js project directory
- `package_manager` (optional, string, default: `npm`): Package manager to use (`npm`, `yarn`, or `pnpm`)

**Usage Example:**

```yaml
name: CI Build
on:
  push:
    branches: [main]
  pull_request:

jobs:
  build:
    uses: TuanWoox/GithubActionTemplates/.github/workflows/BuildNextJS.yaml@main
    with:
      node_version: '20.x'
      build_context: '.'
      package_manager: 'npm'
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