# SonarCloud Security Scan GitHub Action

This GitHub Action performs a security scan using SonarCloud to analyze your code for vulnerabilities and code quality issues.

## Inputs

- `github_token` (required): Token for GitHub repository access.
- `sonar_token` (required): Token for SonarCloud access.

## How It Works

1. **SonarCloud Scan**: The action uses the `SonarSource/sonarcloud-github-action@master` action to perform a security scan. It requires the `GITHUB_TOKEN` to get PR information and the `SONAR_TOKEN` to access SonarCloud.