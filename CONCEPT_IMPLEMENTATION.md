# Mini App Hub - Concept Implementation

This document explains the implementation direction of Mini App Hub without exposing the full internal codebase.

## Product Goal

The goal is to create a local application hub for small businesses that need simple internal tools but do not want to deal directly with deployment, Docker commands, server setup, or maintenance.

Mini App Hub is designed as a layer between business users and containerized applications.

Instead of asking the user to manually run Docker commands, configure ports, inspect logs, or troubleshoot containers, the system provides a more structured backend flow that can later be connected to a simple dashboard.

## Core Flow

The intended user flow is:

1. A mini business app is packaged as a Docker image.
2. The business owner or operator selects the app from a local hub.
3. Mini App Hub receives the request through an API.
4. The backend validates the requested app configuration.
5. The backend runs the container locally.
6. The system exposes app status, logs, and basic control actions.
7. A future dashboard displays the app in a business-friendly way.

## MVP Scope

The early MVP focuses on the backend foundation.

The private implementation includes:

- A Node.js / Express / TypeScript backend
- API endpoints for local app execution
- Docker-based container running flow
- Port mapping logic
- Container logs access
- Health check endpoint
- Basic input validation
- Safer process execution practices

## Example Backend Responsibilities

The backend is responsible for turning a business-friendly request into a controlled container action.

Example request concept:

```json
{
  "appName": "mini-crm",
  "image": "example/mini-crm:latest",
  "internalPort": 3000,
  "externalPort": 5050
}
```

Instead of requiring a user to manually understand Docker command syntax, the backend receives structured data, validates it, and executes the required local container flow.

## Security-Aware Direction

A major part of the concept is not only "running Docker from Node.js", but doing it responsibly.

The implementation direction avoids unsafe raw shell execution where possible and prefers structured command execution patterns.

The system should validate:

- Container name
- Image name
- Internal port
- External port
- Allowed actions
- Input shape

Future versions should also add:

- App allowlist
- Safer image source control
- User permissions
- Execution limits
- Logs filtering
- Local network restrictions

## Future Dashboard

A future frontend dashboard could include:

- Installed mini-apps list
- App status: running / stopped / error
- Start / stop / restart buttons
- Logs viewer
- Port display
- Update button
- Environment variable editor
- Business-friendly setup wizard

## Example Use Case

A small business wants a lightweight local dashboard for orders, customers, or internal reporting.

Without Mini App Hub, the setup may require:

- Installing dependencies
- Running terminal commands
- Configuring ports
- Setting environment variables
- Reading logs manually
- Updating the app manually

With Mini App Hub, the goal is to make this process guided, local, and simpler.

## Why This Matters

Small businesses often need software, but not every small internal app justifies a full cloud deployment, DevOps setup, or monthly hosting complexity.

Mini App Hub explores a practical middle ground:

A local, Docker-based app management layer that can make small applications easier to use in real business environments.

## Public Repository Note

This public repository is a concept and portfolio presentation.

The full working implementation is kept private while the idea is still being developed.

This repository is intended to show:

- The problem
- The product direction
- The technical thinking
- The implementation approach
- The business use case
