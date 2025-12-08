
# **Interactive Task - I: Assignment**

**Introduction:**
This assignment builds on the Docker concepts you have learned so far through [taskA](../taskA/) and [taskB](../taskB/): running existing images, building custom static site containers, and working with multiple containers. You will apply these skills to create and manage Dockerized web applications, explore container networking, and handle multiple container versions.

**Submission Guidelines:**
All submissions must follow this folder structure within your GitHub repository:

```
iAssgn1/
├── assignment-1/
└── assignment-2/
```

Each folder should contain:

* All relevant Dockerfiles, scripts, and HTML files.
* A clear `README.md` with instructions, commands used, and a brief explanation of your approach.
* Screenshots or curl outputs *(optional but recommended)* showing your containers running and accessible.

Ensure your repository is **public** and that your submission is complete and understandable for evaluation.

---

## **Assignment 1 — Build & Run a Personalized Web Server Container**

**Goal:** Create your own Dockerized static website and run it using custom ports.

### Requirements:

1. Create a simple `index.html` with your name, a heading, and a short description.
2. Write a Dockerfile that serves the page using **Nginx or Apache**.
3. Build an image named:

   ```bash
   yourname-site
   ```
4. Run the container so it’s accessible on port **7070** on the host.
5. Test using a browser and `curl`.
6. Stop and remove the container after testing.

---

## **Assignment 2 — Create & Run Two Containers That Communicate**

**Goal:** Deploy two containers — one static web server and one simple API — and connect them using Docker networking.

### Requirements:

1. Create a custom Docker network:

   ```bash
   docker network create webnet
   ```
2. Run an Nginx container on that network (port exposed to host).
3. Create a **simple API container** (e.g., using a prebuilt image like `hashicorp/http-echo`):

   ```bash
   docker run -d --name api --network webnet hashicorp/http-echo -text="Hello from API"
   ```
4. Update your Nginx static page to include a button or link that fetches `/api` from the API container.
5. Test that the web container can reach the API container using container name:

   ```bash
   http://api:5678
   ```
6. Demonstrate connectivity using `curl` inside the web container:

   ```bash
   docker exec -it web curl http://api:5678
   ```

