# BRTOPS Command Reference v1.0.004

## Phase Names (Normalized)

### RCC (Requirements & Context Collection)
**Purpose**: Discovery phase to gather requirements and context  
**Usage**: `GO RCC` or `GO for RCC`  
**Normal**: "Requirements & Context Collection"  
**Next**: PLAN or GOFLIGHT  
**Authority**: Any user  

### PLAN (Strategic Planning)
**Purpose**: Strategic planning and architecture design  
**Usage**: `GO PLAN` or `GO for PLAN`  
**Normal**: "Strategic Planning"  
**Next**: CODE or GOFLIGHT  
**Authority**: Any user  

### CODE (Implementation)
**Purpose**: Development and implementation phase  
**Usage**: `GO CODE` or `GO for CODE`  
**Normal**: "Development & Implementation"  
**Next**: FINAL or GOFLIGHT  
**Authority**: Any user  

### FINAL (Quality Assurance)
**Purpose**: Quality assurance and completion tasks  
**Usage**: `GO FINAL` or `GO for FINAL`  
**Normal**: "Quality Assurance"  
**Next**: VAL or GOFLIGHT  
**Authority**: Any user  

### VAL (Post-deployment Validation)
**Purpose**: Post-deployment validation and verification  
**Usage**: `GO VAL` or `GO for VAL`  
**Normal**: "Post-deployment Validation"  
**Next**: DEBRIEF  
**Authority**: Any user  

### DEBRIEF (Retrospective)
**Purpose**: Retrospective using AAR (After Action Report)  
**Usage**: `DEBRIEF` or `GO DEBRIEF`  
**Normal**: "After Action Report"  
**Next**: Project completion  
**Authority**: Any user  

## Control Commands

### GOFLIGHT
**Purpose**: Auto-proceed authorization - continue immediately without confirmation  
**Usage**: `GOFLIGHT`  
**Context**: Flight operations terminology  
**Authority**: Any user  

### SITREP (Situation Report)
**Purpose**: Get current project status report  
**Usage**: `SITREP`  
**Normal**: "Current Status"  
**Output**: Formatted project status with recent actions and next steps  
**Authority**: Any user  

### OPSCHECK
**Purpose**: Comprehensive system status verification + protocol compliance check  
**Usage**: `OPSCHECK`  
**Context**: Operations check terminology - includes protocol verification  
**Authority**: Any user  

### HOLD
**Purpose**: Pause current work  
**Usage**: `HOLD`  
**Pair**: RESUME  
**Authority**: Any user  

### RESUME
**Purpose**: Continue from pause  
**Usage**: `RESUME`  
**Pair**: HOLD  
**Authority**: Any user  

### ABORT
**Purpose**: Emergency stop all operations  
**Usage**: `ABORT`  
**Authority**: Any user  

### RESET
**Purpose**: Start over from beginning  
**Usage**: `RESET`  
**Authority**: Any user

## Alert System

### ALERT-1 (Crisis Mode)
**Purpose**: Emergency procedures - halt all non-essential work, focus exclusively on critical problem  
**Usage**: `ALERT-1 [critical issue description]`  
**Protocol**:
- ❌ HALT all non-essential work immediately
- 🎯 FOCUS exclusively on identified critical problem  
- 🔧 ENHANCED DEBUG, DOCUMENT, SITREP capabilities active
- 📊 MANDATORY SITREP after each major state change
- 🖥️ PERSISTENT VIEW in terminal (when supported)
**Authority**: Any user

### ALERT-2 (Serious Non-Emergency)
**Purpose**: Significant issue requiring focus shift - pause non-essential work at stable checkpoint  
**Usage**: `ALERT-2 [serious issue description]`  
**Protocol**:
- 🛑 PAUSE non-essential work at next stable checkpoint
- 📝 DOCUMENT current state before refocusing
- 🔧 ENHANCED DEBUG, DOCUMENT, SITREP protocols active
- 🎯 REFOCUS on identified problem with full attention
**Authority**: Any user

### ALERT-3 (Minor/Medium Severity)
**Purpose**: Issue noted but not requiring immediate action - continue to stable state  
**Usage**: `ALERT-3 [issue description]`  
**Protocol**:
- 📝 NOTE issue for future addressing
- ✅ CONTINUE current work to stable state
- 📚 DOCUMENT all context before potential auto-compacting
- 🕒 QUEUE for next appropriate work cycle
**Authority**: Any user

