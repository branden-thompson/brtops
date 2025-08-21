# Getting Started with BRTOPS v1.0.000

Welcome to **BRTOPS** (Branden Thompson Operations) - a military-precision development framework for Human/AI collaborative work.

## What is BRTOPS?

BRTOPS is a comprehensive Standard Operating Procedures framework that brings military-inspired command structure, adaptive guidance, and systematic quality assurance to any project involving Human/AI collaboration.

### Core Philosophy
```
🎯 PRECISION: Clear, unambiguous commands
🧭 GUIDANCE: Learn as you go with adaptive tips
🤝 COLLABORATION: Seamless human/AI partnership
✅ QUALITY: Built-in gates ensure reliable outcomes
📊 VISIBILITY: Always know where you stand
🔧 UNIVERSAL: Works across all project types
```

## Quick Start (5 minutes)

### Step 1: Choose Your AI Agent
BRTOPS currently supports:
- ✅ **Claude** (Full support)
- 🔄 **ChatGPT** (Coming in v1.1.0)
- 🔄 **Gemini** (Coming in v1.2.0)

### Step 2: Install BRTOPS Configuration

**For Claude Users:**
```bash
# Download Claude configuration
curl -o ~/.claude/CLAUDE.md https://raw.githubusercontent.com/bthompso/brtops/main/framework/integrations/agents/claude/CLAUDE.md

# Start using BRTOPS immediately
echo "GUIDE ACTIVE" | claude
```

### Step 3: Start Your First Project

```bash
# Initialize BRTOPS in any conversation
"GUIDE ACTIVE"

# Classify your first project  
"MINOR SEV-2 Learn BRTOPS Commands"

# Begin discovery
"GO RCC"
```

## Essential Commands (Learn These First)

### The Big 6 (Phase Commands)
1. **GO RCC** - Start Requirements & Context Collection
2. **GO PLAN** - Begin Strategic Planning
3. **GO CODE** - Start Implementation  
4. **GO FINAL** - Execute Quality Assurance
5. **GO VAL** - Begin Post-deployment Validation
6. **DEBRIEF** - Present findings and retrospective

### Control Commands
- **GOFLIGHT** - Auto-proceed to next phase
- **SITREP** - Get current project status
- **HOLD** / **RESUME** - Pause and continue work

### Guide Commands
- **GUIDE ACTIVE** - Full explanations and tips
- **GUIDE BRIEF** - Minimal guidance
- **GUIDE SILENT** - No explanations
- **GUIDE AUTO** - Adaptive to your experience

## Your First BRTOPS Project

Let's walk through a complete mini-project:

### 1. Start with Guidance
```
You: "GUIDE ACTIVE"
AI: "🧭 GUIDE ACTIVE: Full guidance mode enabled. I'll provide explanations and tips for all commands."
```

### 2. Classify Your Project
```
You: "MINOR SEV-3 Create a Simple Calculator"
AI: "🎯 MINOR SEV-3 project classified. This will follow streamlined process: GO CODE → GO FINAL → GO VAL"
```

### 3. Begin Requirements Collection
```
You: "GO RCC"
AI: "🧭 GUIDE: Starting Requirements & Context Collection...
    🎯 Purpose: Gather all information about your calculator requirements
    📋 What happens next: I'll ask about features, constraints, and goals
    ⚡ Pro tip: Say 'GOFLIGHT' to auto-proceed through approved phases
    
    What features should this calculator include?"
```

### 4. Auto-Proceed Through Phases
```
You: "Basic math operations: +, -, *, /"
AI: [Analyzes requirements]
You: "GOFLIGHT"
AI: "🚀 GOFLIGHT acknowledged - proceeding to GO CODE phase..."
```

### 5. Check Status Anytime
```
You: "SITREP"
AI: "-------------------------------------------------------------
    Simple Calculator | FEATURE: basic-calculator
    MINOR FEATURE ENHANCEMENT SEV-3 - LVL-2
    -------------------------------------------------------------
    Current Status: ON TRACK
    
    Calculator requirements gathered, implementation 60% complete.
    Basic arithmetic operations implemented and tested.
    
    LAST ACTION:
    Completed addition and subtraction functions with error handling.
    
    NEXT ACTION:
    Implement multiplication and division, then run quality gates.
    -------------------------------------------------------------"
```

