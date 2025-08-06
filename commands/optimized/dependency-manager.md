# Dependency Manager

A comprehensive tool for managing dependencies with multiple operations.

## Usage

```bash
/dependency-manager [operation] [options]
```

## Operations

- `analyze` (default): Analyze project dependencies and architecture health
- `performance`: Analyze performance issues related to dependencies
- `update`: Safely update dependencies in your project

## Options

- `--visual`: Visually display dependencies
- `--circular`: Detect only circular dependencies
- `--depth <number>`: Specify analysis depth (default: 3)
- `--focus <path>`: Focus on specific module/directory
- `--lang <language>`: Specify programming language (node, python, rust, etc.)
- `--risk <level>`: Specify risk level for updates (safe, caution, dangerous)

## Basic Examples

```bash
# Analyze dependencies for entire project
/dependency-manager analyze

# Detect circular dependencies
/dependency-manager analyze --circular

# Analyze performance issues
/dependency-manager performance

# Update Node.js dependencies
/dependency-manager update --lang node

# Update only safe dependencies
/dependency-manager update --risk safe
```

## Analyze Operation

Analyzes project dependencies and evaluates architecture health:

### Dependency Matrix

Quantifies and displays dependencies between modules:

- Direct dependencies
- Indirect dependencies
- Dependency depth
- Fan-in/fan-out

### Architecture Violation Detection

- Layer violations (lower layers depending on upper layers)
- Circular dependencies
- Excessive coupling (high dependency degree)
- Isolated modules

### Clean Architecture Compliance Check

- Domain layer independence
- Proper separation of infrastructure layer
- Dependency direction of use case layer
- Interface application status

### Output Example

```
Dependency Analysis Report
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

📊 Metrics Overview
├─ Total modules: 42
├─ Average dependencies: 3.2
├─ Maximum dependency depth: 5
└─ Circular dependencies: 2 detected

⚠️  Architecture Violations
├─ [HIGH] src/domain/user.js → src/infra/database.js
│  └─ Domain layer directly depends on infrastructure layer
├─ [MED] src/api/auth.js ⟲ src/services/user.js
│  └─ Circular dependency detected
└─ [LOW] src/utils/helper.js → 12 modules
   └─ Excessive fan-out

✅ Recommended Actions
1. Introduce UserRepository interface
2. Redesign authentication service responsibilities
3. Split helper functions by functionality

📈 Dependency Graph
[Visual dependency diagram displayed in ASCII art]
```

## Performance Operation

Analyzes application performance issues and proposes improvements from a technical debt perspective:

### Code-Level Issues

- **O(n²) Algorithms**: Detection of inefficient array operations
- **Synchronous I/O**: Identification of blocking operations
- **Redundant Processing**: Elimination of unnecessary calculations and requests
- **Memory Leaks**: Management of event listeners and timers

### Architecture-Level Issues

- **N+1 Queries**: Database access patterns
- **Insufficient Caching**: Repeated calculations and API calls
- **Bundle Size**: Unnecessary libraries and code splitting
- **Resource Management**: Connection pools and thread usage

### Impact of Technical Debt

- **Legacy Code**: Performance degradation due to old implementations
- **Design Issues**: High coupling due to insufficient responsibility distribution
- **Insufficient Testing**: Missed detection of performance regressions
- **Insufficient Monitoring**: Early detection system for issues

### Improvement Priorities

```
🔴 Critical: System failure risk
├─ Memory leaks (server crashes)
├─ N+1 queries (database load)
└─ Synchronous I/O (response delays)

🟡 High: User experience impact
├─ Bundle size (initial load time)
├─ Image optimization (display speed)
└─ Caching strategy (response speed)

🟢 Medium: Operational efficiency
├─ Dependency updates (security)
├─ Code duplication (maintainability)
└─ Enhanced monitoring (operational load)
```

## Update Operation

Safely updates dependencies in your project:

### Risk Criteria

```
Safe (🟢):
- Patch version upgrade (1.2.3 → 1.2.4)
- Bug fixes only
- Backward compatibility guaranteed

Caution (🟡):
- Minor version upgrade (1.2.3 → 1.3.0)
- New features added
- Deprecation warnings

Dangerous (🔴):
- Major version upgrade (1.2.3 → 2.0.0)
- Breaking changes
- API removals or modifications
```

### Update Process

1. **Analysis**: Analyze current dependencies and available updates
2. **Risk Assessment**: Evaluate risk level for each update
3. **Update Plan**: Create a plan for updating dependencies
4. **Backup**: Create backups of dependency files
5. **Execution**: Execute the update
6. **Verification**: Verify functionality after updates

### Language-Specific Updates

#### Node.js

```bash
# Create backups
cp package.json package.json.backup
cp package-lock.json package-lock.json.backup

# Execute update
npm update

# Verify after update
npm test
npm run build
npm audit
```

#### Python

```bash
# Create backups
cp requirements.txt requirements.txt.backup

# Execute update
pip install -r requirements.txt --upgrade

# Verify after update
pytest
```

#### Rust

```bash
# Create backups
cp Cargo.toml Cargo.toml.backup
cp Cargo.lock Cargo.lock.backup

# Execute update
cargo update

# Verify after update
cargo test
cargo build
```

## Dependency Management Process

1. **Project Analysis**: Analyze project structure and dependencies
2. **Operation Selection**: Select appropriate operation
3. **Execution**: Execute the selected operation with specified options
4. **Report Generation**: Generate comprehensive reports
5. **Action Plan**: Create an action plan for improvements

## Best Practices

- Regularly analyze dependencies for architecture violations
- Monitor performance impact of dependencies
- Update dependencies incrementally to minimize risk
- Create backups before updating dependencies
- Verify functionality after updates
- Document dependency changes and their impact