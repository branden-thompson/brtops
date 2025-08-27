# DEFRAG Operation Procedures - BRTOPS v1.1.1

**🛩️ BRTOPS Framework Component**  
**Version**: 1.1.1  
**Component**: Context Optimization Engine  
**Classification**: Critical Context Management System

## 🎯 DEFRAG OPERATION OVERVIEW

The DEFRAG command performs context optimization and memory management when context utilization reaches the 75% threshold, ensuring continued high-performance operation during extended development sessions.

## 📊 DEFRAG TRIGGER CONDITIONS

### Automatic Triggers
- **Context Utilization ≥ 75%**: Primary threshold for optimization
- **Response Degradation**: Detected slowdown in AI response quality
- **Memory Fragmentation**: Detected inefficient context organization
- **Session Duration**: Extended sessions (>2 hours continuous operation)

### Manual Triggers  
- **User Command**: `DEFRAG` - Immediate context optimization
- **Emergency Context**: Critical operations requiring optimal performance
- **Pre-Critical Operations**: Before high-importance development phases

## 🔧 DEFRAG OPERATION SEQUENCE

### Phase 1: Context Assessment
```json
{
  "contextAssessment": {
    "utilizationLevel": "75-95%",
    "fragmentationScore": "0-10 scale",
    "criticalInformation": "identification of essential context",
    "redundantInformation": "identification of duplicate/obsolete context",
    "activeWorkflows": "current BRTOPS phase and dependencies"
  }
}
```

### Phase 2: Information Prioritization
**Critical Context (PRESERVE)**:
- Current project objectives and requirements
- Active feature specifications and constraints
- Current BRTOPS phase state and progress
- Recent decisions and their justifications
- Open issues and their resolution paths

**Standard Context (COMPRESS)**:
- Historical conversations and decisions
- Background documentation references
- Previous phase outputs and summaries
- General project context and setup

**Low Priority Context (ARCHIVE)**:
- Resolved issues and their solutions
- Completed phase documentation
- Reference materials and general knowledge
- Debugging sessions for resolved problems

### Phase 3: Context Optimization
```markdown
## DEFRAG EXECUTION TEMPLATE

### Context State Summary
**Pre-Defrag Utilization**: X%
**Active Workflows**: [Phase] - [Feature Name]
**Critical Operations**: [List of essential ongoing work]

### Information Architecture
**PRESERVED (Critical)**:
- Current objectives and active requirements
- In-progress implementation details
- Open decisions requiring resolution
- Active quality gates and validation criteria

**COMPRESSED (Standard)**:
- Project background → [Summary Link]
- Historical decisions → [Decision Log Reference]  
- Previous phases → [Phase Summary References]
- Documentation → [Documentation Index]

**ARCHIVED (Historical)**:
- Resolved issues → [Issue Archive Reference]
- Completed phases → [Completion Archive Reference]
- General references → [Reference Library]

### Context Restoration Points
**Quick Recovery References**:
- Project README and BRTOPS configuration
- Current feature 7-folder documentation structure
- Active branch and recent commit history
- Quality gate status and compliance checklist

### Post-Defrag Validation
- [ ] Current objectives clearly stated
- [ ] Active workflow state preserved
- [ ] Critical decisions and justifications accessible
- [ ] Context utilization reduced to ≤ 50%
- [ ] Response quality maintained or improved
```

## 🎯 DEFRAG OUTPUT REQUIREMENTS

### User Communication Template
```markdown
🔄 **DEFRAG COMPLETE**

**Context Optimization Results**:
- Utilization: [X%] → [Y%] (Δ [Z%])
- Performance: [IMPROVED | MAINTAINED | OPTIMIZED]
- Critical Information: [PRESERVED]
- Session Efficiency: [ENHANCED]

**Active Context Summary**:
- Project: [Project Name]
- Feature: [Current Feature]
- Phase: [BRTOPS Phase]
- Status: [Current Status]

**Restoration Available**: Full context restoration available via ORIENT command
**Ready State**: [READY FOR CONTINUED OPERATION]
```

## 🚨 CRITICAL PRESERVATION REQUIREMENTS

### Never Remove During DEFRAG
- Current project and feature objectives
- Active BRTOPS phase state and progress
- Open issues and blockers
- Recent architectural decisions (last 24 hours)
- Current quality gate status
- Emergency contact information and escalation procedures

### Always Preserve References To
- Project CLAUDE.md and BRTOPS configuration
- Current feature 7-folder documentation structure
- Recent git commit history and branch status
- Active pull requests and code reviews
- Current deployment and release status

## 🔗 INTEGRATION WITH OTHER COMMANDS

### Pre-DEFRAG Commands
- **SITREP**: Generate current status summary for preservation
- **CHECKPOINT**: Create restoration point before optimization

### Post-DEFRAG Commands  
- **ORIENT**: Full context restoration from preserved summaries
- **PREFLIGHT**: Validate readiness for continued operations
- **SITREP**: Confirm optimized context state

### Emergency Procedures
- **DEFRAG ABORT**: Cancel optimization and restore previous state
- **FULL RESTORE**: Complete context restoration from checkpoints
- **HUM CALL**: Request human assistance if optimization fails

## 📋 DEFRAG CHECKLIST

### Pre-Execution
- [ ] Verify context utilization ≥ 75%
- [ ] Identify current BRTOPS phase and critical state
- [ ] Confirm no critical operations in progress
- [ ] Create restoration checkpoint

### During Execution  
- [ ] Preserve all critical context identified in assessment
- [ ] Compress standard context with proper references
- [ ] Archive historical context with retrieval links
- [ ] Maintain workflow state and decision context

### Post-Execution
- [ ] Validate context utilization ≤ 50%
- [ ] Confirm critical information accessibility
- [ ] Test response quality and performance
- [ ] Verify ORIENT restoration capabilities
- [ ] Generate defrag completion report

---

**DEFRAG Operations ensure continuous high-performance context management for extended agentic team operations while preserving all critical project state and decision context.**