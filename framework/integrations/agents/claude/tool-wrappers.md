# Tool Wrapper Implementation - BRTOPS v1.1.004

**🎖️ BRTOPS Framework Component**  
**Version**: 1.1.004  
**Component**: Claude Tool Protocol Wrappers  
**Classification**: Critical System Enhancement

## 🎯 TOOL WRAPPER OVERVIEW

This implementation guide provides specific tool-level protocol integration to prevent violations at the source. Based on conversation-tracker analysis, violations occur primarily through unauthorized tool usage during high cognitive load periods.

## 🔧 EDIT TOOL PROTOCOL WRAPPER

### Implementation Strategy
**Problem**: Premature code modification before GO CODE approval  
**Solution**: Protocol validation before any file editing

```javascript
// Pseudo-implementation for Edit Tool Protocol Wrapper
function enhancedEditTool(params) {
  // Phase 1: Protocol State Validation
  const protocolState = getProtocolState();
  
  // Phase 2: Authorization Check
  if (!validateCodePhaseAuthorization(protocolState)) {
    return {
      error: "🚨 BRTOPS VIOLATION PREVENTION",
      message: "GO CODE approval required before editing files",
      guidance: "Please request GO CODE approval from user before modifying code",
      requiredAction: "REQUEST_GO_CODE_APPROVAL",
      blockingLevel: "HARD_BLOCK"
    };
  }
  
  // Phase 3: File Type Validation
  const fileType = determineFileType(params.file_path);
  if (fileType === 'CODE' && !protocolState.codePhaseApproved) {
    return {
      error: "🚨 BRTOPS VIOLATION PREVENTION", 
      message: "Code file modification requires CODE phase authorization",
      guidance: "Detected code file modification attempt without proper approval",
      requiredAction: "REQUEST_CODE_PHASE_APPROVAL",
      blockingLevel: "HARD_BLOCK"
    };
  }
  
  // Phase 4: Execute if authorized
  return executeOriginalEdit(params);
}
```

### Authorization Validation Logic
```javascript
function validateCodePhaseAuthorization(protocolState) {
  return (
    protocolState.currentPhase === 'CODE' ||
    protocolState.currentPhase === 'FINAL' ||
    protocolState.currentPhase === 'VAL'
  ) && (
    protocolState.goCodeApprovalReceived === true
  );
}

function determineFileType(filePath) {
  const codeExtensions = ['.js', '.jsx', '.ts', '.tsx', '.py', '.md', '.json'];
  const documentationPaths = ['/docs/', '/documentation/', 'README'];
  
  if (codeExtensions.some(ext => filePath.endsWith(ext))) {
    if (documentationPaths.some(path => filePath.includes(path))) {
      return 'DOCUMENTATION';
    }
    return 'CODE';
  }
  return 'OTHER';
}
```

## ✏️ WRITE TOOL PROTOCOL WRAPPER

### Implementation Strategy
**Problem**: Unauthorized file creation during non-CODE phases  
**Solution**: Phase-appropriate file creation validation

```javascript
function enhancedWriteTool(params) {
  // Phase 1: Protocol State Check
  const protocolState = getProtocolState();
  
  // Phase 2: File Creation Authorization
  const creationAuth = validateFileCreationAuth(params.file_path, protocolState);
  if (!creationAuth.authorized) {
    return {
      error: "🚨 BRTOPS VIOLATION PREVENTION",
      message: creationAuth.reason,
      guidance: creationAuth.guidance,
      requiredAction: creationAuth.requiredAction,
      blockingLevel: "HARD_BLOCK"
    };
  }
  
  // Phase 3: Content Validation
  const contentValidation = validateFileContent(params.content, params.file_path);
  if (!contentValidation.valid) {
    return {
      warning: "🚨 BRTOPS CONTENT WARNING",
      message: contentValidation.warning,
      guidance: "Consider if this content requires different phase authorization",
      blockingLevel: "SOFT_WARNING"
    };
  }
  
  // Phase 4: Execute if authorized
  return executeOriginalWrite(params);
}

function validateFileCreationAuth(filePath, protocolState) {
  const fileType = determineFileType(filePath);
  
  switch (fileType) {
    case 'CODE':
      if (!protocolState.goCodeApprovalReceived) {
        return {
          authorized: false,
          reason: "Code file creation requires GO CODE approval",
          guidance: "Request GO CODE approval before creating code files",
          requiredAction: "REQUEST_GO_CODE_APPROVAL"
        };
      }
      break;
      
    case 'DOCUMENTATION':
      // Documentation can be created in any phase with appropriate approval
      if (!protocolState.currentPhaseApproved) {
        return {
          authorized: false,
          reason: "Documentation creation requires current phase approval",
          guidance: "Ensure current phase is properly authorized",
          requiredAction: "VERIFY_PHASE_APPROVAL"
        };
      }
      break;
      
    default:
      // Other files require case-by-case evaluation
      break;
  }
  
  return { authorized: true };
}
```

