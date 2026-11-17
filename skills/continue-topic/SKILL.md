---
name: continue-topic
description: Continue work from a töre topic. Use when the person asks to continue, pick up, resume or work on something "from töre", names one of their töre topics, or asks what is open in töre.
allowed-tools: mcp__plugin_tore_tore__tore_list_topics, mcp__plugin_tore_tore__tore_get_topic, mcp__plugin_tore_tore__tore_list_shared_contexts, mcp__plugin_tore_tore__tore_get_shared_context
---

# Continue from a töre topic

töre is the person's local notebook. You can only see the topics they explicitly opened to this tool, and you cannot change the notebook.

## Steps

1. Call `tore_list_topics`. If the person named a topic, pick the one that matches. If several match or none was named, show the titles with their open task and question counts and ask which one. If the list is empty, tell them to open a topic to the connected AI tool in töre (Konularım, Bağlı AI aracı) and stop.
2. Call `tore_get_topic` for that topic.
3. Report where they left off, in their language, keeping the labels apart:
   - **Adopted decisions and opinions**: what they decided. These are theirs.
   - **Open tasks**: work that is still to do. An open task is not done until they close it in töre.
   - **Open questions**: undecided. Never present an open question as a decision or an opinion.
   - **Unadopted AI suggestions**: if any appear, say they are suggestions the person has not adopted.
4. Propose the next concrete step, usually on an open task, and ask whether to start.
5. When work on a task produces a result, offer to leave it in töre's inbox with `/tore:propose`. Never say a task is closed; only the person closes it.

If the person refers to a prepared continuation context rather than a topic, use `tore_list_shared_contexts` and `tore_get_shared_context` instead.

## Rules

- Quote the person's records accurately and keep each quote attributed to its speaker.
- Do not infer beliefs, values or a political identity from the records.
- If a tool says the notebook could not be read and asks to reconnect, tell the person to run `/mcp`, choose `plugin:tore:tore`, then Reconnect.
