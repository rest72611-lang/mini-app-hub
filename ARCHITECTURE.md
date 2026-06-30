# Architecture Overview

## High-Level Architecture

Mini App Hub is planned as a local system with three main layers:

```text
User / Dashboard
      |
      v
Mini App Hub Backend API
      |
      v
Local Docker Engine
      |
      v
Containerized Mini Apps
```

## Main Components

### 1. Dashboard Layer

A future UI that allows users to manage mini-apps without technical knowledge.

Possible actions:

- View available apps
- Run an app
- Stop an app
- Restart an app
- View logs
- View app status
- Manage settings

### 2. Backend API Layer

The backend is the control layer.

Responsibilities:

- Receive structured requests
- Validate input
- Trigger container actions
- Read container logs
- Return app status
- Prepare a clean API for the frontend

### 3. Docker Execution Layer

This layer interacts with the local Docker environment.

Responsibilities:

- Pull or run images
- Map ports
- Start containers
- Read logs
- Manage app lifecycle

## MVP API Direction

Possible API structure:

```text
GET  /health
POST /api/apps/run
GET  /api/apps/:name/logs
GET  /api/apps/:name/status
POST /api/apps/:name/stop
POST /api/apps/:name/restart
```

## Design Principle

The core idea is to hide infrastructure complexity behind a simple product experience.

A non-technical user should not need to know the difference between:

- Image
- Container
- Internal port
- External port
- Logs
- Runtime errors

The system should translate those details into simple actions and statuses.
