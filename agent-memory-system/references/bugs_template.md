# Bug Log Template

This file demonstrates the format for logging bugs and their solutions. Keep entries brief and chronological.

Note: The example entries in this template are generic. Adapt details to match your repository's actual environment and tooling.

## Format

Each bug entry should include:
- Date (YYYY-MM-DD)
- Brief description of the bug/issue
- Solution or fix applied
- Any prevention notes (optional)

Use bullet lists for simplicity. Older entries can be manually removed when they become irrelevant.

## Example Entries

### 2025-01-15 - Container Architecture Mismatch
- **Issue**: Container failing to start with "exec format error"
- **Root Cause**: Built for a different CPU architecture than the deployment environment
- **Solution**: Built/published a compatible image for the target platform
- **Prevention**: Standardize build platform settings in build scripts and CI

### 2025-01-20 - Scheduled Job HTTPS Requirement
- **Issue**: Scheduled job failing with "URL must use HTTPS"
- **Root Cause**: Target endpoint required HTTPS
- **Solution**: Updated scheduled job configuration to use HTTPS endpoints
- **Prevention**: Validate endpoint requirements when configuring schedulers and webhooks

### 2025-01-22 - Database Connection Pool Exhaustion
- **Issue**: API returning 500 errors under load
- **Root Cause**: Connection pool size too small (default 5)
- **Solution**: Increased pool limits and tuned timeouts based on load testing results
- **Prevention**: Load test critical paths and document safe pool sizing defaults

## Tips

- Keep descriptions under 2-3 lines
- Focus on what was learned, not exhaustive details
- Include enough context for future reference
- Date entries so you know how recent the issue is
- Periodically clean out very old entries (6+ months)
