# Audit Manager

A comprehensive tool for performing various types of audits and generating documentation.

## Usage

```bash
/audit-manager [mode] [options]
```

## Modes

- `performance` (default): Conduct a performance audit
- `security`: Perform a security assessment
- `api-docs`: Generate API documentation

## Options

- `--scope <scope>`: Specify scope (file, directory, project)
- `--format <format>`: Output format (markdown, html, json, etc.)
- `--level <level>`: Audit detail level (basic, comprehensive, expert)
- `--output <path>`: Output path for generated documentation

## Basic Examples

```bash
# Conduct a performance audit
/audit-manager performance

# Perform a security assessment
/audit-manager security

# Generate API documentation
/audit-manager api-docs

# Conduct a comprehensive performance audit
/audit-manager performance --level comprehensive

# Generate API documentation in HTML format
/audit-manager api-docs --format html
```

## Performance Audit Mode

Conducts a comprehensive performance audit following these steps:

1. **Technology Stack Analysis**
   - Identifies the primary language, framework, and runtime environment
   - Reviews build tools and optimization configurations
   - Checks for performance monitoring tools already in place

2. **Code Performance Analysis**
   - Identifies inefficient algorithms and data structures
   - Looks for nested loops and O(n²) operations
   - Checks for unnecessary computations and redundant operations
   - Reviews memory allocation patterns and potential leaks

3. **Database Performance**
   - Analyzes database queries for efficiency
   - Checks for missing indexes and slow queries
   - Reviews connection pooling and database configuration
   - Identifies N+1 query problems and excessive database calls

4. **Frontend Performance**
   - Analyzes bundle size and chunk optimization
   - Checks for unused code and dependencies
   - Reviews image optimization and lazy loading
   - Examines render performance and re-render cycles
   - Checks for memory leaks in UI components

5. **Network Performance**
   - Reviews API call patterns and caching strategies
   - Checks for unnecessary network requests
   - Analyzes payload sizes and compression
   - Examines CDN usage and static asset optimization

6. **Asynchronous Operations**
   - Reviews async/await usage and promise handling
   - Checks for blocking operations and race conditions
   - Analyzes task queuing and background processing
   - Identifies opportunities for parallel execution

7. **Memory Usage**
   - Checks for memory leaks and excessive memory consumption
   - Reviews garbage collection patterns
   - Analyzes object lifecycle and cleanup
   - Identifies large objects and unnecessary data retention

8. **Build & Deployment Performance**
   - Analyzes build times and optimization opportunities
   - Reviews dependency bundling and tree shaking
   - Checks for development vs production optimizations
   - Examines deployment pipeline efficiency

9. **Performance Monitoring**
   - Checks existing performance metrics and monitoring
   - Identifies key performance indicators (KPIs) to track
   - Reviews alerting and performance thresholds
   - Suggests performance testing strategies

10. **Benchmarking & Profiling**
    - Runs performance profiling tools appropriate for the stack
    - Creates benchmarks for critical code paths
    - Measures before and after optimization impact
    - Documents performance baselines

11. **Optimization Recommendations**
    - Prioritizes optimizations by impact and effort
    - Provides specific code examples and alternatives
    - Suggests architectural improvements for scalability
    - Recommends appropriate performance tools and libraries

## Security Audit Mode

Performs a systematic security audit following these steps:

1. **Environment Setup**
   - Identifies the technology stack and framework
   - Checks for existing security tools and configurations
   - Reviews deployment and infrastructure setup

2. **Dependency Security**
   - Scans all dependencies for known vulnerabilities
   - Checks for outdated packages with security issues
   - Reviews dependency sources and integrity
   - Uses appropriate tools: `npm audit`, `pip check`, `cargo audit`, etc.

3. **Authentication & Authorization**
   - Reviews authentication mechanisms and implementation
   - Checks for proper session management
   - Verifies authorization controls and access restrictions
   - Examines password policies and storage

4. **Input Validation & Sanitization**
   - Checks all user input validation and sanitization
   - Looks for SQL injection vulnerabilities
   - Identifies potential XSS (Cross-Site Scripting) issues
   - Reviews file upload security and validation

5. **Data Protection**
   - Identifies sensitive data handling practices
   - Checks encryption implementation for data at rest and in transit
   - Reviews data masking and anonymization practices
   - Verifies secure communication protocols (HTTPS, TLS)

6. **Secrets Management**
   - Scans for hardcoded secrets, API keys, and passwords
   - Checks for proper secrets management practices
   - Reviews environment variable security
   - Identifies exposed configuration files