## 📝 TODOWRITE TOOL PROTOCOL WRAPPER

### Implementation Strategy
**Problem**: Phase advancement without user confirmation  
**Solution**: Mandatory user validation before phase completion

```javascript
function enhancedTodoWriteTool(params) {
  // Phase 1: Detect Phase Completion Attempt
  const phaseCompletion = detectPhaseCompletionAttempt(params.todos);
  
  if (phaseCompletion.detected) {
    // Phase 2: User Confirmation Validation
    const userConfirmation = validateUserConfirmation(phaseCompletion.phase);
    
    if (!userConfirmation.confirmed) {
      return {
        error: "🚨 BRTOPS VIOLATION PREVENTION",
        message: "User confirmation required before phase completion",
        guidance: `Please request user confirmation that ${phaseCompletion.phase} phase is complete`,
        requiredAction: "REQUEST_USER_PHASE_CONFIRMATION",
        blockingLevel: "HARD_BLOCK",
        suggestedMessage: `Is the ${phaseCompletion.phase} phase complete and ready for advancement?`
      };
    }
    
    // Phase 3: Documentation Completeness Check
    if (phaseCompletion.phase === 'FINAL') {
      const docCheck = validateDocumentationCompleteness();
      if (!docCheck.complete) {
        return {
          error: "🚨 BRTOPS VIOLATION PREVENTION", 
          message: "Missing required documentation for FINAL phase",
          guidance: "Complete all required documentation before FINAL phase completion",
          requiredAction: "COMPLETE_MISSING_DOCUMENTATION",
          blockingLevel: "HARD_BLOCK",
          missingDocs: docCheck.missingDocuments
        };
      }
    }
  }
  
  // Phase 4: Execute if authorized
  return executeOriginalTodoWrite(params);
}

function detectPhaseCompletionAttempt(todos) {
  const phaseKeywords = ['RCC', 'PLAN', 'CODE', 'FINAL', 'VAL', 'DEBRIEF'];
  
  for (const todo of todos) {
    if (todo.status === 'completed') {
      for (const phase of phaseKeywords) {
        if (todo.content.toUpperCase().includes(phase)) {
          return {
            detected: true,
            phase: phase,
            todoContent: todo.content
          };
        }
      }
    }
  }
  
  return { detected: false };
}

function validateUserConfirmation(phase) {
  // This would check against a protocol state tracking system
  // that logs user confirmations for each phase
  const protocolState = getProtocolState();
  
  return {
    confirmed: protocolState.userConfirmations[phase] === true,
    timestamp: protocolState.confirmationTimestamps[phase]
  };
}
```

## 🎯 TASK TOOL PROTOCOL WRAPPER

### Implementation Strategy
**Problem**: Complex technical work without proper phase authorization  
**Solution**: Validate task complexity against current phase permissions

