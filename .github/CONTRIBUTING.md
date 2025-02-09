## CONTRIBUTING
The following items are the ways of working on code within 4th brain organization:

1. Git Workflow:
   - Default branch name is `main`
   - All branches must be protected and require a PR to change the code with at least one reviewer to approve
   - Work should happen on branches and should be `squash and merge` to main via PR
   - Branch naming should follow the convention:
     `feature/<feature_name>/` for example: `feature/marvin/parsing` or `features`
     `bug/<bug_number_in_github>` for example: `bug/112`
     The reasoning is to set up an easy way to search in git and GitHub
   - When creating commits that fix bugs, use the following commit message to autoclose the issue once it's merged: "Fixes #42", this commit message will close Issue number 42 once the code is merged. [docs](https://docs.github.com/en/issues/tracking-your-work-with-issues/using-issues/linking-a-pull-request-to-an-issue#linking-a-pull-request-to-an-issue-using-a-keyword)
1. Repositories are using [pre-commit](https://pre-commit.com/), as part of improving code quality, to use it properly, whenever a repository is cloned, use:
`pre-commit install`, this will automatically trigger it whenever you try to commit.
To run pre-commit before committing the code: `pre-commit run -a`
Note: If you have no other alternative, as last resort and have to bypass it, add the no verify flag:  `git commit -a -m"amazing code" --no-verify`
1. Linters should be included in pre-commit hooks to enforce usage.
1. Linters should be set to use fix option if possible, meaning, if there is an issue, it will fix it in the first run and in the second one it is already fixed and will pass the hook. For example: `ruff --fix`
1. Testing should happen on dev environment and not on prod environments.
1. PR are expected to be merged only when integration tests have passed successfully.
1. PR should have unit tests as much possible. Unit tests coverage should not go down with new PRs.
1. Every PR should make the code base a bit better.

### Code Review

The following are the guidelines when performing code review as well as asking for one:

1. Ideal wait time for a review is less than 24 hours, if it exceeds, ping someone specifically to review.
1. Focus on logic and less on syntax, leave syntax to linter/automation.
1. Always assume good intent
1. Don't just say what's wrong, add a suggestion on how to improve it
1. Leverage CODEOWNERS to get automated review included.

### Release

Releases are done via tagging of main.
Libraries and release tags must follow [Semantic Versioning](https://semver.org/)
For example: 0.1.3, if there is a bug fix, then the next one is 0.1.4, however if there is a new feature then it will become: 0.2.0

### Issues

When creating issues, it is crucial to provide as much context as possible so anyone would be able to pick up the work. It is crucial to set up proper labels to know what the issue is about for example:
1. When reporting a bug, the issue should have `bug` label
1. When creating a feature request, the issue should have `enhancement` label

