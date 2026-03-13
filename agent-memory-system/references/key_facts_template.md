# Key Facts Template

This file demonstrates the format for storing project constants, configuration, and frequently-needed **non-sensitive** information. Organize by category using bullet lists.

Note: The example entries in this template are generic. Adapt categories and examples to match your repository and deployment environment.

## ⚠️ SECURITY WARNING: What NOT to Store Here

**NEVER store passwords, API keys, or sensitive credentials in this file.** This file is typically committed to version control and should only contain non-sensitive reference information.

**❌ NEVER store:**
- Passwords or passphrases
- API keys or authentication tokens
- Service account JSON keys or credentials
- Database passwords
- OAuth client secrets
- Private keys or certificates
- Session tokens
- Any secret values from environment variables

**✅ SAFE to store:**
- Database hostnames, ports, and cluster names
- Client names and project identifiers
- Ticket/project keys and workspace names
- Cloud account names and profile names
- API endpoint URLs (public URLs only)
- Service account email addresses (not the keys!)
- Project IDs and region names
- Container registry names
- Environment names and deployment targets

**Where to store secrets:**
- Local environment files excluded via `.gitignore`
- A password manager
- A secrets manager
- CI/CD environment variables
- Platform credential stores

## Format

Organize information into logical categories:
- Cloud configuration
- Database connection details (hostnames, ports, cluster names)
- API endpoints (URLs only, not credentials)
- Local development setup (ports, service names)
- Important URLs
- Service accounts and permissions (emails and roles, not keys)

Use bullet lists for simplicity and easy scanning.

## Example Structure
### Cloud / Environment

- Environment names: `dev`, `staging`, `prod`
- Project/account identifier: `(fill in)`
- Regions/zones used: `(fill in)`

### Database (Non-Sensitive)

- Hostname / private address: `(fill in)`
- Port: `(fill in)`
- Database name: `(fill in)`
- Connection notes: (e.g., "requires VPN", "requires tunnel/proxy")  

### API Endpoints (Public URLs Only)

- Production: `https://api.example.com`
- Staging: `https://api-staging.example.com`
- Local development: `http://localhost:8000`

### Local Development Ports

- Backend API: `(fill in)`
- Frontend: `(fill in)`
- Database: `(fill in)`

### Service Accounts / Principals (Identifiers Only)

- CI principal: `(fill in)`
- Runtime principal: `(fill in)`

### Important URLs

- Docs/runbook: `(fill in)`
- Monitoring/logs: `(fill in)`
- Deploy dashboard: `(fill in)`

## Tips

- Keep entries current (update when things change)
- Remove deprecated information after migration is complete
- Include both production and development details
- Add URLs to make navigation easier
- Use consistent formatting (same structure for similar items)
- Group related information together
- Mark deprecated items clearly with dates
