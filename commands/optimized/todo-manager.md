# TODO Manager

A comprehensive tool for managing TODOs with multiple operations.

## Usage

```bash
/todo-manager [operation] [options]
```

## Operations

- `create`: Create new TODOs
- `find`: Find existing TODOs
- `fix`: Fix TODOs
- `convert`: Convert TODOs to issues

## Options

- `--scope <scope>`: Specify scope (file, directory, project)
- `--priority <priority>`: Specify priority (high, medium, low)
- `--assignee <assignee>`: Specify assignee
- `--due <date>`: Specify due date
- `--format <format>`: Output format (markdown, json, etc.)

## Basic Examples

```bash
# Create new TODOs
/todo-manager create --scope src/

# Find existing TODOs
/todo-manager find --scope project

# Fix TODOs
/todo-manager fix --priority high

# Convert TODOs to issues
/todo-manager convert --assignee username
```

## Create Operation

Creates new TODOs with:
- Clear and descriptive messages
- Priority levels
- Assignees (if specified)
- Due dates (if specified)
- Categorization (bug, feature, refactor, etc.)

Example TODO format:
```
// TODO(priority:high, assignee:username, due:2023-12-31): Implement authentication system
```

## Find Operation

Finds existing TODOs with:
- Location (file, line number)
- Message
- Priority (if specified)
- Assignee (if specified)
- Due date (if specified)
- Category (if specified)

The find operation can filter TODOs by:
- Priority
- Assignee
- Due date
- Category
- Content

## Fix Operation

Fixes TODOs by:
1. Identifying the TODO
2. Understanding the required implementation
3. Implementing the solution
4. Testing the implementation
5. Removing or updating the TODO comment

The fix operation prioritizes TODOs based on:
- Priority level
- Due date
- Dependency on other TODOs
- Complexity

## Convert Operation

Converts TODOs to issues in your issue tracking system:
- Creates new issues with:
  - Title based on TODO message
  - Description including context
  - Priority based on TODO priority
  - Assignee based on TODO assignee
  - Due date based on TODO due date
  - Labels based on TODO category
- Updates the TODO comment with issue reference

## TODO Management Process

1. **Code Analysis**: Analyze code for existing TODOs
2. **Context Understanding**: Understand the context of each TODO
3. **Operation Execution**: Execute the specified operation
4. **Output Generation**: Generate comprehensive output
5. **Follow-up Actions**: Suggest follow-up actions if needed

## Best Practices

- Write clear and descriptive TODO messages
- Include priority, assignee, and due date when relevant
- Keep TODOs specific and actionable
- Regularly review and update TODOs
- Convert important TODOs to issues for better tracking