# PR Manager

A comprehensive tool for managing pull requests with multiple operations.

## Usage

```bash
/pr-manager [operation] [options]
```

## Operations

- `create`: Create a new pull request
- `review`: Review an existing pull request
- `feedback`: Provide feedback on a pull request
- `list`: List pull requests
- `issue`: Handle pull request issues
- `auto-update`: Automatically update pull requests

## Options

- `--repo <repository>`: Specify repository
- `--branch <branch>`: Specify branch
- `--title <title>`: Specify PR title
- `--body <body>`: Specify PR description
- `--reviewers <reviewers>`: Specify reviewers (comma-separated)
- `--labels <labels>`: Specify labels (comma-separated)

## Basic Examples

```bash
# Create a new pull request
/pr-manager create --branch feature/new-feature

# Review an existing pull request
/pr-manager review --repo owner/repo --pr 123

# List pull requests
/pr-manager list --repo owner/repo

# Handle pull request issues
/pr-manager issue --repo owner/repo --pr 123

# Automatically update pull requests
/pr-manager auto-update --repo owner/repo
```

## Create Operation

Creates a new pull request with:
- Automatically generated title based on commits
- Comprehensive description including:
  - Changes summary
  - Implementation details
  - Testing information
  - Screenshots (if applicable)
- Suggested reviewers based on code ownership
- Appropriate labels based on changes

## Review Operation

Reviews an existing pull request with:
- Code quality assessment
- Architecture and design review
- Performance analysis
- Security evaluation
- Test coverage assessment
- Documentation review

The review organizes feedback by severity:

### 🚨 CRITICAL (Must fix before merging)
- Security vulnerabilities
- Breaking changes
- Performance regressions

### ⚠️ HIGH PRIORITY (Should fix)
- Code quality issues
- Missing tests
- Documentation gaps

### 💡 SUGGESTIONS (Consider improving)
- Code style improvements
- Optimization opportunities
- Additional test coverage

## Feedback Operation

Provides detailed feedback on a pull request:
- Specific code suggestions
- Alternative approaches
- Best practices
- Performance considerations
- Security implications

## List Operation

Lists pull requests with:
- Status (open, closed, merged)
- Author
- Title
- Creation date
- Last update
- Review status
- CI/CD status

## Issue Operation

Handles pull request issues:
- Identifies common problems
- Suggests solutions
- Provides troubleshooting steps
- Helps resolve merge conflicts
- Addresses CI/CD failures

## Auto-Update Operation

Automatically updates pull requests:
- Rebases on target branch
- Resolves simple merge conflicts
- Updates dependencies
- Fixes linting issues
- Updates documentation

## PR Management Process

1. **Repository Analysis**: Analyze repository structure and conventions
2. **PR Context**: Understand PR context and requirements
3. **Operation Execution**: Execute the specified operation
4. **Output Generation**: Generate comprehensive output
5. **Follow-up Actions**: Suggest follow-up actions if needed

## Best Practices

- Follow repository-specific conventions
- Provide detailed context for changes
- Include comprehensive testing information
- Address all review comments
- Keep PRs focused and manageable