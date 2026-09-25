# Platform Engineering Reference

A reference architecture for a Kubernetes-based internal platform using **GitOps, self-service and observable-by-default workloads**.

## Architecture

```mermaid
flowchart LR
    DEV[Developer] --> PORTAL[Backstage]
    PORTAL --> GIT[Service Repository]
    GIT --> CI[CI]
    CI --> REG[Artifact Registry]
    GIT --> ENV[Environment Config]
    ENV --> ARGO[Argo CD]
    ARGO --> K8S[Kubernetes Platform]
    K8S --> APPS[Workloads]
    K8S --> OTEL[OpenTelemetry]
    OTEL --> OBS[Metrics Logs Traces]
```

## Principles

- Git is the desired-state source of truth.
- Platform APIs expose paved roads without hiding infrastructure reality.
- Self-service should reduce cognitive load, not remove ownership.
- Workloads are observable by default.
- Security and policy are platform capabilities.
- Production readiness is part of the delivery path.

## Repository layout

```text
backstage/       example catalog entity
gitops/          Argo CD ApplicationSet example
platform/base/   baseline Kubernetes resources
platform/overlays/
docs/            architecture and ADRs
```

The manifests are intentionally small so architectural choices remain easy to inspect.
