# Task A — Running an Existing Nginx Image

### 1. Pull the Nginx Image

Download the latest Nginx image from Docker Hub:

```bash
docker pull nginx
```

### 2. Run a Container

Start Nginx in a detached container named **web**, exposing port **8080** on your machine system with service provided at port **80** of the container:

```bash
docker run -d --name web -p 8080:80 nginx
```

### 3. Test the Servert

Verify that Nginx is running:
* Open in browser: `http://localhost:8080`
* Or test via CLI:

```bash
curl http://localhost:8080
```

### 4. Stop the Container

```bash
docker stop web
```

### 5. Remove the Container

```bash
docker rm web
```
