# Google Cloud (gcloud) CLI Guide

## Authentication and Project Setup

### 1. Login to Google Cloud
```bash
gcloud auth login
```

This command:

- Opens browser window for authentication
- Allows you to choose Google account
- Saves credentials locally

### 2. Set Project
```bash
gcloud config set project cxo-enablers-fe-internal-demo
```

This sets the default project for all subsequent gcloud commands.

### 3. Clone Cloud Source Repository
```bash
gcloud source repos clone <repo-name>
```

This command:

- Clones the repository locally
- Sets up remote tracking
- Uses project-specific authentication