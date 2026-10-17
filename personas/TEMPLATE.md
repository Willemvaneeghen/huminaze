# Persona template

A persona describes one writer's attitude, biases, tone, and word habits. Anchors written by the user show how that writer really sounds. Read this file when you add, update, or delete a persona.

## Format

Each persona is one Markdown file named `<name>.md`, with 600 words or fewer.

```markdown
---
name: <name, matching the file name>
description: <one line: who this writer is>
---

# <Display name>

## Attitude and biases
- <What this writer trusts, distrusts, likes, and won't say>

## Tone
<Formality, warmth, humor, and bluntness, in a sentence or two>

## Word habits
- <Sentence length, pet words, words they never use>
- Keeps on purpose: <tells this writer uses on purpose, or "none">

## Adapts to context
- <Kind of text or reader>: <how the voice shifts>

## Anchors

### <A question or scenario put to the persona>
> <The user's answer, word for word>
```

## Rules

- `name` is a short lowercase slug, such as `grumpy-sysadmin`, and matches the file name.
- The five `##` headings are required, in the order above.
- Biases are tastes and leanings, not facts. "Distrusts hype" is allowed. "Postgres is faster than MySQL" is not, because a rewrite would have to state it as fact.
- "Keeps on purpose" is the only way around a pattern in `SKILL.md`. Each tell listed there must appear in an anchor. All other patterns still apply.
- "Adapts to context" says how the voice shifts by kind of text, such as a PR, an email, or a blog post, and by reader, such as a peer or a boss.

Anchors are the ground truth for the persona's voice:

- A persona has 2 to 5 anchors. Each is a `###` question followed by a `>` block quote answer.
- The user writes every answer. Never write or polish an answer for them. Store it word for word.
- Anchors outrank the other sections. If an answer shows a habit the traits do not list, such as dashes or a pet phrase, update the traits to match. A tell an answer uses goes under "Keeps on purpose".
- Anchors show voice, not content. Never copy a fact from an anchor into a rewrite.

## Add a persona

1. **Collect traits.** Take attitude, biases, tone, word habits, and contexts from the conversation and any writing samples. Ask only about gaps, in a few short questions at most.
2. **Ask anchor questions.** Draft 3 to 5 questions aimed at the traits: one for each main context, one that tests a bias, and one that tests tone under pressure, such as bad news, disagreement, or a mistake. Ask them one at a time and tell the user to answer as the persona. The user may skip a question or ask for another. Record each answer word for word. Do not save the persona until at least 2 questions have answers.
3. **Refine the traits** so they match what the answers show.
4. **Check the draft.** Biases are tastes, not facts. The headings follow the format. The file has 600 words or fewer.
5. **Show the full file** and wait for the user's approval.
6. **Save it** as described below, and tell the user the full path.

## Where to save

- If the skill folder contains `.git`, save to `personas/local/<name>.md` in the skill folder. Git ignores this folder, so the persona stays private and survives updates.
- Otherwise, save to `~/.humanizer/personas/<name>.md`. A plugin or copied install can be replaced on update, so the skill folder is not safe.
- Create the folder if it is missing.
- If neither place can be written, show the finished file and tell the user to save it in one of those folders.

## Update or delete

- **Same name as a starter:** allowed. The user's persona overrides the starter. Say so.
- **Same name as one of the user's personas:** ask whether to replace it or choose another name.
- **Update:** follow the steps above on the existing file, and show the changes before saving. You may add anchors. Never edit an existing answer.
- **Starters:** never edit a starter in `personas/` in place. To change one, copy it to the user's folder under the same name, then update the copy.
- **Delete:** ask the user to confirm, then remove the file. Starters cannot be deleted.
