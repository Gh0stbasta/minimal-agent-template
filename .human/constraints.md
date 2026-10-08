# Constraints

## Purpose

Define the technical, operational, legal, financial, and organizational boundaries that must be respected at all times.

Constraints are mandatory.

If a proposed solution violates a constraint, the solution must be rejected or escalated for human review.

---

## Technology Constraints

### Cloud Platform

Allowed:

Examples:

- AWS
- Azure
- Google Cloud

Restrictions:

---

### Programming Languages

Allowed:

Examples:

- TypeScript
- Python
- Go
- Java

Restrictions:

---

### Frameworks

Allowed:

Examples:

- React
- Next.js
- FastAPI
- Spring Boot

Restrictions:

---

### Infrastructure

Allowed:

Examples:

- Terraform
- CloudFormation
- Pulumi

Restrictions:

---

### Authentication

Allowed:

Examples:

- Cognito
- Entra ID
- Auth0
- Keycloak

Restrictions:

---

## Architecture Constraints

### Deployment Model

Allowed:

- Serverless Only
- Containers
- Virtual Machines
- Hybrid

Restrictions:

---

### Regions

Allowed deployment regions:

Examples:

- eu-central-1
- eu-west-1

Restrictions:

---

### Data Storage

Allowed:

Examples:

- DynamoDB
- PostgreSQL
- Aurora
- S3

Restrictions:

---

### Networking

Requirements:

Examples:

- Public internet access allowed
- Private networking required
- VPN required
- Zero-trust architecture required

---

## Security Constraints

Requirements:

Examples:

- Multi-factor authentication required
- Encryption at rest required
- Encryption in transit required
- Least privilege required

Additional requirements:

---

## Compliance Constraints

Applicable standards, regulations, or policies.

Examples:

- GDPR
- ISO 27001
- HIPAA
- PCI-DSS

Requirements:

---

## Operational Constraints

Requirements:

Examples:

- Infrastructure as Code required
- Automated deployment required
- Git-based workflow required
- Rollback capability required

Additional requirements:

---

## Cost Constraints

Reference cost requirements defined in `cost-policy.md`.

Additional restrictions:

Examples:

- Maximum monthly cost
- Scale-to-zero required
- Managed services preferred

---

## Third-Party Constraints

Rules for external dependencies.

Examples:

- Open source preferred
- SaaS allowed with approval
- No external data processors
- No vendor lock-in where practical

Requirements:

---

## Data Constraints

Requirements:

Examples:

- Data must remain in Germany
- Data must remain in the EU
- No personal data storage
- User deletion supported
- Data retention limits apply

Additional requirements:

---

## AI Constraints

Applicable if AI capabilities are used.

Examples:

- Approved models only
- Human approval required for critical actions
- No autonomous production changes
- No direct access to sensitive data
- Prompt logging required

Additional requirements:

---

## Development Constraints

Requirements:

Examples:

- Pull request workflow required
- Code reviews required
- Automated testing required
- DevContainer required
- Documentation-first development

Additional requirements:

---

## Prohibited Technologies

Technologies, services, or approaches that must not be used.

Examples:

- Long-lived credentials
- Manual infrastructure changes
- Hardcoded secrets
- Shared administrator accounts

---

## Escalation Rules

Human approval is required when:

- A constraint must be bypassed
- A new platform is introduced
- A prohibited technology is proposed
- Compliance requirements are impacted

---

## Additional Notes

Project-specific constraints and guidance.
