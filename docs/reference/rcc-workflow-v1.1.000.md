# RCC (Requirements & Context Collection) Workflow v1.1.000

**🛩️  BRTOPS Framework Component**  
**Version**: 1.1.000  
**Status**: Enhanced Transparency Protocol - Production Ready  
**Authority**: HUM LEAD Collaborative Design

## Overview

The RCC (Requirements & Context Collection) phase is the foundational step in BRTOPS project workflow. This document codifies the enhanced transparent process designed to provide maximum visibility and control to HUM LEAD while maintaining operational efficiency.

## Workflow Structure

```
┌─────────────────────────────────────────────────────────────┐
│ 📋 RCC (Requirements & Context Collection) - SEV-0 Process   │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│ PHASE 1: INTAKE & CLASSIFICATION                            │
│ ├─ 1.1 Parse feature request syntax                        │
│ ├─ 1.2 Confirm SEV level and authority matrix              │
│ └─ 1.3 Establish HUM LEAD protocol                         │
│                                                             │
│ PHASE 2: PROJECT SPACE SETUP                               │
│ ├─ 2.1 NEW PROJECTS                                        │
│ │   ├─ 2.1.1 Create new project space with BRTOPS folders  │
│ │   ├─ 2.1.2 REPORT new project details + prompt approval  │
│ │   ├─ 2.1.3 Set up SCM (Git) using HUM LEAD credentials   │
│ │   └─ 2.1.4 REPORT finalized details + proceed per SEV    │
│ └─ 2.2 EXISTING PROJECTS                                   │
│     ├─ 2.2.1 Search git branches matching HUM LEAD prompt │
│     ├─ 2.2.2 BRANCH EXISTS                                 │
│     │   ├─ 2.2.2.1 Prompt HUM LEAD to confirm branch use   │
│     │   ├─ 2.2.2.2 APPROVED → Use branch, go to 2.2.4      │
│     │   └─ 2.2.2.3 REJECTED → Follow NEW BRANCH protocols  │
│     ├─ 2.2.3 NEW BRANCH                                    │
│     │   └─ 2.2.3.1 Determine branch docs/ location:        │
│     │       • SYSTEM level: application/{project-name}     │
│     │       • FEATURE level: features/{project-name}       │
│     │       • BUGFIX level: prompt user SYSTEM/FEATURE     │
│     ├─ 2.2.4 Verify/create 6-folder structure per SEV     │
│     └─ 2.2.5 REPORT branch + folder details per SEV       │
│                                                             │
│ PHASE 3: REQUIREMENTS GATHERING & CLARIFICATION            │
│ ├─ 3.1 REQUIREMENTS (FUNCTIONAL & NON-FUNCTIONAL)          │
│ │   ├─ 3.1.1 Check for inferred requirements from prompt   │
│ │   ├─ 3.1.2 SUMMARIZE + REPORT inferred to HUM LEAD       │
│ │   ├─ 3.1.3 Prompt HUM LEAD confirmation + additional     │
│ │   ├─ 3.1.4 Intake HUM LEAD requirements + ASSESS         │
│ │   ├─ 3.1.5 Ask HUM LEAD clarifying questions             │
│ │   ├─ 3.1.6 Repeat 3.1.3-3.1.5 as needed for clarity     │
│ │   ├─ 3.1.7 REPORT consolidated requirements for APPROVAL │
│ │   ├─ 3.1.8 HUM LEAD APPROVES                             │
│ │   │   ├─ 3.1.8.1 Document in 'requirements.md'          │
│ │   │   └─ 3.1.8.2 Save to {project}/01-objectives/        │
│ │   └─ 3.1.9 HUM LEAD REJECTS → Return to 3.1.4           │
│ └─ 3.2 CONSTRAINTS                                         │
│     ├─ 3.2.1 ASSESS possible constraints from requirements │
│     ├─ 3.2.2 REPORT possible constraints to HUM LEAD       │
│     ├─ 3.2.3 Prompt HUM LEAD confirmation + additional     │
│     ├─ 3.2.4 Intake HUM LEAD inputs + ASSESS               │
│     ├─ 3.2.5 Ask HUM LEAD clarifying questions             │
│     ├─ 3.2.6 Repeat 3.2.3-3.2.5 as needed                 │
│     ├─ 3.2.7 REPORT consolidated constraints for APPROVAL  │
│     ├─ 3.2.8 HUM LEAD APPROVES                             │
│     │   ├─ 3.2.8.1 Document in 'constraints.md'           │
│     │   └─ 3.2.8.2 Save to {project}/01-objectives/        │
│     └─ 3.2.9 HUM LEAD REJECTS → Return to 3.2.3           │
│                                                             │
│ PHASE 4: CONTEXT DISCOVERY                                 │
│ ├─ 4.1 Search existing codebase for related functionality  │
│ ├─ 4.2 Identify current architecture patterns              │
│ ├─ 4.3 Map dependencies and integration points             │
│ ├─ 4.4 Review existing documentation                       │
│ ├─ 4.5 REPORT context findings to HUM LEAD for APPROVAL    │
│ ├─ 4.6 HUM LEAD APPROVES                                   │
│ │   ├─ 4.6.1 Document in 'context.md'                     │
│ │   └─ 4.6.2 Save to {project}/01-objectives/              │
│ └─ 4.7 HUM LEAD REJECTS → Return to 4.1 for re-analysis   │
│                                                             │
│ PHASE 5: RISK ASSESSMENT                                   │
│ ├─ 5.1 Technical complexity analysis                       │
│ ├─ 5.2 Integration risk evaluation                         │
│ ├─ 5.3 Performance impact assessment                       │
│ ├─ 5.4 Security considerations                             │
│ ├─ 5.5 REPORT risk assessment to HUM LEAD for APPROVAL     │
│ ├─ 5.6 HUM LEAD APPROVES                                   │
│ │   ├─ 5.6.1 Document in 'risk-assessment.md'             │
│ │   └─ 5.6.2 Save to {project}/02-analysis/               │
│ └─ 5.7 HUM LEAD REJECTS → Return to 5.1 for re-analysis   │
│                                                             │
│ PHASE 6: RCC COMPLETION                                    │
│ ├─ 6.1 Generate RCC summary report                         │
│ ├─ 6.2 Present findings to HUM LEAD                        │
│ └─ 6.3 Await approval for PLAN phase                       │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

## Key Principles

### Transparency Checkpoints
- Each phase requires HUM LEAD visibility
- SEV-0 requires confirmation before proceeding between phases  
- All assumptions and questions documented
- Clear go/no-go decision points

### Authority Matrix Integration
- **SEV-0**: HUM LEAD approval required for all major decisions
- **HUM LEAD**: Ultimate authority over requirements, constraints, and context validation
- **AI LEAD**: Execute technical analysis within approved parameters
- **COLLAB**: Joint decision-making on ambiguous technical details

### Documentation Standards
All documentation follows the enhanced 6-folder structure:
- **01-objectives/**: requirements.md, constraints.md, context.md
- **02-analysis/**: risk-assessment.md
- **03-architecture-design/**: (populated in PLAN phase)
- **04-development/**: (populated in CODE phase)  
- **05-debugging/**: (populated as needed)
- **06-key_learnings/**: (populated in DEBRIEF phase)

## Branch Management Protocol

### Project Type Mapping
- **SYSTEM level projects**: `docs/application/{project-name}/`
- **FEATURE level projects**: `docs/features/{project-name}/`
- **BUGFIX level projects**: Prompt HUM LEAD for SYSTEM/FEATURE classification

### Branch Workflow
1. Search for existing branches matching project scope
2. If found, prompt HUM LEAD for continuation approval
3. If new branch needed, follow naming conventions and folder structure
4. Verify/create 6-folder structure per SEV requirements

## Iterative Approval Loops

### Requirements/Constraints Pattern
1. **ASSESS** → Analyze available information
2. **REPORT** → Present findings to HUM LEAD
3. **PROMPT** → Request confirmation and additional input
4. **INTAKE** → Process HUM LEAD feedback
5. **CLARIFY** → Ask follow-up questions as needed
6. **CONSOLIDATE** → Prepare final version
7. **APPROVE** → Request HUM LEAD sign-off
8. **DOCUMENT** → Save to appropriate folder
9. **REJECT** → Return to step 4 for re-clarification

### Context Discovery Pattern
Follow same iterative pattern but focus on:
- Existing codebase analysis
- Architecture pattern identification
- Dependency mapping
- Documentation review

## SEV Level Adaptations

### SEV-0 (Critical)
- Maximum transparency required
- HUM LEAD approval for all phases
- Complete documentation in all folders
- Comprehensive risk assessment

### SEV-1 (High)
- Standard transparency protocols
- HUM LEAD approval for major decisions
- Full documentation with some optional elements
- Thorough risk assessment

### SEV-2 (Moderate)
- Essential transparency checkpoints
- HUM LEAD approval for requirements and constraints
- Core documentation folders required
- Focused risk assessment

### SEV-3+ (Low/Minimal)
- Basic transparency protocols
- HUM LEAD approval for final RCC summary
- Minimal documentation requirements
- Essential risk considerations only

## Integration with BRTOPS Commands

### Command Triggers
- **"RCC"** → Initiate full RCC workflow
- **"GO RCC"** → Begin RCC with auto-proceed authority
- **"INIT RCC"** → Initialize RCC setup phase only
- **"START RCC"** → Legacy alias for "RCC"

### Status Reporting
- **"SITREP RCC"** → Current RCC phase status
- **"RCC STATUS"** → Detailed progress through phases
- **"CHECK RCC"** → Validation of RCC completion

## Success Criteria

RCC phase is complete when:
- [ ] All 6 phases executed per protocol
- [ ] HUM LEAD approval obtained for all required components
- [ ] Documentation saved to appropriate 6-folder locations
- [ ] Risk assessment completed and approved
- [ ] RCC summary report generated and presented
- [ ] Authorization received to proceed to PLAN phase

---

**Version**: 1.1.000  
**Last Updated**: 2025-08-27  
**Simulation Status**: Successfully tested with pretend-conversation-card feature  
**Status**: Production Ready - Enhanced Transparency Protocol