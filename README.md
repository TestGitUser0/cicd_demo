# CI/CD Demo with Jenkins and GitHub Webhook

This repository demonstrates a basic CI/CD pipeline setup using Jenkins and GitHub Webhooks. When code is pushed to GitHub, Jenkins is automatically triggered to execute the pipeline defined in the `Jenkinsfile`.

## Tech Stack

- Jenkins
- GitHub
- GitHub Webhook
- Docker (optional)

## How It Works

1. You push code to this GitHub repo
2. GitHub Webhook notifies Jenkins
3. Jenkins pulls the latest code and runs the pipeline

## Setting up Jenkins Integration

- Expose Jenkins using `ngrok http 8080`
- Add a Webhook in GitHub:
  - Payload URL: `https://<your-ngrok>.ngrok.io/github-webhook/`
  - Content type: `application/json`
- Enable `GitHub hook trigger` in Jenkins job configuration
