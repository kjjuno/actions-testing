# actions-testing

Testing github actions

## GitHub Actions Workflows

This repository includes several GitHub Actions workflows:

### 🔄 CI Pipeline (`ci.yml`)
- **Triggers**: Push to `main`/`develop`, PRs to `main`, manual dispatch
- **Features**: 
  - Multi-language support (Node.js, Python)
  - Conditional dependency installation
  - Testing and linting
  - Automatic deployment to staging

### 🚀 Release (`release.yml`)
- **Triggers**: Git tags (`v*`), manual dispatch
- **Features**:
  - Automated changelog generation
  - GitHub release creation
  - Build artifact preparation

### 🔍 Code Quality (`code-quality.yml`)
- **Triggers**: Push to `main`/`develop`, PRs to `main`
- **Features**:
  - ESLint for JavaScript/TypeScript
  - Flake8, Black, isort, mypy for Python
  - SonarCloud integration
  - Codecov coverage reporting

### 📦 Dependency Check (`dependency-check.yml`)
- **Triggers**: Weekly schedule (Mondays), manual dispatch
- **Features**:
  - Outdated dependency detection
  - Security vulnerability scanning
  - Automatic issue creation for security concerns

## Usage

1. **Automatic**: Workflows trigger on pushes and PRs
2. **Manual**: Use "Actions" tab → "Run workflow" for manual execution
3. **Releases**: Create tags with `v*` pattern (e.g., `v1.0.0`)

## Configuration

Some workflows require secrets to be configured in repository settings:
- `SONAR_TOKEN`: For SonarCloud analysis
- `CODECOV_TOKEN`: For coverage reporting

The workflows are designed to be adaptive and will automatically detect your project type (Node.js, Python, etc.) and run appropriate steps.
