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

## Updating n8n

To update n8n to the latest version:

```
docker-compose pull
docker-compose down
docker-compose up -d
```

## Backing Up

To backup your n8n instance, simply copy the entire `./data/.n8n` directory.
