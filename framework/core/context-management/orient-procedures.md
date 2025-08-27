# ORIENT Operation Procedures - BRTOPS v1.1.1

**🛩️ BRTOPS Framework Component**  
**Version**: 1.1.1  
**Component**: Context Restoration Engine  
**Classification**: Critical Context Management System

## 🎯 ORIENT OPERATION OVERVIEW

The ORIENT command performs comprehensive context restoration and agent re-alignment when context utilization reaches 85% or during agent re-engagement after extended operations, ensuring full situational awareness and optimal performance.

## 📊 ORIENT TRIGGER CONDITIONS

### Automatic Triggers
- **Context Utilization ≥ 85%**: Critical threshold requiring full restoration
- **Post-DEFRAG Operations**: Following context optimization procedures
- **Session Restoration**: Re-engaging after breaks or context switches
- **Performance Degradation**: Detected loss of situational awareness

### Manual Triggers
- **User Command**: `ORIENT` - Immediate context restoration and alignment
- **Phase Transitions**: Before critical BRTOPS phase changes
- **Emergency Realignment**: After context corruption or confusion
- **Long Operation Resume**: Resuming after extended background operations

## 🧭 ORIENT OPERATION SEQUENCE

### Phase 1: Situational Assessment
```json
{
  "situationalAssessment": {
    "currentContext": "available context and recent history",
    "knowledgeGaps": "identified missing information",
    "activeObjectives": "current project and feature goals",
    "recentActivity": "last actions and decisions made",
    "environmentalState": "project structure and tool status"
  }
}
```

### Phase 2: Context Restoration
**Project-Level Restoration**:
- Project objectives and current status
- Team structure and collaboration protocols  
- Technology stack and architectural decisions
- Current sprint/milestone objectives
- Quality standards and compliance requirements

**Feature-Level Restoration**:
- Current feature specifications and acceptance criteria
- Implementation progress and recent decisions
- Open issues and resolution strategies
- Quality gate status and validation requirements
- Integration points and dependencies

**Session-Level Restoration**:
- Current BRTOPS phase and workflow state
- Recent conversations and decision context
- Active branches and code changes
- Pending approvals and review requirements
- Next planned actions and priorities

### Phase 3: Agent Re-Alignment
```markdown
## ORIENT EXECUTION TEMPLATE

### Current State Assessment
**Context Utilization**: [X%]
**Last Known State**: [Timestamp and activity]
**Knowledge Confidence**: [HIGH | MEDIUM | LOW]
**Restoration Required**: [MINIMAL | STANDARD | COMPREHENSIVE]

### Project Context Restoration
**Project**: [Project Name and Description]
**Objectives**: [Current project goals and success criteria]
**Team**: [Collaboration mode and stakeholder information]
**Standards**: [Quality gates, conventions, and compliance requirements]

### Feature Context Restoration  
**Current Feature**: [Feature name and SEV level]
**Phase**: [Current BRTOPS phase]
**Progress**: [Implementation status and recent achievements]
**Next Steps**: [Planned actions and priorities]
**Blockers**: [Open issues and dependency status]

### Technical Context Restoration
**Architecture**: [System design and technology decisions]
**Environment**: [Development setup and tool configuration]
**Code State**: [Branch status, recent changes, pending reviews]
**Quality**: [Test status, coverage, security scan results]
**Deployment**: [Release status and deployment readiness]

### Workflow Context Restoration
**BRTOPS State**: [Current phase and workflow position]
**Authority**: [HUM LEAD/AI LEAD/COLLAB mode]
**Guidance**: [GUIDE mode and assistance level]
**Recent Decisions**: [Key decisions made and their justifications]
**Quality Gates**: [Current gate status and requirements]
```

## 🔄 ORIENT RESTORATION SOURCES

### Primary Sources (Real-Time)
- Current project CLAUDE.md and BRTOPS configuration
- Active feature 7-folder documentation structure
- Recent git history and branch status
- Open pull requests and active code reviews
- Current issue tracker and project board status

### Secondary Sources (Cached)
- Project README and architecture documentation
- Team collaboration guidelines and processes
- Quality gate definitions and compliance checklists
- Historical decision logs and architectural records
- Previous SITREP outputs and status reports

