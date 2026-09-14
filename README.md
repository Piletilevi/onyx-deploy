# onyx-deploy

Komodo source for the company Hetzner Onyx stack.

Runtime compose is the patched install.sh layout (`deployment/docker-compose.yml`), not a raw `onyx-dot-app/onyx` checkout. Local patches vs upstream `v4.5.2`: MCP server enabled, NVIDIA device reservations on both model servers, LiteLLM-style loopback bind on `:3000`.

Secrets stay in Komodo stack environment. Do not commit `.env`.

```
Komodo stack onyx
  repo: Piletilevi/onyx-deploy
  branch: main
  run_directory: deployment
  file_paths: docker-compose.yml
  project_name: onyx
  IMAGE_TAG: v4.5.2
```

`docker-compose.onyx-mcp-tunnel.yml` is the WRK-304 MCP tunnel. Separate Compose project `onyx-mcp-tunnel`.
