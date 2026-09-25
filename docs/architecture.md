# Reference Architecture

The platform separates developer intent from environment reconciliation.

1. Developers create or update application code.
2. CI builds, tests and publishes immutable artifacts.
3. Environment configuration is changed through Git.
4. Argo CD reconciles desired state into Kubernetes.
5. Platform policies enforce baseline security and resource expectations.
6. OpenTelemetry exports workload signals to the observability platform.

## Control-plane responsibilities

The platform team owns reusable capabilities such as cluster lifecycle, ingress, identity integration, secrets delivery, policy, observability and golden paths.

Application teams retain ownership of service behavior, SLOs, capacity assumptions and production readiness.
