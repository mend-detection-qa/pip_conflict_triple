# Test Case: Pip Triple Priority Conflict

## Package Manager
Pip

## Python Version Detection
- **Source**: .python-version (PRIORITY #1)
- **Expected Version**: 3.7.12
- **Conflicts**:
  - .tool-versions says 3.8.5 (PRIORITY #2 - IGNORED)
  - pyproject.toml says >=3.9 (PRIORITY #3 - IGNORED)

## Files Present
- .python-version - 3.7.12 (SHOULD WIN)
- .tool-versions - python 3.8.5 (SHOULD BE IGNORED)
- pyproject.toml - requires-python = ">=3.9" (SHOULD BE IGNORED)
- requirements.txt

## Test Purpose
Stress test: Three conflicting version sources. Validates priority #1 wins.
