# Implementation Manager

A comprehensive tool for implementing and testing features with multiple operations.

## Usage

```bash
/implementation-manager [operation] [options]
```

## Operations

- `implement` (default): Intelligently implement features from any source
- `test`: Intelligently run tests based on your current context

## Options

### Implement Operation Options
- `--source <source>`: Specify source (URL, path, or description)
- `--resume`: Continue from last implementation session
- `--status`: Check implementation progress
- `--new`: Start a fresh implementation
- `--validate`: Validate implementation completeness

### Test Operation Options
- `--context <context>`: Specify context (cold-start, active-session, post-command, debug, pre-commit)
- `--coverage`: Generate coverage report
- `--verbose`: Show detailed test output
- `--fix`: Attempt to fix failing tests
- `--watch`: Run tests in watch mode

## Basic Examples

```bash
# Implement features from a source
/implementation-manager implement --source https://github.com/user/feature

# Resume implementation
/implementation-manager implement --resume

# Run tests based on current context
/implementation-manager test

# Run tests with coverage report
/implementation-manager test --coverage

# Run tests in debug context
/implementation-manager test --context debug
```

## Implement Operation

Intelligently implements features from any source - adapting them perfectly to your project's architecture while maintaining your code patterns and standards:

### Session Intelligence

Maintains implementation progress:

**Session Files (in current project directory):**
- `implement/plan.md` - Current implementation plan and progress
- `implement/state.json` - Session state and checkpoints

**Auto-Detection:**
- If session exists: Resume from last checkpoint
- If no session: Create new implementation plan
- Commands: `resume`, `status`, `new`

### Implementation Process

#### Phase 1: Initial Setup & Analysis

**Source Detection:**
- Web URLs (GitHub, GitLab, CodePen, JSFiddle, documentation sites)
- Local paths (files, folders, existing code)
- Implementation plans (.md files with checklists)
- Feature descriptions for research

**Project Understanding:**
- Architecture patterns
- Existing dependencies and their versions
- Code conventions and established patterns
- Testing approach and quality standards

#### Phase 2: Strategic Planning

Based on analysis, creates an implementation plan:

**Plan Creation:**
- Map source features to your architecture
- Identify dependency compatibility
- Design integration approach
- Break work into testable chunks

Writes this plan to `implement/plan.md`:

```markdown
# Implementation Plan - [timestamp]

## Source Analysis
- **Source Type**: [URL/Local/Description]
- **Core Features**: [identified features to implement]
- **Dependencies**: [required libraries/frameworks]
- **Complexity**: [estimated effort]

## Target Integration
- **Integration Points**: [where it connects]
- **Affected Files**: [files to modify/create]
- **Pattern Matching**: [how to adapt to project style]

## Implementation Tasks
[Prioritized checklist with progress tracking]

## Validation Checklist
- [ ] All features implemented
- [ ] Tests written and passing
- [ ] No broken functionality
- [ ] Documentation updated
- [ ] Integration points verified
- [ ] Performance acceptable

## Risk Mitigation
- **Potential Issues**: [identified risks]
- **Rollback Strategy**: [git checkpoints]
```

#### Phase 3: Intelligent Adaptation

Transforms the source to fit your project perfectly:

**Dependency Resolution:**
- Map source libraries to your existing ones
- Reuse your utilities instead of adding duplicates
- Convert patterns to match your codebase
- Update deprecated approaches to modern standards

**Code Transformation:**
- Match your naming conventions
- Follow your error handling patterns
- Maintain your state management approach
- Preserve your testing style

#### Phase 4: Implementation Execution

Implements features incrementally:

**Execution Process:**
1. Implement core functionality
2. Add supporting utilities
3. Integrate with existing code
4. Update tests to cover new features
5. Validate everything works correctly

**Progress Tracking:**
- Update `implement/plan.md` as each item is completed
- Mark checkpoints in `implement/state.json`
- Create meaningful git commits at logical points

#### Phase 5: Quality Assurance

Ensures the implementation meets your standards:

**Validation Steps:**
- Run your existing lint commands
- Execute test suite
- Check for type errors
- Verify integration points
- Confirm no regressions

#### Phase 6: Implementation Validation

When you run `/implementation-manager implement --validate` after implementation:

**Integration Analysis:**
1. **Coverage Check** - Verify all planned features implemented
2. **Integration Points** - Validate all connections work
3. **Test Coverage** - Ensure new code is tested
4. **TODO Scan** - Find any leftover TODOs
5. **Documentation** - Check if docs reflect changes