7. **Error Handling & Logging**
   - Reviews error messages for information disclosure
   - Checks logging practices for security events
   - Verifies sensitive data is not logged
   - Assesses error handling robustness

8. **Infrastructure Security**
   - Reviews containerization security (Docker, etc.)
   - Checks CI/CD pipeline security
   - Examines cloud configuration and permissions
   - Assesses network security configurations

9. **Security Headers & CORS**
   - Checks security headers implementation
   - Reviews CORS configuration
   - Verifies CSP (Content Security Policy) settings
   - Examines cookie security attributes

10. **Reporting**
    - Documents all findings with severity levels (Critical, High, Medium, Low)
    - Provides specific remediation steps for each issue
    - Includes code examples and file references
    - Creates an executive summary with key recommendations

## API Documentation Mode

Generates comprehensive API documentation following these steps:

1. **API Documentation Strategy Analysis**
   - Analyzes current API structure and endpoints
   - Identifies documentation requirements (REST, GraphQL, gRPC, etc.)
   - Assesses existing code annotations and documentation
   - Determines documentation output formats and hosting requirements
   - Plans documentation automation and maintenance strategy

2. **Documentation Tool Selection**
   - Chooses appropriate API documentation tools:
     - **OpenAPI/Swagger**: REST API documentation with Swagger UI
     - **Redoc**: Modern OpenAPI documentation renderer
     - **GraphQL**: GraphiQL, Apollo Studio, GraphQL Playground
     - **Postman**: API documentation with collections
     - **Insomnia**: API documentation and testing
     - **API Blueprint**: Markdown-based API documentation
     - **JSDoc/TSDoc**: Code-first documentation generation
   - Considers factors: API type, team workflow, hosting, interactivity

3. **Code Annotation and Schema Definition**
   - Adds comprehensive code annotations for API endpoints
   - Defines request/response schemas and data models
   - Adds parameter descriptions and validation rules
   - Documents authentication and authorization requirements
   - Adds example requests and responses

4. **API Specification Generation**
   - Sets up automated API specification generation from code
   - Configures OpenAPI/Swagger specification generation
   - Sets up schema validation and consistency checking
   - Configures API versioning and changelog generation
   - Sets up specification file management and version control

5. **Interactive Documentation Setup**
   - Configures interactive API documentation with try-it-out functionality
   - Sets up API testing and example execution
   - Configures authentication handling in documentation
   - Sets up request/response validation and examples
   - Configures API endpoint categorization and organization

6. **Documentation Content Enhancement**
   - Adds comprehensive API guides and tutorials
   - Creates authentication and authorization documentation
   - Adds error handling and status code documentation
   - Creates SDK and client library documentation
   - Adds rate limiting and usage guidelines

7. **Documentation Hosting and Deployment**
   - Sets up documentation hosting and deployment
   - Configures documentation website generation and styling
   - Sets up custom domain and SSL configuration
   - Configures documentation search and navigation
   - Sets up documentation analytics and usage tracking

8. **Automation and CI/CD Integration**
   - Configures automated documentation generation in CI/CD pipeline
   - Sets up documentation deployment automation
   - Configures documentation validation and quality checks
   - Sets up documentation change detection and notifications
   - Configures documentation testing and link validation

9. **Multi-format Documentation Generation**
   - Generates documentation in multiple formats (HTML, PDF, Markdown)
   - Sets up downloadable documentation packages
   - Configures offline documentation access
   - Sets up documentation API for programmatic access
   - Configures documentation syndication and distribution

10. **Maintenance and Quality Assurance**
    - Sets up documentation quality monitoring and validation
    - Configures documentation feedback and improvement workflows
    - Sets up documentation analytics and usage metrics
    - Creates documentation maintenance procedures and guidelines
    - Trains team on documentation best practices and tools
    - Sets up documentation review and approval processes

## Audit Process

1. **Project Analysis**: Analyze project structure and requirements
2. **Mode Selection**: Select appropriate audit or documentation mode
3. **Scope Definition**: Define the scope of the audit or documentation
4. **Execution**: Execute the selected mode with specified options
5. **Report Generation**: Generate comprehensive reports or documentation
6. **Recommendations**: Provide actionable recommendations

## Best Practices

- Focus on high-impact, low-effort improvements first
- Provide specific, actionable recommendations
- Include code examples and file references
- Consider the project context and constraints
- Automate audits and documentation generation when possible