# Day 2: Volumes and Networks

## What I Learned

### Volumes
- Volumes persist data outside containers
- Changes to volume files appear instantly in containers
- Perfect for development workflows
- Command: `docker run -v $(pwd)/html:/path/in/container`

### Networks
- Custom networks allow container-to-container communication
- Containers can reach each other using container names
- DNS resolution works automatically
- Command: `docker network create my-network`

## Commands Reference

### Volumes
```bash
# Run container with volume
docker run -d -p 8084:80 -v $(pwd)/html:/usr/share/nginx/html --name nginx-volume nginx

# List volumes
docker volume ls
```

### Networks
```bash
# Create network
docker network create my-network

# Run container on network
docker run -d --network my-network --name container1 nginx

# Test connectivity
docker exec container1 curl http://container2
