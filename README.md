# docker-learning-journey

# Day 2: Docker Images, Volumes, and Networks

## Morning Session: Volumes & Networks ✅

### Volumes
- Learned how volumes persist data outside containers
- Practiced mounting host directories into containers
- Understood live code editing without rebuilds

### Networks
- Created custom Docker networks
- Connected multiple containers
- Tested container-to-container communication

## Evening Session: Custom Images ✅

### Python Flask App
- Built first custom Docker image from scratch
- Learned Dockerfile instructions (FROM, COPY, RUN, CMD)
- Containerized a Python web application
- Practiced image building and container deployment

# Personal Learning Notes Day 2- Python Flask App

## Challenges I Faced

1. **Indentation Errors**: Python is strict about indentation. Had to ensure no leading spaces in app.py.

2. **Emoji Encoding Issues**: Special characters (🐍🐳) caused UTF-8 encoding errors. Solution: Use plain text or HTML entities.

3. **Missing the Dot**: Forgot the `.` at end of `docker build` command. Learned that `.` specifies build context.

4. **Network Issues**: Experienced "no such host" error when downloading base image. Fixed by restarting Docker Desktop.

5. **File Naming**: Had to rename `dockerfile` to `Dockerfile` (capital D matters!).

## What Worked Well

✅ Building the image was straightforward once files were correct
✅ Logs command (`docker logs`) very helpful for debugging
✅ Port mapping concept is clear now
✅ Understanding difference between image and container

## Commands I'll Remember
```bash
# Build image
docker build -t name .

# Run container
docker run -d -p host:container --name name image

# Check logs
docker logs container-name

# Clean up
docker stop container-name
docker rm container-name
```

## Time Spent

- Setup and file creation: 15 minutes
- Troubleshooting issues: 20 minutes
- Successful build and run: 5 minutes
- Total: ~40 minutes

## Next Session Preview