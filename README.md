# Simple HAProxy Bridge Docker image

This repository contains a basic Docker image that provides a simple HAProxy-based TCP reverse proxy.

## Usage

Configuration environment variables:

Name | Description | Default
--- | --- | ---
`BACKEND_URL` | URL of the backend server that should receive the incoming TCP requests | *Required*
`TIMEOUT_CONNECT_MS` | See HAProxy `timeout connect` configuration parameter | `5000`
`TIMEOUT_CLIENT_MS` | See HAProxy `timeout client` configuration parameter | `120000`
`TIMEOUT_SERVER_MS` | See HAProxy `timeout server` configuration parameter | `120000`

The reverse proxy listens on port 80 by default.

```
docker run -dP --name=simple_rev_proxy -e BACKEND_URL=my.backend.server:9191 agmangas/simple-haproxy-bridge
```