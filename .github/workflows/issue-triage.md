---
on:
  issues:
    types: [opened, reopened]
  reaction: "eyes"
permissions:
      contents: read
      issues: read
      pull-requests: read
engine: copilot
network:
  allowed:
    - defaults
    - node
tools:
  github:
    toolsets: [default]
safe-outputs:
  add-labels:
    max: 3
  add-comment:
    max: 1
---

# issue-triage

When a new issue is opened in this repository, triage it:
1) Classify it as one of: bug, enhancement, question, documentation.
2) Add the matching label.
3) Post a friendly comment that: greets the author by username,
   summarizes your understanding of the issue in one or two sentences,
   and — if it is a bug report missing reproduction steps, expected
   behavior, or environment details — politely asks for the missing
   information.
Keep the comment short and helpful. Do not close or edit the issue. Add an "eyes" (👀) reaction to the issue so the author knows it was seen.
Additionally, close the issue after triaging it.

<!--
## TODO: Customize this workflow

The workflow has been generated based on your selections. Consider adding:

- [ ] More specific instructions for the AI
- [ ] Error handling requirements
- [ ] Output format specifications
- [ ] Integration with other workflows
- [ ] Testing and validation steps

## Configuration Summary

- **Trigger**: Issue opened or reopened
- **AI Engine**: copilot
- **Tools**: github
- **Safe Outputs**: create-issue, close-issue
- **Network Access**: defaults,node

## Next Steps

1. Review and customize the workflow content above
2. Remove TODO sections when ready
3. Run `gh aw compile` to generate the GitHub Actions workflow
4. Test the workflow with a manual trigger or appropriate event
-->
