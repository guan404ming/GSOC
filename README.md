# 2025cloud Docker Project

This project contains two simple containerized applications:

1. Python Flask Application
2. Node.js Express Application

## Project Structure

```bash
2025cloud/
├── .github/
│   └── workflows/
│       └── docker-build.yml
├── python-app/
│   ├── Dockerfile
│   ├── requirements.txt
│   └── app.py
└── node-app/
    ├── Dockerfile
    ├── package.json
    └── app.js
```

## Automated Container Image Generation

### Workflow Overview

Our project uses GitHub Actions to automate the container image generation process. The workflow is triggered in the following scenarios:

1. **Push to Main Branch**
   - When code is pushed directly to the main branch
   - When a pull request is merged into main
   - Generates images with both `latest` and commit SHA tags

2. **Pull Request Creation/Updates**
   - When a new pull request is created
   - When changes are pushed to an existing pull request
   - Only generates images with commit SHA tags (no `latest` tag)

### Tag Design Logic

We use a dual-tagging strategy for our container images:

1. **Latest Tag**
   - Format: `wesley1117/2025cloud:{app-name}-latest`
   - Example: `wesley1117/2025cloud:python-app-latest`
   - Only generated on main branch updates
   - Always points to the most recent stable version
   - Useful for development and testing

2. **Commit SHA Tag**
   - Format: `wesley1117/2025cloud:{app-name}-{commit-sha}`
   - Example: `wesley1117/2025cloud:python-app-a1b2c3d`
   - Generated for all builds (main branch and PRs)
   - Provides immutable references to specific code versions
   - Useful for version control and rollbacks

### Image Generation Process

The automated build process follows these steps:

1. **Trigger Conditions**
   - Code push to main branch
   - Pull request creation/update
   - Manual workflow dispatch

2. **Build Environment**
   - Uses Ubuntu latest runner
   - Sets up Docker Buildx for multi-platform support
   - Authenticates with Docker Hub

3. **Build Steps**
   - Checks out the code
   - Builds Python application image
   - Builds Node.js application image
   - Pushes images with appropriate tags

4. **Failure Handling**
   - Build failures are reported in GitHub Actions
   - Failed builds don't push any images
   - Detailed logs are available in the Actions tab

## Building the Images

### Option 1: Build from Source

#### Python Application Image

```bash
cd 2025cloud/python-app
docker build -t wesley1117/2025cloud:python-app .
```

#### Node.js Application Image

```bash
cd 2025cloud/node-app
docker build -t wesley1117/2025cloud:node-app .
```

### Option 2: Pull from Docker Hub

```bash
docker pull wesley1117/2025cloud:python-app
docker pull wesley1117/2025cloud:node-app
```

## Running the Containers

### Python Application

```bash
# Run the container
docker run -d -p 5000:5000 --name python-app wesley1117/2025cloud:python-app

# Check container status
docker ps

# View container logs
docker logs python-app
```

### Node.js Application

```bash
# Run the container
docker run -d -p 3000:3000 --name node-app wesley1117/2025cloud:node-app

# Check container status
docker ps

# View container logs
docker logs node-app
```

## Accessing the Applications

- Python Flask app will be available at: <http://localhost:5000>
- Node.js Express app will be available at: <http://localhost:3000>

## Stopping the Containers

```bash
docker stop python-app node-app
docker rm python-app node-app
```

## Docker Hub Repository

All images are available on Docker Hub:

- Repository: [wesley1117/2025cloud](https://hub.docker.com/r/wesley1117/2025cloud)
- Tags:
  - python-app-latest
  - python-app-{commit-sha}
  - node-app-latest
  - node-app-{commit-sha} 

```mermaid
graph TD
    A[GitHub Repository] --> B[Trigger Events]
    B --> C[GitHub Actions Workflow]
    C --> D[Build Process]
    D --> E[Docker Hub]

[GitHub Repository]
        │
        ▼
[Trigger Events]
    ┌─────────────┐
    │ Push to Main│
    │    ┌───────┐│
    │    │  PR   ││
    │    │ Merge ││
    │    └───────┘│
    └─────────────┘
        │
        ▼
[GitHub Actions Workflow]
    ┌─────────────────┐
    │ Ubuntu Runner   │
    │ Docker Buildx   │
    │ Docker Hub Auth │
    └─────────────────┘
        │
        ▼
[Build Process]
    ┌─────────────┐    ┌─────────────┐
    │ Python App  │    │ Node.js App │
    │ Build       │    │ Build       │
    └─────────────┘    └─────────────┘
        │                   │
        ▼                   ▼
[Tag Strategy]
    ┌─────────────────────────────────┐
    │ Main Branch:                    │
    │ - latest tag                    │
    │ - commit SHA tag                │
    │                                 │
    │ Pull Request:                   │
    │ - commit SHA tag only           │
    └─────────────────────────────────┘
        │                   │
        ▼                   ▼
[Image Tags]
    ┌─────────────────┐    ┌─────────────────┐
    │ python-app-     │    │ node-app-       │
    │ -latest         │    │ -latest         │
    │ -{commit-sha}   │    │ -{commit-sha}   │
    └─────────────────┘    └─────────────────┘
        │                   │
        ▼                   ▼
[Docker Hub]
    wesley1117/2025cloud 
```
