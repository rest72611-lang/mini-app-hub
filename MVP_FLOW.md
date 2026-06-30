# MVP Flow

The MVP is based on a simple local execution flow:

1. A mini-app is packaged as a Docker image.
2. The user selects or requests to run the app.
3. The backend receives the app configuration.
4. The backend validates the input.
   - If validation fails, the backend returns a clear error and no container is started.
5. The backend starts the Docker container locally.
6. The system maps the required ports.
7. The user can check status and view logs.
8. A future dashboard will make this process visual and business-friendly.

## Example Scenario

A small business wants to run a local internal dashboard.

Instead of manually writing Docker commands, configuring ports, and checking logs from the terminal, Mini App Hub provides a structured API layer that can later be connected to a simple UI.

## Why This Flow Matters

The goal is not only to run containers.

The real goal is to reduce the gap between a useful small business tool and the technical steps required to make it usable.

Mini App Hub explores how Docker-based apps can be managed through a guided product experience instead of manual infrastructure work.