## Understanding Project Classifications

### Feature Types
- **MAJOR**: Complex features requiring full lifecycle (6 phases)
- **MINOR**: Standard features with streamlined process (3-4 phases)
- **TWEAK**: Simple modifications (1-2 phases)

### SEV (Severity) Levels
- **SEV-0**: Critical/Complex - Maximum oversight required
- **SEV-1**: High Impact - Standard oversight  
- **SEV-2**: Moderate Impact - Balanced approach
- **SEV-3**: Low Impact - Streamlined process
- **SEV-4**: Minimal Impact - Basic process
- **SEV-5**: Trivial - Minimal process

### Example Classifications
```
"MAJOR SEV-0 User Authentication System"     # Full military precision
"MINOR SEV-2 Add Dark Mode Toggle"          # Balanced approach  
"TWEAK SEV-5 Fix Documentation Typo"        # Minimal process
```

## Collaboration Modes

### When to Use Each Mode

**HUM LEAD** - Use when:
- Making architectural decisions
- Handling complex business logic
- Working in unfamiliar domains
```
You: "HUM LEAD architecture decisions"
AI: "🤝 Human-led mode: You drive decisions, I assist with analysis and implementation"
```

**AI LEAD** - Use when:
- Implementing well-defined requirements
- Following established patterns
- Handling routine tasks
```
You: "AI LEAD implementation tasks"  
AI: "🤖 AI-led mode: I'll drive implementation while keeping you informed of key decisions"
```

**COLLAB** - Use when:
- Exploring solutions together
- Brainstorming approaches
- Learning new concepts
```
You: "COLLAB problem solving"
AI: "🤝 Collaborative mode: We'll work together as equal partners"
```

## Quality Gates Explained

BRTOPS automatically applies quality gates based on your project's SEV level:

### SEV-0 Projects (Maximum Gates)
- Test coverage requirements (100%)
- Security scans  
- Performance testing
- Architecture review
- Peer review
- Business approval

### SEV-2 Projects (Balanced Gates)
- Test coverage (80%+)
- Code standards check
- Build verification
- Peer review

### SEV-4+ Projects (Basic Gates)
- Code standards check
- Build verification

## Next Steps

1. **Read the [Command Reference](../reference/command-reference.md)** for complete command list
2. **Try a real project** with your preferred project type:
   - [Software Development](../guides/project-types/software-development.md)
   - [Writing Projects](../guides/project-types/writing-projects.md)  
   - [Creative Projects](../guides/project-types/creative-projects.md)
3. **Explore advanced features** in [Advanced Usage](../guides/advanced/)
4. **Check out examples** in [Case Studies](../examples/case-studies/)

## Troubleshooting

### Common Issues

**Commands not recognized:**
- Ensure you're using exact command syntax
- Try `EXPLAIN [command]` for help
- Check that your AI agent has BRTOPS configuration loaded

**Too many/few explanations:**
- Use `GUIDE ACTIVE` for full explanations
- Use `GUIDE BRIEF` for minimal tips  
- Use `GUIDE SILENT` for no explanations
- Use `GUIDE AUTO` for adaptive guidance

**Process feels too complex:**
- Start with TWEAK or MINOR classifications
- Use higher SEV levels (SEV-4, SEV-5) for simpler processes
- Remember: you can always `ABORT` and restart

### Getting Help

1. **In-session help**: Use `EXPLAIN [command]` or `SITREP`
2. **Documentation**: Check relevant guides in [docs/guides/](../guides/)
3. **Community**: Visit [GitHub Issues](https://github.com/bthompso/brtops/issues)
4. **Examples**: Review [case studies](../examples/case-studies/) for real-world usage

---

**Ready to experience military-precision development?** Start with `GUIDE ACTIVE` and classify your first project!