## Enhanced Analysis Commands

### ASSESS [SUBJECT]
**Purpose**: Comprehensive analysis and assessment operations

#### ASSESS Scope
**Usage**: `ASSESS Scope`  
**Purpose**: Assess current scope of debugging or implementation task
**Protocol**:
1. Define current working functionality percentage
2. Define maximum acceptable functionality loss
3. Set time investment limit (2-hour checkpoints)
4. Establish rollback criteria upfront
**Authority**: Any user

#### ASSESS Impact  
**Usage**: `ASSESS Impact`
**Purpose**: Analyze and project probable changes, improvements, or degradations
**Protocol**:
1. Evaluate positive outcomes and improvements
2. Identify potential negative side effects
3. Assess risk/benefit ratio
4. Project timeline and resource impact
**Authority**: Any user

#### ASSESS Regression
**Usage**: `ASSESS Regression`  
**Purpose**: Conduct thorough regression analysis for changes
**Protocol**:
1. Identify affected system components
2. Evaluate backward compatibility impacts
3. Test critical user workflows
4. Document rollback requirements
**Authority**: Any user

### MAP [SUBJECT | SYSTEM]
**Purpose**: Documentation and diagramming operations for system understanding

#### MAP System Dependencies
**Usage**: `MAP System Dependencies [system name]`
**Purpose**: Document system dependencies before implementing changes
**Output**:
```
DEPENDENCY MAP: [System Name]
Core Dependencies (break system): [list]
Optional Dependencies (degrade gracefully): [list]  
External Dependencies (may cause issues): [list]
```
**Authority**: Any user

#### MAP Data-Flow
**Usage**: `MAP Data-Flow [component/feature]`
**Purpose**: Diagram and document data flow before making changes
**Output**:
```
DATA FLOW MAP: [Component Name]
Input Sources: [list with data types]
Processing Steps: [transformation sequence]
Output Destinations: [list with consumers]
Side Effects: [database writes, API calls, etc.]
```
**Authority**: Any user

#### MAP Event-Flow  
**Usage**: `MAP Event-Flow [system/feature]`
**Purpose**: Diagram and document event flow before making changes
**Output**:
```
EVENT FLOW MAP: [System Name]
Trigger Events: [list of initiating events]
Event Sequence: [ordered event processing]
Event Handlers: [components responding to events]
Side Effects: [secondary events, state changes]
```
**Authority**: Any user

### DEBUG [ENVIRONMENT] [ISSUE]
**Purpose**: Comprehensive debugging operations with contextual inference  
**Usage**: 
- `DEBUG` - Uses current work context (environment + issue)
- `DEBUG [environment]` - Specify environment, infer current issue
- `DEBUG [issue]` - Use current environment, specify issue  
- `DEBUG [environment] [issue]` - Fully explicit

**Verb Variants**:
- `GO for DEBUG [env] [issue]`
- `GO 4 DEBUG [env] [issue]` 
- `START DEBUG [env] [issue]`

**Contextual Inference**:
- **Environment Default**: If current work in 'dev', assume DEBUG in 'dev' unless specified
- **Issue Default**: If working on specific issue, assume DEBUG for that issue unless specified
- **Full Context**: Agent infers both environment and issue from current work context

**Environment Options**: `dev`, `staging`, `prod`, `local`, `test`

**Examples**:
```
# Context: Working on login bug in development
User: "DEBUG" 
AI: "🔧 DEBUG initiated: dev environment, login authentication issue"

# Context: Production deployment issue  
User: "DEBUG prod"
AI: "🔧 PROD DEBUG initiated: production environment, deployment failure issue"

# Explicit specification
User: "GO for DEBUG staging infinite retry loops"
AI: "🔧 DEBUG initiated: staging environment, infinite retry loops"
```

**Enhanced Safeguards by Environment**:
- **prod**: Circuit breaker patterns required, rollback procedures documented
- **staging**: Deployment validation, user acceptance testing protocols  
- **dev**: Comprehensive logging, test coverage validation
- **local**: Performance profiling, memory leak detection
- **test**: Automated test execution, regression validation

