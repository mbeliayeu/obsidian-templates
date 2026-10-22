# Home

Choose up to three outcomes for today in your daily note. Keep each commitment's checkbox in its original Project, Task, or Issue note.

## Projects

- [[Projects/Evaluations|Evaluations]]

![[Projects.base]]

## Next actions

```query
task-todo:(#next) -path:"Templates/" -path:"Archive/" -file:"README"
```

## Waiting for an answer

Review follow-up dates manually. Each waiting item should name who owes the answer, what you need, and when to chase it.

```query
task-todo:(#waiting) -path:"Templates/" -path:"Archive/" -file:"README"
```

## Capture to process

Move captured commitments into their owning note and leave a normal link back to it. Both daily logs and meeting notes can contain temporary capture.

```query
(path:"Daily/" OR [type:meeting]) task-todo:/.*/ -path:"Templates/" -path:"Archive/" -file:"README"
```

## All unfinished commitments

The weekly safety net: includes actions without either tag, across projects and supporting notes.

```query
task-todo:/.*/ -path:"Templates/" -path:"Archive/" -file:"README"
```

## Start here

- [[README|How to use this vault]]
- [[Notes/OmniDocBench eval|Starter evaluation task]]
- Create a Project in `Projects/`; create a Task, Paper, Issue, Meeting, Decision, or Context note in `Notes/`.
- Title the note, insert its template, and fill its `project` property with a real project link.
