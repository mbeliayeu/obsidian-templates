# Obsidian work vault

A small work vault for projects, substantial tasks, papers, issues, feature proposals, meetings, and decisions. It uses Obsidian's built-in features and core plugins.

## Open the vault

1. In Obsidian, choose **Open folder as vault** and select this repository.
2. Open [Home](Home.md), then bookmark it for easy access.
3. Explore [Evaluations](Projects/Evaluations.md) and its starter [OmniDocBench eval](Notes/OmniDocBench%20eval.md).

The starter evaluation has proposed actions and empty results. Replace them with your actual work.

## Structure

```text
Home.md                    Daily starting point and live task searches
Projects.base              Optional table of current project notes
Projects/                  One overview note per project
Daily/                     Date-named capture and meeting logs
Notes/                     Tasks, papers, issues, proposals, meetings, decisions, and context
Templates/                 Reusable note templates
Attachments/               PDFs, screenshots, and other files
Archive/                   Finished notes and projects
.obsidian/                 Shared core-plugin and vault settings
```

New notes default to `Notes/`. Create project hubs explicitly in `Projects/`. Daily notes go to `Daily/`, and attachments go to `Attachments/`. Empty folders contain `.gitkeep` files so they survive a clone.

## Choose a template

Create and title a note, then run **Templates: Insert template** from the command palette. Templates are inserted into the current note. Fill in or remove the bracketed prompts.

| Template | Use it for | Location |
| --- | --- | --- |
| [Project](Templates/Project.md) | An ongoing project with an outcome and related work | `Projects/` |
| [Task](Templates/Task.md) | A substantial piece of work, such as an evaluation, investigation, or implementation | `Notes/` |
| [Paper](Templates/Paper.md) | A paper's ideas, evidence, limitations, citations, and relevance | `Notes/` |
| [Issue](Templates/Issue.md) | A problem, blocker, discrepancy, or unresolved defect | `Notes/` |
| [Feature Proposal](Templates/Feature%20Proposal.md) | A proposed feature with evidence, scope, success criteria, and a review outcome | `Notes/` |
| [Meeting](Templates/Meeting.md) | A conversation with agreements and follow-ups worth keeping | `Notes/` |
| [Decision](Templates/Decision.md) | A consequential choice whose reasoning you may revisit | `Notes/` |
| [Daily](Templates/Daily.md) | Today's focus, quick capture, and chronological log | `Daily/`, created automatically by Daily notes |
| [Context](Templates/Context.md) | A reusable resource, explanation, or supporting note | `Notes/` |

Templates use only the core plugin's title, date, and time variables. The `project` property is filled in manually with a real link, such as `[[Evaluations]]`. It connects the note to its project in backlinks and graphs. For material that spans projects, link the additional projects in the body.

Use **Source mode** when editing templates so property placeholders are preserved. The date variable means the insertion date; correct it when recording an earlier event. For a backdated daily note, also correct the heading if needed.

## Where tasks belong

There are two levels of work:

- **A Task note** holds an outcome that needs context, resources, actions, and results. The OmniDocBench evaluation is an example.
- **A checkbox** is an individual commitment or next action inside a Project, Task, Issue, or Feature Proposal note.

Keep each commitment's authoritative checkbox in one note. A project hub links to its Task and Issue notes without copying their checklists. The Home searches include actions from both `Projects/` and `Notes/`.

Quickly capture new commitments in a Daily or Meeting note when needed. During review, move their checkboxes into the owning project, task, or issue, and leave a normal link to the destination. Meeting notes keep the discussion and agreements as history.

For example, an evaluation action might be:

```markdown
- [ ] Agree on the evaluation's acceptance criteria #next
```

After asking another team for an answer, record the waiting item on one line:

```markdown
- [ ] Waiting for the relevant team to confirm the comparison models — follow up YYYY-MM-DD #waiting
```

Fill in the real follow-up date. Link the person or team if you already have a useful note for them. Keep waiting boxes unchecked until the requested outcome arrives. In core task syntax, custom marks such as `[-]` count as completed; use `#waiting` on an ordinary unchecked box instead.

## Tags, properties, and links

- `#next`: an immediately actionable commitment. Aim for a short list, roughly one per active project; choose up to three outcomes for today.
- `#waiting`: an ask already sent. Name who owes the answer and include a follow-up date.
- `type`: the note's role, such as `project`, `task`, `paper`, or `issue`.
- `project`: a link to the primary project for a supporting note.
- `status`: the lifecycle of the whole note, not the status of every checkbox inside it.

Suggested note statuses:

