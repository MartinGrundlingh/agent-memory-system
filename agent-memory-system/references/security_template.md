# Security Fix Log Template

This file demonstrates the format for logging security vulnerabilities and their fixes. Keep entries brief and chronological.

Note: The example entries in this template are generic. Adapt sources/tools and remediation steps to match your repository's security tooling and workflows.

## Format

Each security fix entry should include:
- Date (YYYY-MM-DD)
- Vulnerability Type (e.g., XSS, SQL Injection, Dependency Vulnerability)
- Tool/Source (e.g., dependency scanner, SAST tool, DAST tool, manual review)
- Brief description of the issue
- Solution or fix applied
- Prevention notes (how to avoid in future)

## Example Entries

### 2025-02-15 - SQL Injection in Login
- **Vulnerability**: SQL Injection (High Severity)
- **Source**: Static analysis tool
- **Issue**: User input directly concatenated into an SQL query
- **Solution**: Switched to parameterized queries
- **Prevention**: Always use parameterized queries; run SAST before merge

### 2025-02-20 - Outdated Dependency
- **Vulnerability**: Prototype Pollution (Critical)
- **Source**: Dependency scanner
- **Issue**: A transitive dependency had a known vulnerability
- **Solution**: Upgraded to a patched version
- **Prevention**: Run dependency security checks regularly; block merges on critical findings

### 2025-02-25 - Missing HSTS Header
- **Vulnerability**: Insecure Transport (Medium)
- **Source**: DAST tool
- **Issue**: Response headers missing `Strict-Transport-Security`
- **Solution**: Enabled HSTS in the application or edge/proxy configuration
- **Prevention**: Use a standard security headers baseline for all services

## Tips

- Prioritize Critical and High severity issues
- Mention the specific tool that flagged it to help with false positive tracking
- Focus on the *pattern* of the fix so AI can replicate it
- If a false positive was flagged and suppressed, note it here with the reason
