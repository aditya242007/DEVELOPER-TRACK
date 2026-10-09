# DevTrack — Git Workflow

## Main branch
Keep main in a working, reviewed state.

## Start a task
git switch main
git switch -c feat/short-feature-name

Use feat/, fix/, docs/, or chore/ branch prefixes as appropriate.

## Review changes
git status --short
git diff
git diff --check

Stage only intended files:
git add path/to/file

Review staged changes:
git diff --cached
git diff --cached --check

## Commit
Use concise, descriptive messages.

Examples:
feat: add project listing endpoint
fix: reject unauthorized issue updates
docs: document session architecture

## Finish a task
Record the changes, actual test results, known bugs, and remaining
work. Push the branch and use pull-request-style review when possible.

Never commit secrets or claim checks passed without running them.
