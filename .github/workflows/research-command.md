---
on:
   slash_command:
      name: research
      events: [issues, issue_comment]
   reaction: "eyes"
permissions:
      contents: read
engine: copilot
network:
   allowed:
      - defaults
      - github
      - "npmjs.com"
      - "pypi.org"
tools:
   web-fetch:
safe-outputs:
   add-comment:
      max: 1
---

# research-command

Create a slash command /research. When someone comments
"/research <library-or-topic>" on an issue, research the topic with a
focus on whether it is suitable for use in this project:
1) Fetch the official documentation or website and the GitHub
   repository page if one exists.
2) Summarize: what it is, current maintenance status (last release,
   activity), license, and rough maturity/popularity.
3) End with a short recommendation: adopt, evaluate further, or avoid —
   with one sentence of reasoning.
Reply as a comment on the same issue, formatted in Markdown with
sources linked. If no topic is given, reply with usage instructions.

<!--
## TODO: Customize this workflow

The workflow has been generated based on your selections. Consider adding:

- [ ] More specific instructions for the AI
- [ ] Error handling requirements
- [ ] Output format specifications
- [ ] Integration with other workflows
- [ ] Testing and validation steps

## Configuration Summary

- **Trigger**: Command trigger (/bot-name)
- **AI Engine**: copilot
- **Tools**: github
- **Safe Outputs**: add-comment
- **Network Access**: defaults,node

## Next Steps

1. Review and customize the workflow content above
2. Remove TODO sections when ready
3. Run `gh aw compile` to generate the GitHub Actions workflow
4. Test the workflow with a manual trigger or appropriate event
-->
