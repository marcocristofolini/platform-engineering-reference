# ADR-001: GitOps pull-based reconciliation

**Status:** Accepted

## Context

Direct deployment credentials in CI increase credential scope and couple delivery systems to cluster access.

## Decision

Environment state is reconciled from Git by an in-cluster GitOps controller.

## Consequences

### Positive
- reduced CI access to clusters;
- auditable desired-state history;
- drift detection;
- consistent rollback model.

### Trade-offs
- reconciliation introduces another control plane;
- teams must understand eventual consistency;
- emergency changes need an explicit break-glass and reconciliation strategy.