**Authority**: Any user  

## Collaboration Commands

### HUM LEAD (Human Lead)
**Purpose**: Switch to human-led collaboration mode  
**Usage**: `HUM LEAD`  
**Context**: Human drives decisions, AI assists  
**Authority**: Human user  

### AI LEAD (AI Lead)
**Purpose**: Switch to AI-led collaboration mode  
**Usage**: `AI LEAD`  
**Context**: AI drives process, human validates  
**Authority**: Human user  

### COLLAB (Collaborative)
**Purpose**: Switch to equal partnership mode  
**Usage**: `COLLAB`  
**Context**: Equal partnership approach  
**Authority**: Any user  

### HUM CALL (Human Call)
**Purpose**: Request human input  
**Usage**: `HUM CALL: [description]`  
**Context**: AI needs human decision  
**Authority**: AI agent  

### AI TAKE (AI Take)
**Purpose**: Transfer control to AI  
**Usage**: `AI TAKE [task]`  
**Context**: Human delegates to AI  
**Authority**: Human user  

### REV REQ (Review Required)
**Purpose**: Mandatory human approval needed  
**Usage**: `REV REQ`  
**Context**: Critical changes  
**Authority**: AI agent  

### AUTO GO (Auto Proceed)
**Purpose**: AI authorized to continue  
**Usage**: `AUTO GO`  
**Context**: Routine operations  
**Authority**: Human user  

## Guide Commands

### GUIDE ACTIVE
**Purpose**: Enable full guidance mode  
**Usage**: `GUIDE ACTIVE`  
**Context**: Provides tips, explanations, and context for all commands  
**Authority**: Any user  

### GUIDE BRIEF
**Purpose**: Enable minimal guidance mode  
**Usage**: `GUIDE BRIEF`  
**Context**: Only provide tips for new/unfamiliar commands  
**Authority**: Any user  

### GUIDE SILENT
**Purpose**: Disable guidance mode  
**Usage**: `GUIDE SILENT`  
**Context**: Execute commands without explanations  
**Authority**: Any user  

### GUIDE AUTO
**Purpose**: Enable adaptive guidance mode  
**Usage**: `GUIDE AUTO`  
**Context**: Learn user familiarity and adjust tips accordingly  
**Authority**: Any user  

### EXPLAIN [COMMAND]
**Purpose**: Get explanation for specific command  
**Usage**: `EXPLAIN GO RCC`  
**Context**: On-demand command help  
**Authority**: Any user  

## Quality Gate Commands

### GATECHECK
**Purpose**: Run, assess, and report on all required quality gates  
**Usage**: `GATECHECK` or `GATECHK`  
**Process**:
1. **RUN**: Execute all SEV-level appropriate quality gates
2. **ASSESS**: Compile results and analyze pass/fail status  
3. **REPORT**: Present findings with 1-3 actionable recommendations
**Context**: Auto-determined by SEV level  
**Authority**: Any user

**Example Output**:
```
🛡️ GATECHECK COMPLETE
✅ Test Coverage: 87% (Target: 85%) - PASS
❌ Security Scan: 2 medium vulnerabilities found - FAIL  
✅ Performance: All benchmarks within acceptable range - PASS
✅ Code Review: Approved with minor suggestions - PASS

📊 RECOMMENDATIONS:
1. Address SQL injection vulnerability in user input validation
2. Update dependency with known security patch  
3. Consider caching optimization for repeated API calls

🎯 GATE STATUS: 3/4 PASS - Address security issues before deployment
```

### OPSSEC (Operational Security Check)
**Purpose**: Scan, assess, and report on security vulnerabilities  
**Usage**: `OPSSEC`  
**Process**:
1. **SCAN**: Execute comprehensive security vulnerability scan
2. **ASSESS**: Analyze findings by severity and exploitability
3. **REPORT**: Present prioritized vulnerabilities with remediation steps  
**Trigger**: Before deployment, on security alerts  
**Authority**: Any user

