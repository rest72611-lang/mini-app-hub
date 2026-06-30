# MVP Evidence

This repository does not expose the full private implementation.

However, the private MVP direction includes a backend flow for managing local Docker-based mini-apps through structured API endpoints.

## Publicly Shareable MVP Signals

The concept is based on the following working direction:

- Local backend API for app execution flow
- Docker-based mini-app runtime concept
- Structured request validation
- Health check endpoint direction
- Container logs access direction
- Port mapping and local app access direction
- Future dashboard layer for business-friendly management

## Example API Flow

The private MVP direction is based on a flow similar to:

```text
GET /health
Response: API is running

POST /api/apps/run
Purpose: request local execution of a Docker-based mini-app

GET /api/apps/:name/logs
Purpose: read logs for a running app

GET /api/apps/:name/status
Purpose: check current app status
```

## Example Safe Request Shape

```json
{
  "appName": "mini-crm",
  "image": "example/mini-crm:latest",
  "internalPort": 3000,
  "externalPort": 5050
}
```

This is a safe public example and does not expose the private implementation.

## Why the Full Code Is Private

The full implementation is kept private because this is being treated as an early product initiative, not only as a code sample.

The public repository is intended to show:

- Product thinking
- Architecture direction
- MVP flow
- DevOps-oriented understanding
- The business problem being solved