**Validation Report:**
```
IMPLEMENTATION VALIDATION
├── Features Implemented: 12/12 (100%)
├── Integration Points: 8/10 (2 pending)
├── Test Coverage: 87%
├── Build Status: Passing
└── Documentation: Needs update

PENDING ITEMS:
- API endpoint /users/profile not connected
- WebSocket integration incomplete
- Missing tests for error scenarios
- README needs feature documentation

ENHANCEMENT OPPORTUNITIES:
1. Add error boundary for new components
2. Implement caching for API calls
3. Add performance monitoring
4. Create usage examples
```

## Test Operation

Intelligently runs tests based on your current context and actively helps fix failures:

### Context Detection

Understands what context you're in:

1. **Cold Start** (no previous context):
   - Run full test suite with coverage
   - Generate complete health report
   - Identify chronic failures

2. **Active Session** (you're implementing features):
   - Check git diff for modified files
   - Read CLAUDE.md for session goals
   - Test ONLY what you've been working on
   - Incremental testing as you code

3. **Post-Command Context**:
   - After `/scaffold`: Test the new component
   - After `/fix-todos`: Test modified files
   - After `/fix-imports`: Re-run previously failed tests
   - After `/security-scan`: Security-focused tests
   - After `/format`: Quick smoke tests only

4. **Debug Context** (previous test failures):
   - Focus on failed tests with verbose output
   - Add strategic debug logging
   - Run in isolation mode

5. **Pre-Commit Context**:
   - Full suite + lint + typecheck
   - Coverage report for PR
   - No skipped tests allowed

### Testing Process

#### Phase 1: Deep Project Analysis

Uses native tools to understand your testing setup:
- **Glob** to find configuration files in project root
- **Read** test configurations and CI/CD workflows
- **Grep** test patterns to understand testing style
- **Read** documentation for test instructions

Detects:
- Test frameworks and runners
- Test file patterns and locations
- Coverage requirements
- Integration vs unit test separation
- CI/CD test commands

#### Phase 2: Intelligent Test Execution

Runs tests with appropriate flags for maximum insight based on your project's testing framework, using verbose output and fail-fast when available to quickly identify issues.

**Build & Compilation Check:**
- Verify project builds successfully before running tests
- Watch console output for compilation errors
- Capture and analyze build warnings that might affect tests
- Check for missing dependencies or version conflicts

#### Phase 3: Failure Analysis & Auto-Fix

When tests fail:

1. **Parse failure output** to understand exact issues
2. **Read failing test** to understand expectations
3. **Read implementation** to find the bug
4. **Analyze patterns** from similar tests that pass
5. **Apply fixes** when confident

**Common fixes attempted:**
- Async/await timing issues
- Mock/stub configuration
- Import path problems
- Type mismatches
- Null/undefined handling
- Off-by-one errors
- Environment variable issues

#### Phase 4: Advanced Diagnostics

For complex failures:
- Run single test in isolation
- Add debug logging strategically
- Check test dependencies and setup/teardown
- Verify test data and fixtures
- Analyze flaky test patterns

**Log Analysis:**
- **Read** test output logs for hidden errors
- **Grep** for common error patterns in console output
- Analyze stack traces to pinpoint exact failure location
- Check for environment-specific issues in logs
- Identify resource conflicts (ports, files, databases)

#### Phase 5: Coverage & Quality

After fixing tests:
- Run coverage report if available
- Identify untested code paths
- Suggest critical missing tests
- Check for test anti-patterns

### Smart Context-Based Strategy

Based on the detected context, chooses the optimal approach:

- **No Context**: Full test discovery and execution
- **Active Development**: Watch mode on changed files only  
- **Post-Implementation**: Test coverage for new code
- **Debugging Mode**: Isolated test with maximum verbosity
- **Pre-Deploy**: Complete validation suite

## Implementation Management Process

1. **Analysis**: Analyze source and project structure
2. **Planning**: Create implementation or testing plan
3. **Execution**: Execute the plan with incremental changes
4. **Validation**: Validate implementation or fix failing tests
5. **Documentation**: Document implementation or test results

## Best Practices

- Always analyze before making changes
- Make incremental changes with frequent testing
- Follow project's code conventions and patterns
- Write tests for new features
- Document implementation decisions
- Validate implementation completeness