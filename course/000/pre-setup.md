# Pre-setup

1. Add pre-commit hooks to the repository.

   ```bash
   pip install pre-commit

   # Inside the repository directory.
   pre-commit sample-config >.pre-commit-config.yaml
   ```

2. Add markdown lint to the config (make sure you have `markdownlint-cli`
   installed first).

   ```yaml
   - repo: https://github.com/igorshubovych/markdownlint-cli
     rev: v0.27.1
     hooks:
     - id: markdownlint
   ```

3. Install pre-commit.

   ```bash
   # Inside the repository directory.
   pre-commit install
   ```
