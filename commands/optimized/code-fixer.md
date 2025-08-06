# Code Fixer

A comprehensive tool for fixing various code issues with multiple operations.

## Usage

```bash
/code-fixer [operation] [options]
```

## Operations

- `error` (default): Identify root causes from error messages and suggest proven solutions
- `imports`: Fix broken import statements caused by file moves or renames

## Options

### Error Operation Options
- `--deep`: Deep analysis mode (includes dependencies and environmental factors)
- `--preventive`: Analysis focused on preventive measures
- `--quick`: Show only immediately applicable fixes

### Imports Operation Options
- `--path <path>`: Specify path to focus on
- `--resume`: Continue fixing from last session
- `--status`: Check progress of import fixes
- `--new`: Start a fresh scan for broken imports

## Basic Examples

```bash
# Standard error analysis
/code-fixer error

# Deep analysis mode
/code-fixer error --deep

# Fix all broken imports
/code-fixer imports

# Focus on specific directory
/code-fixer imports --path src/

# Resume fixing imports
/code-fixer imports --resume
```

## Error Operation

Identifies root causes from error messages and suggests proven solutions:

### Error Analysis Priorities

#### 🔴 Urgency: High (Immediate action required)

- **Application downtime**: Crashes, infinite loops, deadlocks
- **Data loss risk**: Database errors, file corruption
- **Security vulnerabilities**: Authentication failures, permission errors, injections
- **Production impact**: Deployment failures, service outages

#### 🟡 Urgency: Medium (Early action recommended)

- **Performance issues**: Memory leaks, delays, timeouts
- **Partial functionality failure**: Errors in specific features, UI glitches
- **Reduced development efficiency**: Build errors, test failures

#### 🟢 Urgency: Low (Planned action)

- **Warning messages**: Deprecation, lint errors
- **Development environment only**: Issues only in local environments
- **Future risks**: Technical debt, maintainability issues

### Analysis Process

#### Phase 1: Error Information Collection

```bash
🔴 Must execute:
- Obtain complete error messages
- Check stack traces
- Identify occurrence conditions (reproducibility)

🟡 Early execution:
- Collect environment information (OS, versions, dependencies)
- Recent change history (git log, recent commits)
- Check related logs

🟢 Additional execution:
- System resource status
- Network status
- External service status
```

#### Phase 2: Root Cause Analysis

1. **Organize surface symptoms**
   - Exact error message content
   - Timing and patterns of occurrence
   - Identification of impact scope

2. **Identify deep causes**
   - Apply 5 Whys analysis
   - Track dependencies
   - Check environmental differences

3. **Verify hypotheses**
   - Create minimal reproduction code
   - Run isolation tests
   - Narrow down causes

#### Phase 3: Solution Implementation

```bash
🔴 Immediate response (hotfix):
- Minimal fixes to suppress symptoms
- Apply temporary workarounds
- Prepare for emergency deployment

🟡 Fundamental solution:
- Essential fixes for the root cause
- Add test cases
- Update documentation

🟢 Implement preventive measures:
- Strengthen error handling
- Set up monitoring and alerts
- Improve CI/CD pipeline
```

### Output Example

```
🚨 Error Analysis Report
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

📍 Error Overview
├─ Type: [Compilation/Runtime/Logical/Environmental]
├─ Urgency: 🔴 High / 🟡 Medium / 🟢 Low
├─ Impact Scope: [Feature name/Component]
└─ Reproducibility: [100% / Intermittent / Specific conditions]

🔍 Root Cause
├─ Direct Cause: [Specific cause]
├─ Background Factors: [Environment/Configuration/Dependencies]
└─ Trigger: [Occurrence conditions]

💡 Solutions
🔴 Immediate response:
1. [Specific fix command/code]
2. [Temporary workaround]

🟡 Fundamental solution:
1. [Essential fix method]
2. [Necessary refactoring]

🟢 Preventive measures:
1. [Error handling improvement]
2. [Add tests]
3. [Monitoring setup]

📝 Verification Procedure
1. [Method to confirm after applying fix]
2. [Test execution command]
3. [Operation check items]
```

## Imports Operation

Systematically fixes import statements broken by file moves or renames, with full continuity across sessions:

### Session Intelligence

Maintains import fixing progress:

**Session Files (in current project directory):**
- `fix-imports/plan.md` - All broken imports and fixes
- `fix-imports/state.json` - Resolution progress

**Auto-Detection:**
- If session exists: Resume from last import
- If no session: Scan for broken imports
- Commands: `resume`, `status`, `new`

### Import Analysis

Detects broken imports:

**Import Patterns:**
- File not found errors
- Module resolution failures
- Moved or renamed files
- Deleted dependencies
- Circular references

**Smart Detection:**
- Language-agnostic scanning
- Path alias understanding
- Barrel export recognition
- External vs internal imports

### Resolution Planning

Based on analysis, creates resolution plan:

**Resolution Strategy:**
1. Exact filename matches
2. Similar name suggestions
3. Export symbol search
4. Path recalculation
5. Import removal if needed

Writes this plan to `fix-imports/plan.md` with:
- Each broken import location
- Possible resolutions
- Confidence level
- Fix approach

### Intelligent Fixing

Fixes imports matching your patterns:

**Resolution Patterns:**
- Update relative paths correctly
- Maintain path alias usage
- Preserve import grouping
- Follow sorting conventions

**Ambiguity Handling:**
- Show multiple matches
- Provide context for choice
- Never guess when uncertain
- Track decisions for consistency

### Incremental Fixing

Fixes imports systematically:

**Execution Process:**
1. Create git checkpoint
2. Fix import with verification
3. Check for new breaks
4. Update plan progress
5. Move to next import

**Progress Tracking:**
- Mark each fix in plan
- Record resolution choices
- Create meaningful commits

### Verification

After fixing imports:
- Syntax validation
- No new broken imports
- Circular dependency check
- Build verification if possible

### Context Continuity

**Session Resume:**
When you return and run `/code-fixer imports --resume`:
- Load broken imports list
- Show fixing statistics
- Continue from last import
- Apply same resolution patterns

**Progress Example:**
```
RESUMING IMPORT FIXES
├── Total Broken: 34
├── Fixed: 21 (62%)
├── Current: src/utils/helpers.js
└── Next: src/components/Header.tsx

Continuing fixes...
```

## Code Fixing Process

1. **Issue Identification**: Identify code issues (errors, broken imports, etc.)
2. **Analysis**: Analyze the root cause of the issues
3. **Planning**: Create a plan for fixing the issues
4. **Execution**: Execute the plan and fix the issues
5. **Verification**: Verify that the issues are fixed

## Best Practices

- Always analyze the root cause before applying fixes
- Create backups or git checkpoints before making changes
- Verify fixes to ensure they don't introduce new issues
- Document fixes and their impact for future reference
- Implement preventive measures to avoid similar issues in the future