**Example Output**:
```
🔒 OPSSEC SCAN COMPLETE
🚨 CRITICAL: 1 vulnerability found
⚠️  HIGH: 2 vulnerabilities found  
📋 MEDIUM: 3 vulnerabilities found
ℹ️  LOW: 5 vulnerabilities found

📊 RECOMMENDATIONS:
1. IMMEDIATE: Update Express.js to patch RCE vulnerability (CVE-2024-XXXX)
2. THIS WEEK: Implement input sanitization for user-generated content  
3. NEXT SPRINT: Enable security headers (HSTS, CSP, X-Frame-Options)

🎯 SECURITY STATUS: CRITICAL issues must be resolved before production deployment
```

### PR (Peer Review)
**Purpose**: Human code review coordination and tracking  
**Usage**: `PR`  
**Process**:
1. **RUN**: Create or update pull request for review
2. **ASSESS**: Track review status and incorporate feedback
3. **REPORT**: Summarize review outcomes and required changes
**Context**: Uses standard GitHub nomenclature and workflows  
**Authority**: Human reviewer + AI coordination

**Example Output**:
```
📝 PR STATUS REPORT  
🔗 Pull Request: #247 "Add user authentication system"
👥 Reviewers: @tech-lead (approved), @security-expert (requested changes)

📊 REVIEW SUMMARY:
✅ Code quality: Clean implementation, good test coverage
⚠️  Security: Address password hashing concern  
✅ Performance: No performance impact detected

📋 RECOMMENDATIONS:
1. Switch from MD5 to bcrypt for password hashing (security-expert)
2. Add input validation tests (tech-lead suggestion)  
3. Update documentation for new auth endpoints

🎯 PR STATUS: 1 approval, 1 change request - Address security concern to merge
```

### PERFCHK (Performance Check)
**Purpose**: Run, assess, and report on performance status and benchmarks  
**Usage**: `PERFCHK` or `PERFSTAT`  
**Process**:
1. **RUN**: Execute performance tests and collect metrics
2. **ASSESS**: Compare against benchmarks and identify bottlenecks  
3. **REPORT**: Present performance status with optimization recommendations
**Context**: Includes load testing, memory usage, response times  
**Authority**: Any user

**Example Output**:
```
⚡ PERFCHK COMPLETE
📈 API Response Times: 245ms avg (Target: <300ms) - PASS
💾 Memory Usage: 512MB (Target: <1GB) - PASS  
🔄 Database Queries: 15ms avg - PASS
❌ Page Load Time: 4.2s (Target: <3s) - FAIL

📊 PERFORMANCE METRICS:
- CPU Usage: 45% avg, 78% peak  
- Network I/O: 2.3MB/s avg
- Cache Hit Rate: 87%

📋 RECOMMENDATIONS:
1. Optimize image compression (reduce page load by ~1.5s)
2. Implement lazy loading for below-fold content
3. Consider CDN for static assets in production

🎯 PERFORMANCE STATUS: 3/4 benchmarks met - Address page load optimization
```

### COV CHECK (Coverage Check)
**Purpose**: Run, assess, and report on test coverage status
**Usage**: `COV CHECK`
**Process**:
1. **RUN**: Execute test coverage analysis across codebase
2. **ASSESS**: Compare against coverage targets and identify gaps
3. **REPORT**: Present coverage metrics with improvement recommendations
**Context**: Integrated with GATECHECK but available as standalone command
**Authority**: Any user

**Example Output**:
```
📊 COV CHECK COMPLETE
✅ Overall Coverage: 87% (Target: 85%) - PASS
✅ Function Coverage: 92% - PASS
⚠️  Branch Coverage: 78% (Target: 80%) - WARN
❌ Line Coverage: 83% (Target: 90%) - FAIL

📋 UNCOVERED AREAS:
- src/auth/password-reset.js: 45% coverage
- src/utils/data-validation.js: 62% coverage  
- src/api/error-handling.js: 71% coverage

📊 RECOMMENDATIONS:
1. Add test cases for password reset edge cases (email failures, expired tokens)
2. Implement validation tests for malformed input scenarios
3. Create error handling tests for network timeout conditions

🎯 COVERAGE STATUS: 2/4 metrics met - Focus on branch and line coverage improvements
```  

## Feature Classification

### Feature Types
- **MAJOR**: Complex features requiring full lifecycle
- **MINOR**: Standard features with streamlined process  
- **TWEAK**: Simple modifications