| Note type | Statuses |
| --- | --- |
| Project | `active`, `on-hold`, `done` |
| Task | `planned`, `active`, `done`, `dropped` |
| Paper | `unread`, `reading`, `read` |
| Issue | `open`, `investigating`, `resolved`, `dropped` |
| Feature Proposal | `draft`, `proposed`, `accepted`, `deferred`, `rejected` |
| Decision | `proposed`, `accepted`, `superseded` |

These are simple conventions, not enforced states. Completing a Task note's status does not check off its actions. Resolve or deliberately drop the remaining checkboxes before finishing or archiving it. Keep future possibilities as ordinary bullets under **Later** until you commit to them.

Use links for projects, meaningful related notes, and recurring people or teams. Add a separate note when it needs its own context, evidence, reuse, or history; a short question or URL can stay in the parent note. No separate Evaluation template is needed: start with Task and adapt its Setup and Results sections.

Use Feature Proposal to explore and review a change before committing to implementation. Start at `draft`, move to `proposed` when ready for review, and record the outcome. Once accepted, link the Task or Jira ticket that owns implementation. A separate Decision note is useful when the choice and its reasoning deserve their own history.

## The daily and weekly routine

**Daily, about five minutes:**

1. Open today's Daily note with **Daily notes: Open today's daily note**.
2. Process unchecked capture from earlier daily or meeting notes.
3. Review Home's waiting items and follow up on dates that have arrived.
4. Scan your project hubs and choose up to three outcomes for today. Link back to their source notes rather than copying checkboxes.
5. Complete actions in their original notes.

**Weekly, about twenty minutes:**

1. Scan Jira, flagged emails, and relevant Teams conversations for missed promises.
2. Review each project's outcome, next action, open questions, and blockers.
3. Scan Home's **All unfinished commitments**, including untagged items.
4. Revisit **Later** and promote only work you actually intend to do.
5. Resolve, drop, or transfer remaining commitments before moving finished material into `Archive/`.

Jira remains the team's record of delivery status. Obsidian holds your own actions, follow-ups, and context, with source links where available. Follow-up dates in checkbox text are plain text: review them manually. Core Search does not sort individual task dates or schedule notifications.

## Graphs, backlinks, and the project table

Open a project's **local graph** at depth 1. Increase to depth 2 to explore shared tasks, papers, issues, people, or teams. The graph's saved global filter hides Templates, Daily, Archive, and this README; global tags, attachments, and unresolved links are hidden initially. If Daily history is useful in a particular graph, remove that filter there.

Backlinks are configured to appear below notes. They also remain available in the sidebar. Explicit project links make daily logs and supporting notes discoverable from the project. Links between a Paper, Task, and Issue explain where evidence is used and what a problem affects.

Graph nodes represent notes, not the individual checkboxes. Write dependency meanings in the note text. For example, an Issue can say that it blocks a linked Task.

`Projects.base` is an optional core Bases table of project notes and their statuses, embedded in Home. It does not aggregate individual checkbox tasks. If your Obsidian version does not support Bases, open the ordinary project links instead.

## Vault configuration

The shared settings enable the core plugins used here, configure Templates and Daily notes, and set default note and attachment folders. No community plugins or custom scripts are required. Workspace state and device-specific files are ignored by Git.

If Obsidian is already open while these settings are added, reopen the vault to load them. Check that **Templates → Template folder location** is `Templates` and **Daily notes → Template file location** is `Templates/Daily.md`.

## Possible additions to discuss

Meeting and Decision are included because they preserve agreements and reasoning. The next candidates are:

| Candidate | When it earns a separate template | Simpler starting option |
| --- | --- | --- |
| Person or Team | You repeatedly prepare agendas or chase the same stakeholders across projects | A normal note with contact context and useful backlinks |
| Weekly Review | The review needs a repeatable written record | Follow the routine above |
| Experiment or Run | One Task has many runs with different configurations and large result sets | The Task's Results table and artifact links |
| Resource | Many non-paper sources need consistent source metadata and quotations | Context, or a link under References |

Start with Person/Team if meeting preparation is still hard, or Weekly Review if commitments continue to escape the review. Keep Experiment/Run as a possible specialization of Task rather than adding it for every evaluation.

## Official references

- [Core plugins](https://obsidian.md/help/plugins)
- [Templates](https://obsidian.md/help/plugins/templates)
- [Daily notes](https://obsidian.md/help/plugins/daily-notes)
- [Search and embedded queries](https://obsidian.md/help/plugins/search)
- [Properties](https://obsidian.md/help/properties)
- [Internal links](https://obsidian.md/help/links)
- [Graph view](https://obsidian.md/help/plugins/graph)
- [Backlinks](https://obsidian.md/help/plugins/backlinks)
- [Bases](https://obsidian.md/help/bases)
