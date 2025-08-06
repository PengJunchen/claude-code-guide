# Command and Subagent Optimization

This document outlines the recommendations for optimizing and merging similar functionality in the commands and subagents directories.

## Commands Directory Optimization

### Merged Commands

1. **Git Commit Related Commands**
   - Merged `commit.md`, `commit-message.md`, and `semantic-commit.md` into `git-commit.md`
   - Provides three modes: message generation, standard commit, and semantic commit splitting

2. **Code Review Related Commands**
   - Merged `review.md`, `smart-review.md`, and `explain-like-senior.md` into `code-review.md`
   - Offers three depth levels: basic review, smart review, and senior perspective

3. **Documentation Related Commands**
   - Merged `docs.md`, `update-doc-string.md`, and `update-dart-doc.md` into `documentation.md`
   - Supports general documentation, docstring updates, and Dart-specific documentation

4. **PR Related Commands**
   - Merged `pr-create.md`, `pr-review.md`, `pr-feedback.md`, `pr-list.md`, `pr-issue.md`, and `pr-auto-update.md` into `pr-manager.md`
   - Provides operations for creating, reviewing, providing feedback, listing, handling issues, and auto-updating PRs

5. **TODO Related Commands**
   - Merged `create-todos.md`, `find-todos.md`, `fix-todos.md`, and `todos-to-issues.md` into `todo-manager.md`
   - Supports operations for creating, finding, fixing, and converting TODOs

6. **Audit Related Commands**
   - Merged `performance-audit.md`, `security-audit.md`, and `generate-api-documentation.md` into `audit-manager.md`
   - Provides modes for performance audits, security assessments, and API documentation generation

7. **Dependency Related Commands**
   - Merged `analyze-dependencies.md`, `analyze-performance.md`, and `update-node-deps.md` into `dependency-manager.md`
   - Supports operations for analyzing dependencies, analyzing performance, and updating dependencies

8. **Code Fixing Related Commands**
   - Merged `fix-error.md` and `fix-imports.md` into `code-fixer.md`
   - Supports operations for fixing errors and broken imports

9. **Code Architecture Related Commands**
   - Merged `refactor.md`, `design-patterns.md`, and `tech-debt.md` into `code-architect.md`
   - Supports operations for refactoring, suggesting design patterns, and analyzing technical debt

10. **Implementation Related Commands**
    - Merged `test.md` and `implement.md` into `implementation-manager.md`
    - Supports operations for implementing features and running tests

### Benefits of Command Merging

1. **Reduced Duplication**: Eliminates overlapping functionality
2. **Improved Discoverability**: Related commands are grouped together
3. **Consistent Interface**: Provides a consistent interface for related operations
4. **Enhanced Functionality**: Combines features from multiple commands
5. **Simplified Maintenance**: Easier to maintain and update

## Subagents Directory Recommendations

### Language-Specific Experts

Recommend keeping these separate as they provide specialized expertise for different programming languages:
- `python-pro.md`, `javascript-pro.md`, `typescript-pro.md`, `java-pro.md`, etc.

Ensure they follow a consistent structure and approach.

### Architecture Related Subagents

Consider merging some of these into a more general `architecture-expert.md` with specializations:
- `architect-review.md`, `backend-architect.md`, `cloud-architect.md`, etc.

Keep domain-specific architects separate where specialized knowledge is required.

### Developer Role Subagents

Keep these separate as they represent different specialized roles:
- `frontend-developer.md`, `mobile-developer.md`, `ios-developer.md`, etc.

Ensure consistent structure and approach across similar roles.

### Engineering Specializations

Keep these separate as they represent different specialized roles:
- `data-engineer.md`, `ml-engineer.md`, `mlops-engineer.md`, etc.

Ensure consistent structure and approach across similar specializations.

## Implementation Approach

1. Create merged command files with comprehensive functionality
2. Maintain backward compatibility through mode/operation parameters
3. Ensure consistent interface and documentation
4. Standardize subagent structure and approach
5. Validate merged functionality against original commands

## Next Steps

1. Review the merged command files
2. Test the merged commands for functionality
3. Update documentation to reflect the new command structure
4. Consider similar optimizations for other command groups
5. Standardize subagent structure and approach