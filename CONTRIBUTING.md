# Contributing to alemuro.mosquitto

Thank you for your interest in contributing to this Ansible role! This document provides guidelines for contributing.

## Development Setup

1. Fork the repository
2. Clone your fork locally
3. Create a new branch for your feature/fix
4. Make your changes
5. Test your changes locally
6. Submit a pull request

## Testing

### Local Testing

Before submitting a pull request, make sure to test your changes locally:

```bash
# Install testing dependencies
pip install yamllint ansible-lint ansible

# Run linting
yamllint .
ansible-lint

# Test syntax
ansible-playbook tests/test.yml --syntax-check
```

### CI/CD Pipeline

This repository uses GitHub Actions for continuous integration and deployment:

- **Pull Requests**: Automatically run linting and testing
- **Main Branch**: Automatically create tags and releases

The pipeline includes:
- YAML linting with yamllint
- Ansible linting with ansible-lint
- Ansible syntax checking
- Role structure validation
- Testing across multiple Ansible versions

## Code Style

- Follow Ansible best practices
- Use descriptive task names
- Include proper documentation
- Maintain backward compatibility when possible

## Commit Messages

Use conventional commit messages:
- `feat:` for new features
- `fix:` for bug fixes
- `docs:` for documentation changes
- `chore:` for maintenance tasks

## Release Process

Releases are automatically created when changes are pushed to the main branch:
1. Changes are merged to main
2. CI tests pass
3. A new tag is automatically created
4. A GitHub release is generated with changelog