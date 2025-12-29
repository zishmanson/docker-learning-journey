# Day 1: Docker Basics
    1. Run nginx web server:
   docker run -d -p 8080:80 --name my-nginx nginx
    2. Open browser: http://localhost:8080 (you'll see nginx welcome page!)
    3. Understand what happened: 
        ○ -d = run in background
        ○ -p 8080:80 = map port 8080 on your machine to port 80 in container
        ○ --name = give it a friendly name
        ○ nginx = the image to use
    4. Basic commands to practice:
   docker ps                    # See running containers
   docker ps -a                 # See all containers
   docker stop my-nginx         # Stop the container
   docker start my-nginx        # Start it again
   docker logs my-nginx         # See container logs
   docker rm my-nginx           # Remove container (must stop first)
