---
description: Leave a proposal in your töre inbox (a task result, decision, question, task, note or objection). Nothing is adopted until you review it in töre.
argument-hint: "[what to propose]"
allowed-tools: mcp__plugin_tore_tore__tore_list_topics, mcp__plugin_tore_tore__tore_get_topic, mcp__plugin_tore_tore__tore_propose
---

Leave one proposal in the person's töre inbox. Request: $ARGUMENTS

1. Decide the topic. Use the topic already being worked on in this conversation; otherwise call `tore_list_topics` and ask. Only topics that allow proposals can receive one; if it does not, say so and stop.
2. Decide the kind: `note` (a result or finding), `decision`, `question`, `task` or `objection`. An objection must name the record it objects to (`relatesTo`, a record id from `tore_get_topic`). A result of an open task should use `relatesTo` with that task's id.
3. Write the text in the person's language, self-contained and short. Mark what the person said and what is your suggestion. Never write that a task is closed or done; the person closes tasks in töre.
4. Show the person the topic, the kind and the exact text, and ask for a yes before sending.
5. Call `tore_propose`. Report that it waits in töre's **Gelen kutusu** and is not part of the notebook until they accept it; an accepted proposal stays an unreviewed AI proposal until they review it.
