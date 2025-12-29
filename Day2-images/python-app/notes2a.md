# Python Flask App in Docker

A simple Flask web application containerized with Docker.

## Project Structure
```
python-app/
├── Dockerfile          # Instructions to build the Docker image
├── app.py             # Flask application code
├── requirements.txt   # Python dependencies
└── README.md          # This file
```

## What I Learned

### Building Custom Docker Images
- Created a `Dockerfile` with multiple layers
- Used `FROM` to specify base image (python:3.9-slim)
- Used `WORKDIR` to set working directory
- Used `COPY` to add files to the image
- Used `RUN` to execute commands during build
- Used `CMD` to specify the container startup command

### Python in Docker
- Installed dependencies with pip inside the container
- Made Flask accessible from outside the container with `host='0.0.0.0'`
- Mapped container port to host port with `-p 5000:5000`

### Docker Commands Used

#### Build the Image
```bash
docker build -t python-flask-app .
```
- `-t python-flask-app` = Tag/name the image
- `.` = Use current directory as build context

#### Run the Container
```bash
docker run -d -p 5000:5000 --name flask-app python-flask-app
```
- `-d` = Run in detached/background mode
- `-p 5000:5000` = Map port 5000 on host to port 5000 in container
- `--name flask-app` = Give container a friendly name

#### Check Container Logs
```bash
docker logs flask-app
```

#### Stop and Remove Container
```bash
docker stop flask-app
docker rm flask-app
```

## How to Run

### Prerequisites
- Docker Desktop installed and running
- Internet connection (to download base images)

### Steps

1. **Build the Docker image:**
```bash
   docker build -t python-flask-app .
```

2. **Run the container:**
```bash
   docker run -d -p 5000:5000 --name flask-app python-flask-app
```

3. **Access the application:**
   - Open browser: http://localhost:5000
   - You should see: "Hello from Python in Docker!"

4. **Check logs (optional):**
```bash
   docker logs flask-app
```

5. **Stop the container:**
```bash
   docker stop flask-app
   docker rm flask-app
```

## Dockerfile Explanation
```dockerfile
FROM python:3.9-slim
# Start with Python 3.9 slim base image (smaller size)

WORKDIR /app
# Set /app as the working directory inside container

COPY requirements.txt .
# Copy requirements.txt to /app in container

RUN pip install -r requirements.txt
# Install Python dependencies during build

COPY app.py .
# Copy application code to /app in container

EXPOSE 5000
# Document that container listens on port 5000

CMD ["python", "app.py"]
# Command to run when container starts