### SEV Levels
- **SEV-0**: Critical impact/extreme complexity
- **SEV-1**: High impact/high complexity
- **SEV-2**: Moderate impact/moderate complexity
- **SEV-3**: Low impact/low complexity
- **SEV-4**: Minimal impact/minimal complexity
- **SEV-5**: Trivial impact/trivial complexity

### Usage Pattern
```
[FEATURE TYPE] SEV-[LEVEL] [Description]

Examples:
"MAJOR SEV-0 User Authentication System"
"MINOR SEV-2 Theme Toggle Implementation"
"TWEAK SEV-5 Fix Documentation Typo"
```

## Process Integration

### Standard Flow
```
Feature Request → GO RCC → GO PLAN → GO CODE → GO FINAL → GO VAL → DEBRIEF
```

### With Quality Gates
```
GO CODE → GATECHECK → GO FINAL → PR → GATECHECK → GO VAL
```

### Security & Performance Integration
```
Implementation → OPSSEC → PERFCHK → GATECHECK → Deployment
```

### Emergency Flow (Traditional)
```
ABORT → ASSESS → ROLLBACK → RESUME or RESET
```

### Alert System Flow
```
Critical Issue → ALERT-1 → ASSESS Scope → MAP System Dependencies → PROD DEBUG → SITREP
Serious Issue → ALERT-2 → ASSESS Impact → Enhanced protocols → SITREP  
Minor Issue → ALERT-3 → DOCUMENT → QUEUE → Continue normal flow
```

## Command Combinations

### Typical Workflow
```
User: "MAJOR SEV-1 User Dashboard Enhancement"
AI: "GO RCC for MAJOR SEV-1 feature"
User: "GOFLIGHT"
AI: [Proceeds through RCC → PLAN → CODE → FINAL → VAL → DEBRIEF]
User: "SITREP"
AI: [Shows current status]
```

### Enhanced Analysis Pattern
```
User: "DEBUG infinite retry loops"
AI: "🔧 DEBUG initiated: dev environment, infinite retry loops"
User: "ASSESS Scope"
AI: [Current functionality: 95%, Max loss: 10%, Time limit: 4h, Rollback criteria defined]
User: "MAP System Dependencies session system"
AI: [Core: GlobalSessionProvider, Optional: ActiveStackers, External: React Query]
User: "ASSESS Impact"
AI: [Risk/benefit analysis with timeline projections]
```

### Contextual DEBUG Examples
```
# Context: Working on login bug in development
User: "DEBUG"
AI: "🔧 DEBUG initiated: dev environment, login authentication issue
    Context auto-detected from current work. Correct? (Y/n)"

# Context: Production deployment failure
User: "GO 4 DEBUG prod"
AI: "🔧 PROD DEBUG initiated: production environment, deployment failure issue
    Enhanced safeguards active: circuit breakers required, rollback documented"

# Explicit environment + issue
User: "START DEBUG staging infinite retry loops"
AI: "🔧 DEBUG initiated: staging environment, infinite retry loops
    Staging protocols active: deployment validation, integration testing"
```

### Alert System Example
```
User: "ALERT-1 Production system down"
AI: "🚨 CRISIS MODE ACTIVATED - halting all non-essential work"
AI: "📊 SITREP: System status, focusing exclusively on production issue"
User: "PROD DEBUG production deployment failure"
AI: [Production-focused debugging with enhanced protocols]
```

### Collaboration Example
```
User: "HUM LEAD architecture decisions"
AI: "🤝 Human-led mode activated"
User: "AI TAKE implementation tasks"  
AI: "🤖 Taking control of implementation"
```

### Quality Gates Example  
```
User: "GATECHECK"
AI: "🛡️ Running all required quality gates for current SEV level..."
AI: [Comprehensive report with pass/fail status and recommendations]
User: "OPSSEC"
AI: "🔒 Security scan complete - 1 CRITICAL vulnerability found"
User: "PERFCHK"  
AI: "⚡ Performance check complete - Page load optimization needed"
```

### System Verification Example
```
User: "OPSCHECK"
AI: [Comprehensive system verification + protocol compliance check]
User: "ABORT" (if critical issues found)
AI: [Emergency stop all operations]
```