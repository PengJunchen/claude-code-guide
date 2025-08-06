# Code Review

A comprehensive tool for reviewing code with multiple depth levels.

## Usage

```bash
/code-review [depth] [options]
```

## Depth Levels

- `basic` (default): Quick overview of code quality
- `smart`: Detailed analysis with specific recommendations
- `senior`: In-depth explanation from a senior developer perspective

## Options

- `--focus <area>`: Focus on specific aspects (security, performance, readability)
- `--format <format>`: Output format (markdown, plain)
- `--diff`: Review only changed code (git diff)

## Basic Examples

```bash
# Quick overview of code quality
/code-review basic

# Detailed analysis with specific recommendations
/code-review smart

# In-depth explanation from a senior perspective
/code-review senior

# Focus on security aspects
/code-review smart --focus security

# Review only changed code
/code-review smart --diff
```

## Basic Review

Provides a quick overview of code quality, focusing on:
- Code style and formatting
- Basic error handling
- Function and variable naming
- Simple performance issues
- Common security vulnerabilities

## Smart Review

Provides a detailed analysis with specific recommendations, focusing on:
- Architecture and design patterns
- Code organization and structure
- Advanced error handling
- Performance optimization
- Security best practices
- Test coverage
- Documentation quality

The smart review organizes feedback by severity:

### 🚨 CRITICAL (Must fix before deployment)
- Security vulnerabilities
- Data loss risks
- Breaking changes

### ⚠️ HIGH PRIORITY (Should fix)
- Performance degradation risks
- Maintainability issues
- Missing error handling

### 💡 SUGGESTIONS (Consider improving)
- Code style improvements
- Optimization opportunities
- Additional test coverage

## Senior Perspective

Provides an in-depth explanation from a senior developer perspective, focusing on:
- High-level architecture decisions
- Design patterns and principles
- Code maintainability and scalability
- Performance considerations
- Security implications
- Testing strategies
- Documentation requirements

The senior perspective includes:
- Detailed explanations of complex code
- Alternative approaches with pros and cons
- Best practices and industry standards
- Long-term maintenance considerations
- Knowledge transfer and mentoring

## Review Process

1. **Code Analysis**: Analyze code structure, patterns, and quality
2. **Issue Identification**: Identify potential issues and areas for improvement
3. **Recommendation Generation**: Generate specific recommendations
4. **Prioritization**: Prioritize issues by severity and impact
5. **Output Formatting**: Format output based on selected depth and options

## Best Practices

- Focus on the most critical issues first
- Provide specific, actionable recommendations
- Include code examples when appropriate
- Consider the context and constraints
- Be constructive and educational