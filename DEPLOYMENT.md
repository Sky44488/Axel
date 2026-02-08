# Deployment Guide

This document provides detailed instructions for deploying the Axel project in various environments.

## Vercel Frontend

1. Sign up or log in to your Vercel account.
2. Click on 'New Project' and import your GitHub repository.
3. Configure the Vercel settings:
   - Set environment variables as needed.
   - Choose the correct framework (e.g., Next.js, React).
4. Click 'Deploy' and wait for the build process to complete.

## Heroku Backend

1. Sign up or log in to your Heroku account.
2. Create a new app in the Heroku dashboard.
3. Connect your GitHub repository to the Heroku app.
4. Set up necessary environment variables in the 'Settings' tab.
5. Enable automatic deploys or deploy manually from the 'Deploy' tab.

## AWS Deployment

1. Log in to your AWS Management Console.
2. Choose a service for hosting (e.g., EC2, Elastic Beanstalk).
3. Configure your service:
   - For EC2, launch an instance and deploy your backend service.
   - For Elastic Beanstalk, upload your application and manage environment settings.
4. Set up any necessary security groups and IAM roles for your application.

## Docker Deployment

1. Ensure Docker is installed on your machine.
2. Create a Dockerfile in the root of your project with your application setup.
3. Build your Docker image:
   ```bash
   docker build -t my-application .
   ```
4. Run your Docker container:
   ```bash
   docker run -p 3000:3000 my-application
   ```

## GitHub Actions Secrets Configuration

1. In your GitHub repository, go to `Settings` > `Secrets and variables` > `Actions`.
2. Click `New repository secret` to add any secrets your actions need (e.g., API keys, tokens).
3. Reference these secrets in your GitHub Actions workflow file using the `secrets` context:
   ```yaml
   env:
     MY_SECRET: ${{ secrets.MY_SECRET }}
   ```