```javascript
function enhancedTaskTool(params) {
  // Phase 1: Analyze Task Complexity and Type
  const taskAnalysis = analyzeTaskComplexity(params.prompt);
  
  // Phase 2: Phase Authorization Check
  const phaseAuth = validateTaskPhaseAuthorization(taskAnalysis);
  
  if (!phaseAuth.authorized) {
    return {
      error: "🚨 BRTOPS VIOLATION PREVENTION",
      message: phaseAuth.reason,
      guidance: phaseAuth.guidance,
      requiredAction: phaseAuth.requiredAction,
      blockingLevel: "HARD_BLOCK"
    };
  }
  
  // Phase 3: Cognitive Load Assessment
  const cognitiveLoad = assessCognitiveLoad(taskAnalysis);
  if (cognitiveLoad.level === 'HIGH') {
    return {
      warning: "🚨 BRTOPS COGNITIVE LOAD WARNING",
      message: "High complexity task detected - Enhanced protocol compliance required",
      guidance: "Consider requesting explicit user approval before proceeding",
      enhancedProtocol: true,
      blockingLevel: "SOFT_WARNING"
    };
  }
  
  // Phase 4: Execute with enhanced monitoring
  return executeOriginalTask(params, { enhancedProtocol: cognitiveLoad.level === 'HIGH' });
}

function analyzeTaskComplexity(prompt) {
  const complexityIndicators = {
    high: ['implement', 'debug', 'fix', 'create', 'modify', 'refactor'],
    medium: ['analyze', 'review', 'assess', 'evaluate', 'plan'],
    low: ['read', 'search', 'find', 'list', 'show']
  };
  
  const promptLower = prompt.toLowerCase();
  
  for (const [level, indicators] of Object.entries(complexityIndicators)) {
    if (indicators.some(indicator => promptLower.includes(indicator))) {
      return {
        level: level.toUpperCase(),
        type: detectTaskType(promptLower),
        indicators: indicators.filter(indicator => promptLower.includes(indicator))
      };
    }
  }
  
  return { level: 'UNKNOWN', type: 'UNKNOWN', indicators: [] };
}

function detectTaskType(prompt) {
  if (prompt.includes('code') || prompt.includes('implement')) return 'IMPLEMENTATION';
  if (prompt.includes('docs') || prompt.includes('document')) return 'DOCUMENTATION';
  if (prompt.includes('search') || prompt.includes('find')) return 'RESEARCH';
  if (prompt.includes('plan') || prompt.includes('design')) return 'PLANNING';
  return 'GENERAL';
}
```

## 🔄 PROTOCOL STATE MANAGEMENT

### State Tracking System
```javascript
class ProtocolState {
  constructor() {
    this.currentPhase = 'RCC';
    this.goCodeApprovalReceived = false;
    this.userConfirmations = {};
    this.confirmationTimestamps = {};
    this.violationAttempts = [];
    this.cognitiveLoadLevel = 'NORMAL';
  }
  
  updatePhase(newPhase, userConfirmed = false) {
    if (userConfirmed) {
      this.currentPhase = newPhase;
      this.userConfirmations[newPhase] = true;
      this.confirmationTimestamps[newPhase] = Date.now();
    }
  }
  
  recordGoApproval(command) {
    switch (command) {
      case 'GO CODE':
        this.goCodeApprovalReceived = true;
        break;
      // ... other GO commands
    }
  }
  
  recordViolationAttempt(toolName, violationType, context) {
    this.violationAttempts.push({
      timestamp: Date.now(),
      tool: toolName,
      violation: violationType,
      context: context
    });
  }
  
  getCognitiveLoadLevel() {
    // Analyze recent activity patterns to determine cognitive load
    const recentActivity = this.getRecentActivity();
    return this.analyzeCognitiveLoad(recentActivity);
  }
}

// Global protocol state instance
const protocolState = new ProtocolState();

function getProtocolState() {
  return protocolState;
}
```

## 📊 IMPLEMENTATION MONITORING

### Violation Prevention Metrics
```javascript
class ViolationPreventionMetrics {
  constructor() {
    this.preventedViolations = 0;
    this.userApprovalRequests = 0;
    this.phaseAdvancementBlocks = 0;
    this.documentationGapPrevention = 0;
  }
  
  recordPreventedViolation(type, tool, context) {
    this.preventedViolations++;
    // Log for analysis and improvement
    console.log(`🎖️ BRTOPS: Prevented ${type} violation in ${tool}`);
  }
  
  generateEffectivenessReport() {
    return {
      totalPrevented: this.preventedViolations,
      approvalRequests: this.userApprovalRequests,
      phaseBlocks: this.phaseAdvancementBlocks,
      docGapPrevention: this.documentationGapPrevention,
      effectivenessRate: this.calculateEffectiveness()
    };
  }
}
```

---

**🎖️ TOOL WRAPPER IMPLEMENTATION v1.1.004**  
**Status**: Implementation Guide Complete  
**Integration**: Ready for agent-specific deployment  
**Target**: 100% violation prevention at tool level with clear user guidance