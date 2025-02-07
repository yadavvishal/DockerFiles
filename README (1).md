
# Node.js Application in a Docker Container

This project runs a simple Node.js application inside a Docker container.

## Prerequisites
- Docker installed on your system
- Node.js (for local testing, optional)

## Project Structure
```
.
├── Dockerfile
├── main.js
├── package.json
├── package-lock.json
```

## Setup and Usage

### 1. Build the Docker Image
Run the following command to build the Docker image:
```sh
docker build -t my-node-app .
```

### 2. Run the Container
To run the application inside a container, use:
```sh
docker run -p 8000:8000 my-node-app
```
This binds the container's port `8000` to the host machine's port `8000`.

### 3. Access the Application
Once the container is running, open your browser and visit:
```
http://localhost:8000
```
You should see the following response:
```json
{
  "message": "Hey, I am nodejs in container"
}
```

## Dockerfile Explanation
- Uses `ubuntu` as the base image.
- Updates system packages and installs `curl`.
- Sets up Node.js version 18.
- Copies `package.json`, `package-lock.json`, and `main.js` into the container.
- Installs dependencies using `npm install`.
- Runs `main.js` as the application entry point.

## Stopping the Container
To stop the running container, press `CTRL + C` in the terminal or find and stop the container using:
```sh
docker ps
```
Find the container ID and stop it using:
```sh
docker stop <container_id>
```

## Cleanup
To remove the container and image:
```sh
docker rm <container_id>
docker rmi my-node-app
```

## License
This project is open-source and available for modification and distribution.

