# Code Architect

A comprehensive tool for improving code architecture with multiple operations.

## Usage

```bash
/code-architect [operation] [options]
```

## Operations

- `refactor` (default): Perform safe and incremental code refactoring
- `patterns`: Suggest applicable design patterns for codebases
- `tech-debt`: Analyze project technical debt and create a prioritized improvement plan

## Options

### Refactor Operation Options
- `--solid`: Evaluate compliance with SOLID principles
- `--complexity`: Focus on reducing code complexity
- `--duplication`: Focus on eliminating code duplication

### Patterns Operation Options
- `--suggest`: Suggest applicable patterns (default)
- `--analyze`: Analyze existing pattern usage
- `--refactor`: Generate refactoring proposals
- `--solid`: Check compliance with SOLID principles
- `--anti-patterns`: Detect anti-patterns

### Tech-Debt Operation Options
- `--priority`: Sort issues by priority
- `--impact`: Sort issues by business impact
- `--cost`: Sort issues by fix cost
- `--roi`: Sort issues by return on investment

## Basic Examples

```bash
# Perform code refactoring
/code-architect refactor

# Suggest design patterns
/code-architect patterns

# Analyze technical debt
/code-architect tech-debt

# Refactor with SOLID principles evaluation
/code-architect refactor --solid

# Detect anti-patterns
/code-architect patterns --anti-patterns

# Analyze technical debt sorted by priority
/code-architect tech-debt --priority
```

## Refactor Operation

Performs safe and incremental code refactoring and evaluates compliance with SOLID principles:

### Refactoring Techniques

#### Extract Method

```javascript
// Before: Long method
function processOrder(order) {
  // 50 lines of complex processing
}

// After: Separation of responsibilities
function processOrder(order) {
  validateOrder(order);
  calculateTotal(order);
  saveOrder(order);
}
```

#### Replace Conditional with Polymorphism

```javascript
// Before: switch statement
function getPrice(user) {
  switch (user.type) {
    case 'premium': return basePrice * 0.8;
    case 'regular': return basePrice;
  }
}

// After: Strategy pattern
class PremiumPricing {
  calculate(basePrice) { return basePrice * 0.8; }
}
```

### SOLID Principles Check

```
S - Single Responsibility
├─ Each class has a single responsibility
├─ Limited to one reason for change
└─ Clear responsibility boundaries

O - Open/Closed
├─ Open for extension
├─ Closed for modification
└─ Protection of existing code when adding new features

L - Liskov Substitution
├─ Substitutability of derived classes
├─ Contract compliance
└─ Maintenance of expected behavior

I - Interface Segregation
├─ Appropriately granular interfaces
├─ Avoid dependencies on unused methods
└─ Role-specific interface definitions

D - Dependency Inversion
├─ Dependency on abstractions
├─ Separation from concrete implementations
└─ Utilization of dependency injection
```

### Refactoring Steps

1. **Current state analysis**
   - Complexity measurement (cyclomatic complexity)
   - Duplicate code detection
   - Dependency analysis

2. **Incremental execution**
   - Small steps (15-30 minute units)
   - Test execution after each change
   - Frequent commits

3. **Quality confirmation**
   - Maintain test coverage
   - Performance measurement
   - Code review

### Common Code Smells

- **God Object**: Class with excessively many responsibilities
- **Long Method**: Method longer than 50 lines
- **Duplicate Code**: Repetition of the same logic
- **Large Class**: Class larger than 300 lines
- **Long Parameter List**: 4 or more parameters

## Patterns Operation

Suggests applicable design patterns for codebases and evaluates compliance with SOLID principles:

### Analysis Categories

#### 1. Creational Patterns

- **Factory Pattern**: Abstracts object creation
- **Builder Pattern**: Step-by-step construction of complex objects
- **Singleton Pattern**: Ensures only one instance exists
- **Prototype Pattern**: Creates object clones

#### 2. Structural Patterns

- **Adapter Pattern**: Converts interfaces
- **Decorator Pattern**: Dynamically adds functionality
- **Facade Pattern**: Simplifies complex subsystems
- **Proxy Pattern**: Controls access to objects

#### 3. Behavioral Patterns

- **Observer Pattern**: Implements event notifications
- **Strategy Pattern**: Switches algorithms
- **Command Pattern**: Encapsulates operations
- **Iterator Pattern**: Traverses collections

### Output Example

