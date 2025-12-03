# CODACY_API_TOKEN

This repository includes a GitHub Actions workflow that integrates with Codacy for automated code quality analysis.

## Setup Instructions

To enable the Codacy integration, you need to configure the `CODACY_API_TOKEN` secret:

1. In your repository, go to **Settings** > **Secrets and variables** > **Actions**
2. Click **"New repository secret"**
3. Name it `CODACY_API_TOKEN`
4. Paste your Codacy project or account API token as the value
5. Save the secret

The workflow is configured to automatically consume this secret:

```yaml
env:
  CODACY_API_TOKEN: ${{ secrets.CODACY_API_TOKEN }}
```

## Workflow Details

The workflow runs on:
- Push events to `main` or `master` branches
- Pull requests targeting `main` or `master` branches

It performs Codacy security analysis and uploads results to GitHub Code Scanning.