# Task B — Custom Static Site Container

### Provided Files

Your custom static site consists of:
* `taskB/files/index.html`
* `taskB/files/Dockerfile`

---

### 1. Build the Image

Navigate into the project folder and build an image named **simple-site**:

```bash
cd taskB/files
docker build -t simple-site .
```

### 2. Run the Container

Start the container (built on Ubuntu as defined in the Dockerfile), exposing port **9090** on your system with service provided at port **8000** of the container:

```bash
docker run -d --name site1 -p 9090:8000 simple-site
```

### 3. Test the Site

Verify the container is serving your static page:

* Browser: `http://localhost:9090`
* CLI:

```bash
curl http://localhost:9090
```

### 4. Stop the Container

```bash
docker stop site1
```

### 5. Remove the Container

```bash
docker rm site1
```

