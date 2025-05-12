# CI/CD Demo with Jenkins and GitHub Webhook

This project demonstrates a basic CI/CD pipeline using Jenkins and GitHub Webhooks. It automatically builds and runs an Nginx-based container depending on the pushed Git branch.

## 🧱 Tech Stack

- **Jenkins** – CI/CD orchestration
- **GitHub Webhook** – triggers Jenkins jobs on push events
- **Docker** – containerizes and runs Nginx
- **Nginx** – serves a static HTML page

## 🚀 Features

- Triggered by `git push` to GitHub via webhook
- Uses Jenkins pipeline defined in `Jenkinsfile`
- Branch-based deployment behavior:
  - `main` branch → deploys container to **port 8080**
  - other branches → deploys to **port 8081**
- Displayed content: **"Hi nginx"**

## 📁 Project Structure

```text
├── Dockerfile         # Builds a minimal Nginx container
├── index.html         # Static HTML page displayed by Nginx
├── Jenkinsfile        # Pipeline logic with branch-based deployment
└── README.md



🌐 Exposing Jenkins (if running locally)
To allow GitHub Webhook to reach your local Jenkins, use ngrok:

bash
ngrok http 8080
Then configure your GitHub repository:

Settings > Webhooks > Add webhook

Payload URL: https://<your-ngrok-subdomain>.ngrok.io/github-webhook/

Content Type: application/json

Event Type: Just the push event
```

## 📝 How to Use
Set up Jenkins with Docker support

Add this project as a GitHub repository

Configure a multibranch pipeline in Jenkins

Add a webhook to GitHub (see above)

Push to:

main → visible on http://<your-ip>:8080

other branches → visible on http://<your-ip>:8081
