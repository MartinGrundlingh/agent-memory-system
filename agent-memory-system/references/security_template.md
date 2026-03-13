# Security Fix Log Template

This file demonstrates the format for logging security vulnerabilities and their fixes. Keep entries brief and chronological.

Note: The example entries in this template are generic. Adapt sources/tools and remediation steps to match your repository's security tooling and workflows.

## Format

Each security fix entry should include:
- Date (YYYY-MM-DD)
- Vulnerability Type (e.g., XSS, SQL Injection, Dependency Vulnerability)
- Tool/Source (e.g., Snyk, SonarCloud, OWASP ZAP, Manual Review)
- Brief description of the issue
- Solution or fix applied
- Prevention notes (how to avoid in future)

## Example Entries

### 2025-02-15 - SQL Injection in Login
- **Vulnerability**: SQL Injection (High Severity)
- **Source**: SonarCloud
- **Issue**: User input directly concatenated into SQL query in `auth.js`
- **Solution**: Replaced with parameterized queries using `pg-promise`
- **Prevention**: Always use parameterized queries; run SAST before merge

### 2025-02-20 - Outdated Dependency (lodash)
- **Vulnerability**: Prototype Pollution (Critical)
- **Source**: Snyk
- **Issue**: `lodash` version 4.17.15 has a known vulnerability
- **Solution**: Upgraded to `lodash` 4.17.21 via `npm update`
- **Prevention**: Run `npm audit` regularly; configure Snyk to block PRs with critical vulns

### 2025-02-25 - Missing HSTS Header
- **Vulnerability**: Insecure Transport (Medium)
- **Source**: OWASP ZAP
- **Issue**: Response headers missing `Strict-Transport-Security`
- **Solution**: Added HSTS middleware in Express app configuration
- **Prevention**: Use `helmet` middleware by default for all Express apps

## Tips

- Prioritize Critical and High severity issues
- Mention the specific tool that flagged it to help with false positive tracking
- Focus on the *pattern* of the fix so AI can replicate it
- If a false positive was flagged and suppressed, note it here with the reason