```
Design Pattern Analysis Report
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Currently Used Patterns
├─ Observer Pattern: EventEmitter (12 instances)
├─ Factory Pattern: UserFactory (3 instances)
├─ Singleton Pattern: DatabaseConnection (1 instance)
└─ Strategy Pattern: PaymentProcessor (5 instances)

Recommended Patterns
├─ [HIGH] Repository Pattern
│  └─ Target: src/models/*.js
│  └─ Reason: Separation of data access logic
│  └─ Example:
│      class UserRepository {
│        async findById(id) { ... }
│        async save(user) { ... }
│      }
│
├─ [MED] Command Pattern
│  └─ Target: src/api/handlers/*.js
│  └─ Reason: Standardization of request processing
│
└─ [LOW] Decorator Pattern
   └─ Target: src/middleware/*.js
   └─ Reason: Improved combination of functionalities

SOLID Principle Violations
├─ [S] UserService: Handles both authentication and authorization
├─ [O] PaymentGateway: Requires modification when adding new payment methods
├─ [D] EmailService: Directly depends on concrete classes
└─ [I] IDataStore: Contains unused methods

Refactoring Proposals
1. Split UserService into authentication and authorization
2. Introduce PaymentStrategy interface
3. Define EmailService interface
4. Split IDataStore by usage
```

### Pattern Application Example

#### Before (Problematic Code)

```javascript
class OrderService {
  processOrder(order, paymentType) {
    if (paymentType === "credit") {
      // Credit card processing
    } else if (paymentType === "paypal") {
      // PayPal processing
    }
    // Other payment methods...
  }
}
```

#### After (Applying Strategy Pattern)

```javascript
// Strategy interface
class PaymentStrategy {
  process(amount) {
    throw new Error("Must implement process method");
  }
}

// Concrete strategies
class CreditCardPayment extends PaymentStrategy {
  process(amount) {
    /* Implementation */
  }
}

// Context
class OrderService {
  constructor(paymentStrategy) {
    this.paymentStrategy = paymentStrategy;
  }

  processOrder(order) {
    this.paymentStrategy.process(order.total);
  }
}
```

### Anti-Pattern Detection

- **God Object**: Classes with excessively many responsibilities
- **Spaghetti Code**: Code with complex, tangled control flow
- **Copy-Paste Programming**: Excessive use of duplicated code
- **Magic Numbers**: Hard-coded constants
- **Callback Hell**: Deeply nested callbacks

## Tech-Debt Operation

Analyzes project technical debt and creates a prioritized improvement plan:

### Analysis Perspectives

#### 1. Code-Level Issues

- **Complexity**: Functions with high cyclomatic complexity
- **Duplication**: Detection of duplicate code
- **Size**: Files/functions that are too long
- **Error Handling**: Lack of proper error handling

#### 2. Architecture-Level Issues

- **Dependency Health**: Outdated dependencies and their risks
- **Security Risks**: Security-related technical debt
- **Performance Issues**: Performance bottlenecks and optimization opportunities
- **Test Coverage Gaps**: Insufficient test coverage

#### 3. Impact of Technical Debt

- **Business Impact**: How technical debt affects business operations
- **Fix Cost**: Time and resources required to fix issues
- **Risk**: Potential risks of not addressing technical debt
- **ROI**: Return on investment of fixing technical debt

### Improvement Priorities

```
🔴 Critical: System failure risk
├─ Memory leaks (server crashes)
├─ Security vulnerabilities
├─ Performance bottlenecks
└─ Outdated dependencies with known issues

🟡 High: User experience impact
├─ Code complexity
├─ Duplicate code
├─ Insufficient error handling
└─ Lack of proper documentation

🟢 Medium: Operational efficiency
├─ Test coverage gaps
├─ Code style inconsistencies
├─ Minor performance optimizations
└─ Refactoring opportunities
```

### Output Example

```
Technical Debt Analysis Report
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

📊 Metrics Overview
├─ Total files: 120
├─ Average complexity: 15.3
├─ Duplicate code: 12%
└─ Test coverage: 65%

🚨 Critical Issues
├─ [SECURITY] Hardcoded credentials in src/config/database.js
├─ [PERFORMANCE] N+1 query in src/services/user.js
└─ [DEPENDENCY] Outdated authentication library with known vulnerabilities

⚠️ High Priority Issues
├─ [COMPLEXITY] UserService has 25 methods and 1200 lines
├─ [DUPLICATION] Similar validation logic in 5 different files
└─ [ERROR] Insufficient error handling in API endpoints

💡 Improvement Opportunities
├─ [REFACTOR] Extract validation logic into shared module
├─ [TEST] Increase test coverage for critical services
└─ [DOCS] Improve API documentation

📝 Improvement Plan
1. Fix critical security issues (1 day)
2. Update outdated dependencies (2 days)
3. Optimize performance bottlenecks (3 days)
4. Extract shared validation logic (2 days)
5. Improve error handling (2 days)
6. Increase test coverage (ongoing)
```

## Code Architecture Process

1. **Analysis**: Analyze code structure, patterns, and technical debt
2. **Planning**: Create a plan for improvements
3. **Execution**: Execute the plan with incremental changes
4. **Verification**: Verify improvements with tests and code review
5. **Documentation**: Document architectural decisions and patterns

## Best Practices

- Always analyze before making changes
- Make incremental changes with frequent testing
- Follow SOLID principles
- Use design patterns appropriately
- Prioritize technical debt based on business impact
- Document architectural decisions and patterns
- Maintain test coverage during refactoring