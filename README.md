DevOps-Task-2---Elevate-Labs

CSS Template Deployment using Jenkins, Docker, and Webhooks
This project demonstrates how to deploy a static CSS-based website template to a server using a Docker image and Jenkins pipeline. GitHub Webhooks are configured to trigger automatic deployments on every push.

Tools & Technologies
- Jenkins
- Docker
- GitHub Webhooks
- GitHub (Source Code Management)
- Nginx (as Web Server)

Deployment Process
1. Clone the Repository
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name

Dockerfile
FROM nginx
COPY * /usr/share/nginx/html

Jenkinsfile
pipeline {
    agent any
    stages {
        stage ("Code") {
            steps {
                git 'https://github.com/kompallyvishnuvardhanreddy/DevOps-Task-2---Elevate-Labs.git'
            }
        }
        stage ("Build") {
            steps {
                sh 'docker build -t image1 .'
            }
        }
        stage ("Test") {
            steps {
                echo "HTML site is valid - no automated tests configured."
            }
        }
        stage ("Deploy") {
            steps {
                sh 'docker stop con1 || true'
                sh 'docker rm cont1 || true'
                sh 'docker run -itd --name cont1 -p 1234:80 image1'
                
            }
        } 
    }
}

Configure Jenkins Job
Create a Freestyle or Pipeline job.
Set the GitHub repository URL in SCM.

Configure Webhook on GitHub
Go to Settings > Webhooks in your GitHub repo.
Add a new webhook:
Payload URL: http://3.89.113.22:8080/github-webhook/
Content Type: application/json

Visit: http://3.89.113.22:1234 to see the deployed CSS template.

