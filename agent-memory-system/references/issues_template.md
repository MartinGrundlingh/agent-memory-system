# Issues/Work Log Template

This file demonstrates the format for logging work completed on tickets. Keep it simple - just enough to remember what was done. Full details live in your ticket system.

Note: The example entries in this template are generic. Adapt ticket systems, services, and technical details to match your repository and organization.

## Format

Each entry should include:
- Date (YYYY-MM-DD)
- Ticket ID (optional)
- Brief description (1-2 lines)
- URL to ticket (if available)
- Status (optional: completed, in-progress, blocked)
- Notes (brief technical context; keep short and link to the ticket/PR for details)

Use bullet lists for simplicity. This is NOT a replacement for your ticket system - it's a quick reference log.

## Example Entries

### 2025-01-15 - TICKET-123: Implement Core API Endpoint
- **Status**: Completed
- **Description**: Added API endpoints with validation and error handling
- **URL**: https://tracker.example.com/TICKET-123
- **Notes**: Added unit tests, coverage at 85%

### 2025-01-16 - TICKET-124: Fix Build/Deploy Issues
- **Status**: Completed
- **Description**: Fixed a deployment configuration mismatch
- **URL**: https://tracker.example.com/TICKET-124
- **Notes**: See bugs.md for details on the fix

### 2025-01-18 - TICKET-125: Database Migration
- **Status**: Completed
- **Description**: Migrated to a new database instance and updated infrastructure configuration
- **URL**: https://tracker.example.com/TICKET-125
- **Notes**: Multi-phase migration completed over 3 days

### 2025-01-20 - TICKET-126: Add Authentication
- **Status**: In Progress
- **Description**: Implementing an authentication flow with an external identity provider
- **URL**: https://tracker.example.com/TICKET-126
- **Notes**: Backend complete, frontend integration pending

### 2025-01-22 - TICKET-130: Performance Optimization
- **Status**: Blocked
- **Description**: Optimize slow queries in contact search endpoint
- **URL**: https://tracker.example.com/TICKET-130
- **Notes**: Waiting for review of proposed indexes

## Alternative Format (Grouped by Week)

### Week of 2025-01-15

**Completed:**
- TICKET-123: Core API endpoint → https://tracker.example.com/TICKET-123
- TICKET-124: Build/deploy fix → https://tracker.example.com/TICKET-124

**In Progress:**
- TICKET-125: Database migration (phase 2 of 3)

### Week of 2025-01-22

**Completed:**
- TICKET-125: Database migration completed → https://tracker.example.com/TICKET-125
- TICKET-126: Authentication backend done → https://tracker.example.com/TICKET-126

**Blocked:**
- TICKET-130: Query optimization (waiting on review) → https://tracker.example.com/TICKET-130

## Tips

- Keep descriptions brief (1-2 lines max)
- Always include ticket URL for easy reference
- Update status if work gets blocked or resumed
- Optional: Group by week or sprint for better organization
- Don't duplicate ticket details - link to source of truth
- Clean out very old entries periodically (3+ months)
- Include multiple ticket sources as appropriate
