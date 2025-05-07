# OWUI Compose

This repository provides a Docker Compose setup for deploying Open WebUI (OWUI) along with its dependencies.

## Prerequisites

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)
- NVIDIA GPU

## Setup Instructions

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/trackzero/owui-compose.git
   cd owui-compose
   ```

2. **Ensure Required Named Volumes Exist**:

   This project uses **external named volumes** for `ollama` and `open-webui`. If you haven't created them yet, run:

   ```bash
   docker volume create ollama
   docker volume create open-webui
   ```

   If you're already running ollama and open-webui containers from the original OWUI setup, you can re-mount them by verifying their names and using the `external: true` tag.

   I....I've said this before and right here it bears repeating: I don't know what I'm doing a lot of the time and I take a lot of shortcuts, but stuff seems to work.  You've heard of vibe-coding?  Imagine that, but the vibe is bourbon.

3. **Start the Services**:

   Build and start the services using Docker Compose:

   ```bash
   docker-compose up --build
   ```

   The services will start in the foreground (recommended for the first run to catch any errors, and yes I know there are better ways).

   After the first successful run, you can start them in detached mode (and skip `--build` unless you've changed the Dockerfile):

   ```bash
   docker-compose up -d
   ```

4. **Accessing the Application**:

   Once the services are running, access OWUI by navigating to:

   ```
   http://localhost:3000
   ```

5. **Configuring Stuff**:

   Look at the original project references below for usage, configuration, and customization options of the various components.  For mcpo, you'll find the config file in ./mcpo-config/config.json. It's a bind mount so it's easier to edit.  It currently only contains a time mcp.

6. **Updating**:
   `docker compose pull` to update.
---

## 🔗 Project References

### 🧠 Open WebUI
> A user-friendly interface for interacting with LLMs (like those exposed by Ollama).
- GitHub: [https://github.com/open-webui/open-webui](https://github.com/open-webui/open-webui)
- Container: `ghcr.io/open-webui/open-webui`

---

### 🧠 Ollama
> Run large language models locally using a simple API and GPU acceleration.
- Website: [https://ollama.com](https://ollama.com)
- GitHub: [https://github.com/ollama/ollama](https://github.com/ollama/ollama)
- Docker Hub: [https://hub.docker.com/r/ollama/ollama](https://hub.docker.com/r/ollama/ollama)

---

### 🧪 MCPO
> A modular control plane for running local tools with `uvx`.
- GitHub: [https://github.com/open-webui/mcpo](https://github.com/open-webui/mcpo)

---

### 🐍 uvx
> A Python tool used to launch and manage the mcpo-based services.
- Docs: [https://docs.astral.sh/uv/guides/tools/](https://docs.astral.sh/uv/guides/tools/)  
  *(Note: uvx is separate from [uv](https://github.com/astral-sh/uv), but mentioned in the same doc tree.)*

---

### 🐳 Docker Compose
> Used to define and run multi-container Docker applications.
- Docs: [https://docs.docker.com/compose/](https://docs.docker.com/compose/)

---

### 🌐 Traefik (Optional, not currently included)
> A modern reverse proxy and load balancer for containers.
- Website: [https://traefik.io](https://traefik.io)
- GitHub: [https://github.com/traefik/traefik](https://github.com/traefik/traefik)
