# Definition of Done

## Purpose

Define the minimum requirements that must be met before work can be considered complete.

These requirements apply to all generated work unless explicitly overridden.

---

## General Requirements

A task is considered complete only when:

- Requirements are implemented
- Acceptance criteria are fulfilled
- Documentation is updated
- All tests pass
- Security considerations have been reviewed
- No known critical defects remain
- The implementation follows project conventions

---

## Requirements Validation

Before closing a task:

- All acceptance criteria have been verified
- Scope matches the original requirement
- No unintended functionality was introduced

---

## Code Quality

The implementation must:

- Be readable and maintainable
- Avoid unnecessary complexity
- Follow project standards
- Remove unused code
- Avoid duplication where practical

---

## Testing

The implementation must include appropriate testing.

Examples:

- Unit Tests
- Integration Tests
- End-to-End Tests
- Manual Validation

Requirements:

- All automated tests pass
- New functionality is verified
- Existing functionality is not broken

---

## Security

The implementation must be reviewed for:

- Secrets exposure
- Access control issues
- Input validation
- Authentication impacts
- Authorization impacts
- Data protection concerns

No known critical security issues may remain.

---

## Infrastructure

When infrastructure changes are included:

- Infrastructure as Code is updated
- Terraform plans are reviewed
- Infrastructure documentation is updated
- Least privilege principles are followed

---

## Documentation

The following documentation must be updated when applicable:

- Architecture documentation
- API documentation
- Deployment documentation
- User documentation
- Operational documentation

Documentation must reflect the implemented solution.

---

## Observability

When applicable:

- Logging is implemented
- Monitoring is configured
- Alerting is reviewed
- Operational visibility is sufficient

---

## Cost Review

When applicable:

- Cost impact has been evaluated
- Unnecessary resources have been avoided
- Cost policies have been followed

---

## Accessibility

For user-facing functionality:

- Responsive design is verified
- Accessibility requirements are reviewed
- Usability is validated

---

## AI-Specific Requirements

Applicable for AI-enabled systems.

- AI outputs are validated
- Safety controls are reviewed
- Human oversight requirements are respected
- Prompt changes are documented
- Model limitations are considered

---

## Production Readiness

The solution is considered production ready when:

- Deployment process is defined
- Rollback process exists
- Required monitoring exists
- Required documentation exists
- Known risks are documented

---

## Completion Checklist

Before marking work as Done:

- [ ] Requirements implemented
- [ ] Acceptance criteria met
- [ ] Tests passed
- [ ] Documentation updated
- [ ] Security reviewed
- [ ] Cost impact reviewed
- [ ] Monitoring considered
- [ ] Risks documented
- [ ] Ready for deployment

---

## Exceptions

Any exception to this Definition of Done must be explicitly documented and approved.

---

## Additional Notes

Project-specific guidance.