### Tertiary Sources (Background)
- General project context and background information
- Technology documentation and best practices
- Team knowledge base and reference materials
- Historical troubleshooting guides and solutions
- Industry standards and compliance frameworks

## 🎯 ORIENT OUTPUT REQUIREMENTS

### Comprehensive Status Report
```markdown
🧭 **ORIENT COMPLETE - FULL SITUATIONAL AWARENESS RESTORED**

### PROJECT OVERVIEW
**Name**: [Project Name]
**Status**: [Current project status and health]
**Team**: [Collaboration mode and team structure]
**Timeline**: [Current milestone and deadlines]

### CURRENT FEATURE
**Feature**: [Feature name] (SEV-[X])
**Phase**: [BRTOPS Phase] - [Phase description]
**Progress**: [Implementation status percentage]
**Quality**: [Quality gate status]

### IMMEDIATE CONTEXT
**Last Action**: [Most recent activity and outcome]
**Current Focus**: [What we're working on now]
**Next Step**: [Immediate next action required]
**Blockers**: [Any impediments to progress]

### TECHNICAL STATE
**Branch**: [Current branch and status]  
**Changes**: [Recent code changes summary]
**Tests**: [Test status and coverage]
**Deploy**: [Deployment readiness status]

### WORKFLOW STATE
**BRTOPS Phase**: [Current phase and requirements]
**Authority**: [Decision-making authority mode]
**Guide Level**: [Assistance and explanation level]
**Quality Gates**: [Active gates and compliance status]

### RESTORATION CONFIDENCE
**Knowledge Level**: [HIGH | MEDIUM | LOW]
**Context Completeness**: [Percentage estimate]
**Ready for Operations**: [YES | CONDITIONAL | REQUIRES_ASSISTANCE]
```

## 🚨 CRITICAL RESTORATION PRIORITIES

### Highest Priority (Mission Critical)
- Current project objectives and success criteria
- Active feature requirements and acceptance criteria
- Current BRTOPS phase state and next required actions
- Open blockers and critical decision points
- Quality gate status and compliance requirements

### High Priority (Operational Effectiveness)
- Recent technical decisions and their justifications
- Current code state and pending changes
- Team collaboration protocols and authority matrix
- Integration dependencies and external constraints
- Timeline pressures and delivery commitments

### Standard Priority (Background Context)
- Historical project context and evolution
- Technology choices and architectural rationale
- Team processes and workflow optimizations
- Reference materials and documentation links
- Best practices and lessons learned

## 🔗 INTEGRATION WITH OTHER COMMANDS

### Pre-ORIENT Commands
- **SITREP**: Generate current status for restoration baseline
- **OPSCHECK**: Validate system health before restoration

### Post-ORIENT Commands
- **PREFLIGHT**: Validate operational readiness
- **GOFLIGHT**: Confirm readiness for continued operations
- **SITREP**: Generate comprehensive status with restored context

### Complementary Commands
- **DEFRAG**: Context optimization before restoration
- **HUM CALL**: Request human clarification for ambiguous context
- **CHECKPOINT**: Create restoration point after successful ORIENT

## 📋 ORIENT EXECUTION CHECKLIST

### Pre-Execution Assessment
- [ ] Identify trigger condition and restoration scope required
- [ ] Assess available context sources and information quality
- [ ] Determine restoration priority based on current needs
- [ ] Validate access to project documentation and status

### During Execution
- [ ] Restore project-level context and objectives
- [ ] Restore feature-level context and current state
- [ ] Restore workflow state and BRTOPS phase information
- [ ] Restore technical context and environment state
- [ ] Validate restored information for completeness and accuracy

### Post-Execution Validation
- [ ] Confirm comprehensive situational awareness restored
- [ ] Validate understanding of current objectives and priorities
- [ ] Verify workflow state and next action clarity
- [ ] Test response quality and decision-making capability
- [ ] Generate restoration confidence assessment

### Quality Assurance
- [ ] Cross-reference restored context with available sources
- [ ] Identify and document any remaining knowledge gaps
- [ ] Confirm alignment with team collaboration protocols
- [ ] Validate compliance with quality standards and gates
- [ ] Ensure readiness for continued high-performance operations

---

**ORIENT Operations ensure comprehensive situational awareness and optimal agent alignment for continued high-performance collaborative development.**