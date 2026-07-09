---
on:
  schedule: daily on weekdays
permissions:
      contents: read
engine: copilot
network:
  allowed:
    - defaults
    - node
safe-outputs:
  create-issue:
    max: 1
---

# daily-digest

Every weekday morning, create a GitHub issue that summarizes all open
issues and pull requests in this repository. Group them by label
(issues without labels go in an "Untriaged" section). For each item
include the title, the author, and how long it has been open. Start
with a one-paragraph summary of the overall state of the repo.
Title the issue "Daily Digest – <date>".

<!--
## TODO: Customize this workflow

The workflow has been generated based on your selections. Consider adding:

- [ ] More specific instructions for the AI
- [ ] Error handling requirements
- [ ] Output format specifications
- [ ] Integration with other workflows
- [ ] Testing and validation steps

## Configuration Summary

- **Trigger**: Daily schedule (fuzzy, scattered time)
- **AI Engine**: copilot
- **Safe Outputs**: create-issue, update-discussion, close-discussion, close-issue
- **Network Access**: defaults,node

## Next Steps

1. Review and customize the workflow content above
2. Remove TODO sections when ready
3. Run `gh aw compile` to generate the GitHub Actions workflow
4. Test the workflow with a manual trigger or appropriate event
-->
