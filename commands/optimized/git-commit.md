# Git Commit Manager

A comprehensive tool for managing git commits with multiple modes.

## Usage

```bash
/git-commit [mode] [options]
```

## Modes

- `message` (default): Generate commit messages from staged changes
- `commit`: Analyze changes and create a meaningful commit
- `semantic`: Split large changes into multiple semantic commits

## Options

- `--format <format>`: Specify message format (conventional, gitmoji, angular)
- `--lang <language>`: Force language (en, ja)
- `--breaking`: Detect and mark breaking changes
- `--dry-run`: Show proposed commit splits without actually committing (semantic mode)
- `--max-commits <number>`: Specify maximum number of commits (semantic mode)

## Basic Examples

```bash
# Generate message from staged changes
/git-commit message

# Analyze changes and create a commit
/git-commit commit

# Split large changes into semantic commits
/git-commit semantic

# Generate message with specific format
/git-commit message --format conventional

# Split into maximum 5 commits
/git-commit semantic --max-commits 5
```

## Message Mode

Generates appropriate commit messages from staged changes (git diff --staged). Does not execute git commands, only generates messages and copies them to the clipboard.

### Prerequisites

**Important**: This mode only analyzes staged changes. You must stage changes with `git add` beforehand.

### Automatic Clipboard Function

The generated main candidate is automatically copied to the clipboard in the complete format `git commit -m "message"`. You can paste and execute it directly in the terminal.

## Commit Mode

Analyzes your changes and creates a meaningful commit message.

**Pre-Commit Quality Checks:**
Before committing, it verifies:
- Build passes (if build command exists)
- Tests pass (if test command exists)
- Linter passes (if lint command exists)
- No obvious errors in changed files

The commit message will be concise, meaningful, and follow your project's conventions if they can be detected from recent commits.

## Semantic Mode

Splits large changes into meaningful minimum units and commits them sequentially with semantic commit messages.

### Workflow

1. **Change Analysis**: Get all changes with `git diff HEAD`
2. **File Classification**: Logically group changed files
3. **Commit Proposal**: Generate semantic commit messages for each group
4. **Sequential Execution**: Commit each group sequentially after user confirmation

### Core Features for Change Splitting

#### Detecting "Large Changes"

Changes are detected as large under the following conditions:

1. **Changed Files**: 5 or more files changed
2. **Changed Lines**: 100 or more lines changed
3. **Multiple Features**: Changes spanning 2 or more functional areas
4. **Mixed Patterns**: Mix of feat + fix + docs

#### Strategies for Splitting into "Meaningful Minimum Units"

1. **Functional Boundaries**: Group by directory structure
2. **Change Type**: New files vs existing file modifications
3. **Dependency Analysis**: Group related files based on imports

## Conventional Commits Compliance

All modes follow the conventional commits format:

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

### Standard Types

**Required Types**:
- `feat`: New feature (user-visible feature addition)
- `fix`: Bug fix

**Optional Types**:
- `build`: Changes to build system or external dependencies
- `chore`: Other changes (no impact on release)
- `ci`: Changes to CI configuration files or scripts
- `docs`: Documentation-only changes
- `style`: Changes that do not affect code meaning (whitespace, formatting, semicolons, etc.)
- `refactor`: Code changes without bug fixes or feature additions
- `perf`: Performance improvements
- `test`: Adding or modifying tests

### Automatic Detection of Project Conventions

All modes automatically detect project-specific conventions from:
- CommitLint configuration files
- Existing commit history
- Project type and structure

**Important**: If project-specific conventions exist, they take precedence.

## Important Notes

- **No AI attribution**: Commits will never include AI signatures or attributions
- **No automatic push**: `git push` after commit must be executed manually
- **No branch creation**: Commits in current branch
- **Backup recommended**: Use `git stash` before important changes