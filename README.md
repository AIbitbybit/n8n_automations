# n8n Self-Hosted Docker Installation

This repository contains the Docker configuration files to run n8n workflow automation platform.

## Prerequisites

- Docker and Docker Compose installed on your system

## Getting Started

1. Clone this repository:

   ```
   git clone <your-repository-url>
   cd n8n
   ```

2. Before starting the container, modify the `docker-compose.yml` file:

   - Change the `N8N_ENCRYPTION_KEY` to a secure random string
   - Adjust other environment variables as needed

3. Start n8n:

   ```
   docker-compose up -d
   ```

4. Access n8n in your browser at:

   ```
   http://localhost:5678
   ```

5. To stop n8n:
   ```
   docker-compose down
   ```

## Persistent Data

All n8n data (including workflows, credentials, and SQLite database) is stored in the `./data/.n8n` directory, which is mapped to the container.

## Workflow Management

The `workflows` directory is intended for storing exported workflow JSON files. When you create workflows in n8n:

1. Export your workflows from the n8n UI
2. Save them in the `workflows` directory with descriptive names
3. Commit them to Git to track changes and share with others

This allows you to version control your workflows and share them with your team.

## Updating n8n

To update n8n to the latest version:

```
docker-compose pull
docker-compose down
docker-compose up -d
```

## Backing Up

To backup your n8n instance, simply copy the entire `./data/.n8n` directory.

## Pushing to GitHub

To share your n8n configurations via GitHub:

1. Create a new GitHub repository:

   - Go to https://github.com/new
   - Name your repository and create it

2. Connect your local repository to GitHub:

   ```
   git remote add origin https://github.com/yourusername/your-repo-name.git
   git branch -M main
   git push -u origin main
   ```

3. After making changes to your workflows in n8n, export them to the `workflows` directory and commit them:
   ```
   git add workflows/
   git commit -m "Updated workflows"
   git push
   ```

Remember that the `.gitignore` file is set up to exclude sensitive data like credentials and the database from being pushed to GitHub.
