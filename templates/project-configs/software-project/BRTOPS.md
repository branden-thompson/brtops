# BRTOPS Configuration - Software Development Project

## Project Classification
**Type**: SOFTWARE  
**Complexity**: {SIMPLE | MODERATE | COMPLEX | ENTERPRISE}  
**Team Size**: {SOLO | SMALL | MEDIUM | LARGE}  
**Primary Language**: {JavaScript | Python | Java | C# | etc.}  

## BRTOPS Settings
**Framework Version**: 1.1.0  
**Guide Mode**: GUIDE AUTO (adaptive to user experience)  
**Collaboration Mode**: COLLAB (equal partnership default)  
**Quality Level**: STANDARD (adjust based on project criticality)  

## Project-Specific Commands
- **Project Status**: `SITREP PROJECT`
- **Feature Status**: `SITREP FEATURE [name]`
- **Quality Check**: `CHECK GATES`
- **Structure Check**: `CHECK STRUCTURE`
- **Emergency Stop**: `ABORT`

## SEV Classification Guidelines (Software-Specific)

### SEV-0 (Critical) - Examples:
- Authentication and authorization systems
- Database schema modifications
- Security vulnerability fixes
- Payment processing systems
- Data backup and recovery systems
- Core API changes affecting multiple services

### SEV-1 (High) - Examples:
- Major feature implementations
- Performance-critical components
- Third-party service integrations
- Database migration scripts
- Caching layer implementations
- Load balancing configurations

### SEV-2 (Moderate) - Examples:
- UI component libraries
- New API endpoints
- Feature flag implementations
- Monitoring and logging enhancements
- Configuration management updates
- Testing framework improvements

### SEV-3 (Low) - Examples:
- UI styling and layout improvements
- Documentation updates
- Non-critical bug fixes
- Code refactoring (no functional changes)
- Development tooling improvements
- Asset optimizations

### SEV-4 (Minimal) - Examples:
- Minor UI adjustments
- Text content updates
- Icon and image updates
- Code formatting improvements
- Comment additions/updates
- Development dependency updates

### SEV-5 (Trivial) - Examples:
- Typo fixes in documentation
- Dead code removal
- Unused import cleanup
- Version number updates
- License file updates
- .gitignore modifications

## Quality Gates Configuration

### Automated Gates (All SEV Levels)
- **BUILD CHECK**: `npm run build` or equivalent
- **LINT CHECK**: `npm run lint` or equivalent  
- **TYPE CHECK**: `npm run typecheck` (if TypeScript)
- **UNIT TEST**: `npm test` or equivalent

### SEV-Specific Quality Gates

#### SEV-0 (Critical) Gates
- **COV CHECK**: 100% test coverage required
- **SEC SCAN**: Security vulnerability scan (zero tolerance)
- **PERF TEST**: Performance regression testing
- **LOAD TEST**: Load testing for scalability
- **SEC REV**: Security team review required
- **ARCH REV**: Architecture review required
- **PEER REV**: 2+ developer reviews required
- **BIZ REV**: Business stakeholder approval

#### SEV-1 (High) Gates  
- **COV CHECK**: 90%+ test coverage required
- **SEC SCAN**: Security vulnerability scan
- **PERF TEST**: Performance regression testing
- **ARCH REV**: Architecture review required
- **PEER REV**: 1+ developer review required
- **INT TEST**: Integration testing required

#### SEV-2 (Moderate) Gates
- **COV CHECK**: 80%+ test coverage required
- **SEC SCAN**: Security vulnerability scan (moderate tolerance)
- **PEER REV**: 1 developer review required
- **SMOKE TEST**: Basic smoke testing

#### SEV-3+ (Low/Minimal) Gates
- **COV CHECK**: 70%+ test coverage for modified code
- **PEER REV**: Optional peer review
- **BASIC TEST**: Basic functionality testing

## Development Environment Configuration

### Required Tools and Commands
```bash
# Development server
npm run dev                    # Start development server
npm run build                  # Production build
npm run test                   # Run test suite
npm run test:watch            # Watch mode testing
npm run test:coverage         # Coverage analysis
npm run lint                  # Code linting
npm run lint:fix              # Auto-fix linting issues
npm run typecheck             # TypeScript checking (if applicable)

# Quality Gates
npm run security:scan         # Security vulnerability scan
npm run test:performance      # Performance testing
npm run test:e2e             # End-to-end testing
npm run test:integration     # Integration testing
```

### Branch Strategy
```bash
# Feature branches
feature/sev-{X}-{feature-name}

# Examples for software projects
feature/sev-0-user-authentication
feature/sev-1-payment-integration  
feature/sev-2-dashboard-ui
feature/sev-3-button-improvements
```

### Commit Message Templates (Software-Specific)
```bash
# Feature implementation
⚡ GO CODE: {feature-name} - {component} implementation

- Added {specific-functionality}
- Implemented {technical-details}
- Added comprehensive test coverage
- Updated API documentation

Files: {number} changed
Tests: {passing/total}
Coverage: {percentage}%

# Bug fix
🐛 FIX: {issue-description}

- Fixed {specific-issue}
- Added regression test
- Verified fix across browsers/environments

Issue: #{issue-number}
```

## Integration Patterns

### Database Changes
- All database migrations require SEV-1 minimum
- Backup procedures must be documented
- Rollback scripts required for production changes
- Migration testing in staging environment mandatory

### API Changes
- Breaking changes require SEV-0 classification
- Backward compatibility preferred when possible
- API versioning strategy must be followed
- Integration tests required for all endpoint changes

### Security Changes
- All security-related changes require SEV-0
- Security team review mandatory
- Penetration testing for major security features
- Compliance validation required

### Performance Changes
- Performance-critical changes require SEV-1 minimum
- Benchmark testing before and after changes
- Load testing for high-traffic components
- Performance monitoring setup required

## Testing Strategy

### Unit Testing
- Minimum 80% coverage for SEV-2+
- 90%+ coverage for SEV-1
- 100% coverage for SEV-0
- Test-driven development encouraged

### Integration Testing
- Required for all API changes
- Database integration testing for data layer changes
- Third-party service integration testing
- Cross-browser compatibility testing

### End-to-End Testing
- Critical user journeys must be covered
- Automated E2E testing in CI/CD pipeline
- Manual testing for complex user interactions
- Accessibility testing for UI changes

### Performance Testing
- Benchmark testing for performance-critical components
- Load testing for high-traffic features
- Memory leak testing for long-running processes
- Database query performance optimization

## Deployment Configuration

### Staging Environment
- All changes must be tested in staging first
- Staging environment mirrors production
- Automated deployment to staging on merge to develop
- Manual promotion to production after validation

### Production Deployment
- Blue-green deployment strategy preferred
- Database migrations run in maintenance windows
- Rollback procedures tested and documented
- Monitoring and alerting configured

### Feature Flags
- All major features behind feature flags
- Gradual rollout strategy for user-facing changes
- Kill switches for critical functionality
- A/B testing framework integration

## Team Collaboration

### Code Review Process
- All code changes require peer review
- SEV-0 changes require 2+ reviews
- Security changes require security team review
- Architecture changes require tech lead review

### Documentation Requirements
- All features require documentation updates
- API changes require API documentation updates
- README updates for setup/deployment changes
- Architecture decision records for major decisions

### Communication
- Feature proposals in feature planning meetings
- Security reviews in security review meetings
- Architecture reviews in architecture review meetings
- Post-mortem analysis for incidents

---

**Last Updated**: {date}  
**BRTOPS Version**: 1.1.0  
**Project Type**: Software Development  
**Status**: Active Development