# Contributing to CO2 Emissions Analysis

We welcome contributions from team members and collaborators. Please follow these guidelines.

## Getting Started

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature-name`
3. Make your changes
4. Commit with descriptive messages: `git commit -m "feat: Add new analysis feature"`
5. Push to your branch: `git push origin feature/your-feature-name`
6. Submit a pull request

## Code Style

- Follow PEP 8 guidelines for Python code
- Use descriptive variable and function names
- Add docstrings to functions
- Comment complex logic

## Commit Message Format

```
<type>(<scope>): <subject>

<body>

<footer>
```

**Types:**
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation
- `style`: Code style changes
- `refactor`: Code refactoring
- `test`: Test updates
- `data`: Data processing or updates

**Example:**
```
feat(analysis): Add 2050 forecasting models

Implemented ARIMA and Prophet models for emissions projections.
Updated visualization pipeline to include forecast scenarios.

Closes #12
```

## Data Handling

- Keep raw data in `data/raw/` unchanged
- Process data into `data/processed/`
- Document any data transformations in the notebook
- Use `.gitignore` to exclude large files

## Testing

- Test code locally before committing
- Verify notebooks run end-to-end without errors
- Document any new dependencies

## Questions?

Open an issue or contact the team leads.
