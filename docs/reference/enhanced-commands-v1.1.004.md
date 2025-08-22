# Enhanced BRTOPS Command Reference v1.1.004

**🎖️ BRTOPS Framework Documentation**  
**Version**: 1.1.004  
**Component**: Enhanced Protocol Enforcement Commands  
**Classification**: Protocol Violation Prevention System

## 🚨 PROTOCOL ENFORCEMENT COMMANDS (NEW v1.1.004)

### PROTOCOL CHECK
**Purpose**: Verify current protocol compliance status  
**Usage**: `PROTOCOL CHECK`  
**Function**: Validates current phase, approvals, and documentation completeness  
**Authority**: Any user or system  
**Response**: Detailed compliance report with any violations or gaps

```json
{
  "command": "PROTOCOL CHECK",
  "response": {
    "currentPhase": "CODE",
    "approvalStatus": "GO CODE approved by user",
    "documentationCompliance": "85% complete for SEV-1",
    "violations": [],
    "recommendations": ["Complete constraints.md for full compliance"]
  }
}
```

### PROTOCOL ENFORCE
**Purpose**: Activate enhanced protocol enforcement mode  
**Usage**: `PROTOCOL ENFORCE [LEVEL]`  
**Levels**: STANDARD, ENHANCED, CRISIS  
**Function**: Adjusts protocol enforcement sensitivity  
**Authority**: User only  

```json
{
  "enforcementLevels": {
    "STANDARD": "Normal protocol compliance checking",
    "ENHANCED": "Increased validation and user confirmation requirements", 
    "CRISIS": "Maximum enforcement with simplified procedures"
  }
}
```

### PROTOCOL OVERRIDE
**Purpose**: Emergency protocol override with justification  
**Usage**: `PROTOCOL OVERRIDE [REASON]`  
**Function**: Temporarily bypass protocol enforcement  
**Authority**: User only  
**Requirements**: Detailed justification required  
**Logging**: All overrides logged for analysis

## 🔧 ENHANCED PHASE COMMANDS (Updated v1.1.004)

### GO CODE (Enhanced)
**Purpose**: Start development with enhanced protocol validation  
**Usage**: `GO CODE`  
**Enhanced Features**:
- Automatic tool permission activation
- Enhanced violation prevention
- Real-time compliance monitoring

**Pre-conditions**: 
- GO PLAN phase completed and user confirmed
- Required planning documentation present
- User explicit authorization logged

**Post-activation**:
- Edit/Write tools enabled with protocol validation
- Code modification permissions granted
- Enhanced monitoring activated

### GO FINAL (Enhanced)
**Purpose**: Quality assurance with automatic documentation audit  
**Usage**: `GO FINAL`  
**Enhanced Features**:
- Automatic SEV-level documentation compliance check
- Missing documentation auto-generation prompts
- Quality gate validation

**Pre-conditions**:
- GO CODE phase completed and user confirmed
- All implementation requirements met
- Code changes properly documented

**Automatic Validations**:
- Documentation completeness audit
- Quality gate status verification
- User confirmation requirement

### GO VAL (Enhanced)
**Purpose**: Validation with mandatory user confirmation  
**Usage**: `GO VAL`  
**Enhanced Features**:
- Mandatory user validation of specific functionality
- No self-assessment advancement allowed
- Explicit user approval required for completion

**Validation Requirements**:
- User must confirm specific functionality works as expected
- User must validate all requirements met
- User must approve advancement to DEBRIEF

## 🛡️ VIOLATION PREVENTION COMMANDS (NEW v1.1.004)

### BLOCK VIOLATION
**Purpose**: Immediate violation prevention activation  
**Usage**: System automatic - not user invoked  
**Function**: Prevents unauthorized actions at tool level  
**Response**: Clear violation explanation and guidance

**Example Responses**:
```
🚨 BRTOPS VIOLATION PREVENTION: GO CODE approval required before editing
Guidance: Please request GO CODE approval from user before modifying code
Required Action: REQUEST_GO_CODE_APPROVAL
```

### REQUEST APPROVAL
**Purpose**: Formal approval request mechanism  
**Usage**: System automatic - triggered by violation prevention  
**Function**: Guides proper approval request process  
**Format**: Structured approval request with context

**Example**:
```
🎖️ BRTOPS APPROVAL REQUEST
Phase: CODE
Action: Modify components/ui/app-header.jsx
Justification: Implement user-requested header reorganization
Required: GO CODE approval to proceed with implementation
```

### CONFIRM PHASE
**Purpose**: User confirmation of phase completion  
**Usage**: System automatic - triggered before phase advancement  
**Function**: Ensures user validates phase completion  
**Requirement**: Explicit user confirmation before advancement

## 📊 MONITORING AND ANALYTICS COMMANDS (NEW v1.1.004)

