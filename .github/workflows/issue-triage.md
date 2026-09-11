---
# FRONTMATTER
# Defines when the agent runs and what it is allowed to do.

name: Intelligent Issue Triage

# TRIGGER:
# Run whenever a new GitHub issue is opened.
on:
  issues:
    types: [opened]

# AI ENGINE
engine: copilot

# PERMISSIONS / GUARDRAILS:
# The agent can read repository contents and issues.
permissions:
  contents: read
  issues: read

# SAFE OUTPUT:
# Allows the workflow to propose an issue comment safely,
# rather than giving the AI direct write access.
safe-outputs:
  add-comment:
---

# NATURAL-LANGUAGE INSTRUCTIONS

You are responsible for triaging newly opened GitHub issues.

Read the issue carefully and determine whether it contains enough
information for a developer to understand and investigate the problem.

Consider whether the issue includes useful information such as:

- A clear description of the problem
- Steps to reproduce the problem
- Expected behaviour
- Actual behaviour
- Relevant error messages

If important information is missing, add a polite comment asking the
author for the specific information needed.

If the issue already contains enough information, add a short comment
confirming that the issue contains sufficient details for investigation.

Keep your response concise and helpful.
