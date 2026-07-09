---
on:
  workflow_run:
    workflows: ["CI"]
    types: [completed]
    branches: [main]
if: ${{ github.event.workflow_run.conclusion == 'failure' }}
permissions:
  contents: read
  actions: read
engine: copilot
network:
  allowed:
    - defaults
    - node
tools:
  github:
    toolsets: [default]
safe-outputs:
  create-issue:
    max: 1
---

# ci-doctor

When the "CI" workflow completes with conclusion "failure" on the main
branch, investigate the failure:
1) Download the logs of the failed jobs from that workflow run.
2) Identify which step and which test failed, and extract the relevant
   error message.
3) Read the failing test file and the source file under test to find
   the root cause.
4) Create an issue titled "CI failure: <short root cause>" containing:
   - a one-paragraph diagnosis in plain English,
   - the relevant log excerpt (trimmed to the essential lines),
   - the file and line where the bug likely is,
   - a suggested fix as a code snippet,
   - a link to the failed workflow run.
If an open issue for the same root cause already exists, do not create
a duplicate.

<!--
## TODO: Customize this workflow

The workflow has been generated based on your selections. Consider adding:

- [ ] More specific instructions for the AI
- [ ] Error handling requirements
- [ ] Output format specifications
- [ ] Integration with other workflows
- [ ] Testing and validation steps

## Configuration Summary

- **Trigger**: Manual trigger
- **AI Engine**: copilot
- **Tools**: github
- **Safe Outputs**: create-issue
- **Network Access**: defaults,node

## Next Steps

1. Review and customize the workflow content above
2. Remove TODO sections when ready
3. Run `gh aw compile` to generate the GitHub Actions workflow
4. Test the workflow with a manual trigger or appropriate event
-->