### PROTOCOL STATS
**Purpose**: Display protocol compliance statistics  
**Usage**: `PROTOCOL STATS`  
**Function**: Shows violation prevention effectiveness  
**Authority**: Any user

**Response Format**:
```json
{
  "violationsPrevented": 15,
  "userApprovalRequests": 8,
  "phaseAdvancementBlocks": 3,
  "documentationGapsFixed": 5,
  "complianceRate": "95%",
  "lastViolationAttempt": "2025-08-22T10:30:00Z"
}
```

### PROTOCOL HISTORY
**Purpose**: Display recent protocol events and actions  
**Usage**: `PROTOCOL HISTORY [LIMIT]`  
**Function**: Shows timeline of protocol enforcement actions  
**Default Limit**: 10 events

### PROTOCOL LEARN
**Purpose**: Analyze violation patterns for improvement  
**Usage**: `PROTOCOL LEARN`  
**Function**: Machine learning integration for prevention enhancement  
**Authority**: System automatic with user visibility

## 🎯 COGNITIVE LOAD MANAGEMENT COMMANDS (NEW v1.1.004)

### SIMPLIFY PROTOCOL
**Purpose**: Activate simplified protocol mode during high cognitive load  
**Usage**: System automatic - triggered by complexity detection  
**Function**: Reduces protocol complexity while maintaining compliance  
**Duration**: Until cognitive load returns to normal

### CRISIS MODE
**Purpose**: Emergency simplified protocol procedures  
**Usage**: `CRISIS MODE ACTIVATE`  
**Function**: Maximum simplification with essential compliance only  
**Authority**: User or system during detected emergencies  
**Features**:
- Simplified approval processes
- Essential documentation only
- Maximum user confirmation frequency

### RESTORE NORMAL
**Purpose**: Return to standard protocol complexity  
**Usage**: `RESTORE NORMAL` or automatic after crisis resolution  
**Function**: Restore full protocol procedures  
**Validation**: Ensure crisis conditions resolved

## 🔄 INTEGRATION COMMANDS (Enhanced v1.1.004)

### TOOL ENABLE
**Purpose**: Activate protocol-enhanced tool permissions  
**Usage**: System automatic after GO approvals  
**Function**: Enables tools with protocol validation wrapper  
**Tools**: Edit, Write, TodoWrite, Task

### TOOL DISABLE
**Purpose**: Deactivate tool permissions  
**Usage**: System automatic during unauthorized attempts  
**Function**: Prevents unauthorized tool usage  
**Recovery**: Automatic re-enablement after proper approval

### STATE SYNC
**Purpose**: Synchronize protocol state across sessions  
**Usage**: System automatic at session boundaries  
**Function**: Maintains protocol state persistence  
**Features**:
- Cross-session state preservation
- Approval status maintenance
- Violation pattern learning retention

## 📋 DOCUMENTATION AUTOMATION COMMANDS (NEW v1.1.004)

### AUTO DOC AUDIT
**Purpose**: Automatic documentation completeness checking  
**Usage**: System automatic during FINAL phase  
**Function**: Validates SEV-level documentation requirements  
**Response**: List of missing or incomplete documentation

### GENERATE MISSING DOCS
**Purpose**: Auto-generate missing required documentation  
**Usage**: `GENERATE MISSING DOCS [SEV-LEVEL]`  
**Function**: Creates placeholder documentation with templates  
**Authority**: System automatic with user confirmation

### VALIDATE DOC COMPLIANCE
**Purpose**: Verify documentation meets BRTOPS standards  
**Usage**: System automatic during phase gates  
**Function**: Ensures documentation quality and completeness  
**Criteria**: SEV-level appropriate depth and coverage

## 🎖️ COMMAND INTEGRATION MATRIX

### Phase Command Enhancements
| Command | v1.1.003 | v1.1.004 Enhancement |
|---------|----------|---------------------|
| GO CODE | Basic activation | + Tool permission management, violation prevention |
| GO FINAL | Basic activation | + Automatic doc audit, quality gate validation |
| GO VAL | Basic activation | + Mandatory user confirmation, no self-assessment |
| DEBRIEF | Basic reporting | + Violation analysis, learning integration |

### New Command Categories
| Category | Commands | Purpose |
|----------|----------|---------|
| Protocol Enforcement | PROTOCOL CHECK, PROTOCOL ENFORCE | Compliance validation |
| Violation Prevention | BLOCK VIOLATION, REQUEST APPROVAL | Structural prevention |
| Cognitive Load Management | SIMPLIFY PROTOCOL, CRISIS MODE | Adaptive compliance |
| Automation | AUTO DOC AUDIT, GENERATE MISSING DOCS | Efficiency enhancement |

---

**🎖️ ENHANCED COMMAND REFERENCE v1.1.004**  
**Status**: Complete Protocol Enhancement Documentation  
**Integration**: Ready for agent implementation  
**Target**: 95% violation prevention through enhanced command structure