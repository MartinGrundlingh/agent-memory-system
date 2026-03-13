# Architectural Decisions Template

This file demonstrates the format for logging architectural decisions (ADRs). Use bullet lists for clarity.

Note: The example entries in this template are generic. Adapt examples to match your repository's actual architecture and deployment environment.

## Format

Each decision should include:
- Date and ADR number
- Status (proposed/accepted/superseded)
- Context (why the decision was needed)
- Decision (what was chosen)
- Alternatives considered (optional if specified)
- Consequences (trade-offs, implications)

## Example Entries

### ADR-001: Use Short-Lived CI Authentication (2025-01-10)

**Status:**
- Accepted

**Context:**
- Need secure authentication from CI to a cloud provider and internal services
- Long-lived credentials increase breach risk and operational burden
- Want stronger auditing and automatic rotation

**Decision:**
- Use short-lived, workload-identity style authentication via CI OIDC (or equivalent)
- Avoid committing or distributing long-lived keys

**Alternatives Considered:**
- Long-lived service credentials → Rejected: security risk, manual rotation required
- Per-environment static credentials → Rejected: harder to manage across projects

**Consequences:**
- ✅ More secure (no long-lived credentials)
- ✅ Automatic credential rotation
- ✅ Better audit trail
- ❌ Slightly more complex initial setup
- ❌ Requires CI OIDC (or equivalent) support

### ADR-002: Standardize Database Migrations (2025-01-12)

**Status:**
- Accepted

**Context:**
- Need version control for database schema changes
- Multiple developers working on database schema
- Want to avoid manual SQL scripts and migration conflicts

**Decision:**
- Use a dedicated database migration tool
- Store migrations in version control alongside the application code
- Prefer generated migrations when supported, with manual review

**Alternatives Considered:**
- Raw SQL scripts → Rejected: no versioning, error-prone
- Framework-specific migration tooling → Rejected: reduces portability

**Consequences:**
- ✅ Version-controlled schema changes
- ✅ Reproducible deployments and rollbacks
- ✅ Easy rollback capability
- ❌ Learning curve for team
- ❌ Requires discipline to keep migrations in sync with models

### ADR-003: Use Managed Database Service (2025-01-15)

**Status:**
- Accepted

**Context:**
- Need a relational database with high availability and backups
- Want to reduce operational overhead
- Performance is important for core workloads

**Decision:**
- Use a managed database offering that supports backups and point-in-time recovery
- Prefer the simplest managed option that meets performance and reliability needs

**Alternatives Considered:**
- Self-managed database → Rejected: high operational overhead
- Non-relational store → Rejected: need relational model and SQL

**Consequences:**
- ✅ Managed service (automated backups, HA)
- ❌ Higher cost than self-managed
- ❌ Vendor lock-in considerations

## Tips

- Number decisions sequentially (ADR-001, ADR-002, etc.)
- Always include date for context
- Be honest about trade-offs (use ✅ and ❌)
- Keep alternatives brief but clear
- Update decisions if they're revisited/changed
- Focus on "why" not "how" (implementation details go elsewhere)
