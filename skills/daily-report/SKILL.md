---
name: daily-report
description: Generate a daily standup report in English summarizing activities done in the current Claude Code session. Use when you need to report your progress, prepare for standup, or document what was accomplished.
---

# Daily Activity Report Generator

Generate professional daily standup reports in English based on activities completed in the current Claude Code session.

## Purpose

Create concise, well-structured reports for:
- Daily standup meetings
- Progress updates to team members
- Documentation of development work
- End-of-day summaries

## How to Use

### Generate report for current session
```
/daily-report
```

### With additional context
```
/daily-report focus on the API changes
```

## Report Format

The report follows the standard standup format:

### What I Did (Completed)
- List of completed tasks and accomplishments
- Files modified or created
- Features implemented
- Bugs fixed

### What I'm Working On (In Progress)
- Current tasks being worked on
- Pending items from this session

### Blockers / Notes
- Any issues encountered
- Questions that need answers
- Dependencies on others

## Instructions for Claude

When this skill is invoked:

1. **Analyze the current conversation** to identify:
   - Files that were read, edited, or created
   - Commands that were executed
   - Tasks that were completed
   - Problems that were solved
   - Any errors or blockers encountered

2. **Generate the report in English** using this template:

```markdown
## Daily Report - [Current Date]

### What I Did
- [Completed task 1]
- [Completed task 2]
- ...

### What I'm Working On
- [In-progress task 1]
- [In-progress task 2]
- ...

### Blockers / Notes
- [Any blockers or important notes]
- None (if no blockers)
```

3. **Writing style guidelines**:
   - Use past tense for completed items
   - Use present continuous for in-progress items
   - Be specific: mention file names, function names, features
   - Keep each bullet point concise (1-2 lines max)
   - Use technical but clear language
   - Group related items together

4. **If the conversation is empty or just started**, respond with:
   "No activities recorded yet in this session. Start working on some tasks and invoke /daily-report again to generate your standup report."

## Example Output

```markdown
## Daily Report - January 14, 2026

### What I Did
- Implemented user authentication flow in `src/auth/login.ts`
- Fixed bug in payment processing where decimal amounts were truncated
- Added unit tests for the new validation middleware
- Refactored database connection pooling for better performance

### What I'm Working On
- Completing the password reset functionality
- Reviewing the API documentation updates

### Blockers / Notes
- Waiting for design team input on the error message copy
- Need access to staging environment for integration testing
```

## Tips

- Invoke at the end of your coding session to capture all activities
- Use the report as a base and add any offline work manually
- Perfect for async standup updates in Slack/Teams
