# Ride Sharing App

Ride Sharing App is a Go microservices backend for an Uber-style system. It is structured as a distributed application rather than a single API: services communicate over gRPC and RabbitMQ, real-time flows use WebSockets, and the local platform tooling is built around Docker, Tilt, and Kubernetes.

## What It Shows

- service decomposition across gateway, trip, driver, and payment domains
- gRPC and protobuf contracts between services
- RabbitMQ-backed event flow
- WebSocket support for real-time updates
- Kubernetes-oriented local and production deployment paths
- shared infrastructure and contracts across multiple services

## Main Structure

- `services/` contains the backend services
- `proto/` contains protobuf contracts
- `shared/` contains cross-service helpers and shared code
- `infra/` contains deployment and platform material
- `web/` contains the frontend client
- `docs/` and `assets/` contain supporting documentation and visuals

## Architecture Notes

The project is designed to exercise the hard parts of distributed backend work:

- service boundaries instead of a monolith
- asynchronous communication instead of only direct request-response flows
- real-time communication paths alongside backend services
- deployment and observability concerns as part of the system, not afterthoughts

The trip service, for example, already follows a layered structure with domain, service, infrastructure, gRPC, repository, and event-handling concerns separated in code.

## Local Development

### Prerequisites

- Go
- Docker
- Tilt
- a local Kubernetes cluster such as Minikube or Docker Desktop Kubernetes

### Run

```bash
tilt up
```

### Monitor

```bash
kubectl get pods
```

## Why This Repo Exists

This repo exists as a stronger public proof point for backend and distributed-systems work than a generic learning archive. The goal is to show concrete system design, service interaction, messaging, deployment structure, and Go implementation in one place.
