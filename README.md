# 2025cloud Docker Project

This project contains two simple containerized applications:

1. Python Flask Application
2. Node.js Express Application

## Project Structure

```bash
2025cloud/
├── python-app/
│   ├── Dockerfile
│   ├── requirements.txt
│   └── app.py
└── node-app/
    ├── Dockerfile
    ├── package.json
    └── app.js
```

## Building the Images

### Option 1: Build from Source

#### Python Image

```bash
cd python-app
docker build -t wesley1117/2025cloud:python-app .
```

#### Node.js Image

```bash
cd node-app
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
  - python-app
  - node-app 
