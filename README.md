# OWUI Compose

This repository provides a Docker Compose setup for deploying Open WebUI (OWUI) along with its dependencies.

## Prerequisites

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Setup Instructions

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/trackzero/owui-compose.git
   cd owui-compose


1. Start the Services:

Build and start the services using Docker Compose:

```bash
docker-compose up --build
```
The services will start in the foreground (recommended for first run to see any errors).

After the first run, you can run them in detached mode (and no longer need to use --build):

'''bash
docker-compose up -d



1. Accessing the Application:

Once the services are running, access OWUI by navigating to http://localhost:3000 in your web browser.


1. Configuring stuff

Look at the original project references.

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
