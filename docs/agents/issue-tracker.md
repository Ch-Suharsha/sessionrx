# Issue tracker: GitHub

Issues and specs live in [Ch-Suharsha/sessionrx](https://github.com/Ch-Suharsha/sessionrx/issues). Use the `gh` CLI from this clone; it infers the repository from the Git remote.

## Conventions

- Create an issue: `gh issue create --title "..." --body-file <file>`. For multiline text, write the exact body to a temporary file first.
- Read an issue, including discussion: `gh issue view <number> --comments`. Fetch labels and other structured fields with `--json` when needed.
- List issues: `gh issue list --state open --json number,title,body,labels,comments`, with label and state filters as appropriate.
- Comment: `gh issue comment <number> --body-file <file>`.
- Apply or remove labels: `gh issue edit <number> --add-label "..."` or `--remove-label "..."`.
- Close: `gh issue close <number> --comment "..."`.

When a skill says "publish to the issue tracker," create a GitHub issue. When it says "fetch the relevant ticket," read the issue and its comments.

## Pull requests as a triage surface

**PRs as a request surface: no.**

## Ticket graphs and wayfinding

Use a parent issue for a spec or wayfinding map and link child tickets as GitHub sub-issues. If sub-issues are unavailable, list children in the parent issue and include `Part of #<parent>` in each child.

Use GitHub's native issue dependencies for blocking edges. To add an edge, call `gh api --method POST repos/Ch-Suharsha/sessionrx/issues/<child>/dependencies/blocked_by -F issue_id=<blocker-database-id>`. Obtain the database ID with `gh api repos/Ch-Suharsha/sessionrx/issues/<blocker-number> --jq .id`; it is distinct from the issue number and node ID. If native dependencies are unavailable, record `Blocked by: #<number>` in the ticket body.

The ready frontier contains open tickets whose blockers are all closed. Account for assignees before claiming a ticket with `gh issue edit <number> --add-assignee @me`.

For `/wayfinder`, use `wayfinder:map` for the map and `wayfinder:<type>` for child types. Resolve a decision with a comment and closure, then add a short answer and link to the map's decisions. Create any additional workflow labels only when that workflow is explicitly requested.
