# Contributing to BRTOPS

Thank you for your interest in contributing to **BRTOPS** (Branden Thompson Operations)! This document provides guidelines for contributing to the framework.

## Table of Contents
- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Development Setup](#development-setup)
- [Contribution Process](#contribution-process)
- [Style Guidelines](#style-guidelines)
- [Community](#community)

## Code of Conduct

BRTOPS follows a military-inspired professional standard:

### Our Standards
- **Precision**: Be clear, direct, and accurate in communication
- **Respect**: Professional courtesy in all interactions  
- **Collaboration**: Human/AI partnership extends to human/human collaboration
- **Quality**: Maintain high standards for all contributions
- **Mission Focus**: Keep the project's goals and users in mind

## How Can I Contribute?

### 🐛 Reporting Bugs

**Before submitting a bug report:**
- Check if the issue already exists in [GitHub Issues](https://github.com/bthompso/brtops/issues)
- Ensure you're using the latest version (check [VERSION](VERSION))
- Gather relevant information (agent type, commands used, error messages)

**Bug Report Template:**
```
**BRTOPS Version**: [e.g., 1.0.000]
**AI Agent**: [Claude/ChatGPT/Gemini/Other]  
**Command Used**: [e.g., GO RCC]
**Expected Behavior**: [What should happen]
**Actual Behavior**: [What actually happened]
**Steps to Reproduce**:
1. 
2. 
3. 

**Additional Context**: [Screenshots, logs, etc.]
```

### 💡 Suggesting Enhancements

We welcome suggestions for:
- New commands or command improvements
- Additional AI agent integrations  
- New project type templates
- Quality gate enhancements
- Documentation improvements
- Automation tools

**Enhancement Request Template:**
```
**Enhancement Type**: [Command/Integration/Template/Documentation/Tool]
**Use Case**: [Why is this needed?]
**Proposed Solution**: [How should it work?]
**Alternatives Considered**: [Other approaches evaluated]
**Additional Context**: [Examples, mockups, etc.]
```

### 📝 Contributing Documentation

Documentation contributions are highly valued:
- **Getting Started guides** for new users
- **Advanced usage examples** for experienced users  
- **Agent-specific setup guides** for new integrations
- **Project type templates** for different domains
- **Case studies** showing real-world usage
- **Translation** of documentation to other languages

### 🛠️ Contributing Code

We accept code contributions for:
- **Setup and installation scripts**
- **Validation and quality checking tools** 
- **Documentation generators**
- **Integration helpers for new agents**
- **Automation utilities**

## Development Setup

### Prerequisites
- Git
- Text editor or IDE
- Access to AI agent for testing (Claude recommended)
- Basic understanding of BRTOPS command structure

### Local Setup
```bash
# Clone the repository
git clone https://github.com/bthompso/brtops.git
cd brtops

# Create a feature branch
git checkout -b feature/your-feature-name

# Make your changes
# ... edit files ...

# Test your changes (see Testing section)

# Commit your changes
git commit -m "Add: Brief description of changes"
git push origin feature/your-feature-name
```

### Testing Changes

**Documentation Changes:**
- Verify all links work correctly
- Check formatting renders properly
- Test examples actually work
- Validate against target AI agents

**Framework Changes:**
- Test with Claude integration
- Verify command recognition works
- Check guide system functionality
- Validate collaboration modes

**Agent Integration Changes:**
- Test with target AI agent
- Verify all BRTOPS commands work
- Check guide system integration
- Validate quality gate functionality

## Contribution Process

### 1. Discuss First (Recommended)
For significant changes, open an issue first to discuss:
- The problem you're solving
- Your proposed approach  
- How it fits with BRTOPS philosophy

### 2. Fork and Branch
- Fork the repository to your GitHub account
- Create a feature branch with a descriptive name
- Make your changes in the feature branch

### 3. Make Changes
- Follow the [Style Guidelines](#style-guidelines)
- Add documentation for new features
- Update CHANGELOG.md for significant changes
- Test your changes thoroughly

### 4. Submit Pull Request
- Write a clear description of your changes
- Reference any related issues  
- Include testing notes
- Assign reviewers (maintainers will assign if needed)

### 5. Review Process
- Maintainers will review your contribution
- Address any feedback or requested changes
- Once approved, your changes will be merged

## Style Guidelines

### Documentation Style
- **Clarity**: Write for your target audience (beginner vs advanced)
- **Conciseness**: Respect the military-inspired brevity principle
- **Structure**: Use consistent headings and formatting
- **Examples**: Include practical, working examples
- **Links**: Use relative links for internal documentation

### Command Documentation
- **Format**: Command name, purpose, usage, context
- **Examples**: Show realistic usage scenarios
- **Integration**: Explain how commands work together
- **Authority**: Specify who can use the command

### Markdown Standards
```markdown
# H1 for main sections
## H2 for subsections  
### H3 for details

**Bold** for commands and important terms
`Code` for literal values and examples
```code blocks``` for multi-line examples

- Use bullet points for lists
- Use numbered lists for procedures
```

### File Organization
- **Documentation**: Place in appropriate `docs/` subdirectory
- **Framework**: Place in `framework/` with clear categorization
- **Templates**: Place in `templates/` with descriptive names
- **Tools**: Place in `tools/` with appropriate subdirectory

### Versioning for Changes
- **MAJOR** (x.0.0): Breaking changes to command structure or core concepts
- **MINOR** (0.x.0): New features, new agent integrations, new commands
- **PATCH** (0.0.x): Bug fixes, documentation updates, small improvements

## Community

### Communication Channels
- **GitHub Issues**: Bug reports and feature requests
- **GitHub Discussions**: Questions and community discussion  
- **Pull Requests**: Code and documentation contributions

### Recognition
Contributors will be:
- Listed in CONTRIBUTORS.md
- Recognized in release notes for significant contributions
- Invited to join as maintainers for sustained contributions

### Maintainer Responsibilities
Current maintainers:
- [@bthompso](https://github.com/bthompso) - Framework Creator & Lead Maintainer

Maintainer duties:
- Review and merge pull requests
- Triage issues and feature requests  
- Maintain framework quality and consistency
- Support community contributors
- Plan and execute releases

## Questions?

- **General questions**: Open a [GitHub Discussion](https://github.com/bthompso/brtops/discussions)
- **Bug reports**: Open a [GitHub Issue](https://github.com/bthompso/brtops/issues)
- **Feature requests**: Open a [GitHub Issue](https://github.com/bthompso/brtops/issues) with enhancement label

---

**Thank you for contributing to BRTOPS!** Your contributions help build better Human/AI collaboration tools for everyone.