# Simple HAProxy Bridge Docker image

This repository contains a basic Docker image that provides a simple HAProxy-based TCP reverse proxy.

## Usage

Set the `BACKEND_URL` environment variable to the URL of the backend server that should receive the incoming TCP requests.

The reverse proxy listens on port 80 by default.

```
docker run -dP --name=simple_rev_proxy -e BACKEND_URL=my.backend.server:9191 agmangas/simple-haproxy-bridge
```