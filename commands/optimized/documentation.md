# Documentation Manager

A comprehensive tool for managing documentation with language-specific options.

## Usage

```bash
/documentation [mode] [options]
```

## Modes

- `general` (default): Generate general documentation
- `docstring`: Update docstrings in code
- `dart`: Update Dart documentation

## Options

- `--lang <language>`: Specify programming language (python, javascript, typescript, etc.)
- `--format <format>`: Output format (markdown, html, etc.)
- `--scope <scope>`: Documentation scope (project, module, function, etc.)

## Basic Examples

```bash
# Generate general documentation
/documentation general

# Update docstrings in Python code
/documentation docstring --lang python

# Update Dart documentation
/documentation dart

# Generate project-level documentation
/documentation general --scope project
```

## General Documentation

Generates comprehensive documentation for your project, including:
- Project overview
- Installation instructions
- Usage examples
- API reference
- Configuration options
- Troubleshooting guide
- Contributing guidelines

The documentation follows best practices for the specified language and format.

## Docstring Updates

Updates docstrings in your code based on the specified language:

### Python
- Google style docstrings
- Type hints
- Parameter descriptions
- Return value descriptions
- Exception documentation
- Usage examples

### JavaScript/TypeScript
- JSDoc format
- Parameter types and descriptions
- Return value types and descriptions
- Exception documentation
- Usage examples

### Other Languages
- Language-specific docstring formats
- Comprehensive parameter and return value documentation
- Exception handling documentation
- Usage examples

## Dart Documentation

Updates Dart documentation following Dart's official documentation guidelines:
- Dartdoc format
- Parameter descriptions
- Return value descriptions
- Exception documentation
- Usage examples
- Widget documentation (for Flutter)

## Documentation Process

1. **Code Analysis**: Analyze code structure and existing documentation
2. **Gap Identification**: Identify missing or outdated documentation
3. **Documentation Generation**: Generate comprehensive documentation
4. **Format Validation**: Ensure documentation follows language-specific formats
5. **Output**: Provide updated documentation

## Best Practices

- Keep documentation concise and clear
- Include examples for complex functionality
- Document exceptions and edge cases
- Maintain consistent style throughout
- Update documentation when code changes