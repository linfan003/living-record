# Living Record protocol

Version 0.1

This protocol says which personal records an agent may rely on before making a judgment for a person. It is not a memory database, not a voice imitation, and not a way to keep speaking for someone who can no longer confirm the record.

The `SKILL.md` format is defined by [agentskills.io](https://agentskills.io). How several sessions share a folder is defined by [session-canon](https://github.com/linfan003/session-canon).

## 1. Terms

| Term | Meaning |
|------|---------|
| Record | One Markdown file under `records/`. One matter per file. |
| Scope | The kind of question this record may inform. For example `work`, `health`, `money`, `home`. |
| Source | Where the sentence came from: the person said it, a file the person keeps, or an inference. |
| Review date | After this date the record is not automatically usable. |
| Judgment | A choice or recommendation. It lists the record paths it used. |

## 2. Eight rules

1. **Cite, then judge.** The answer lists the relative path of each record it used. Without that list, it must not claim the judgment comes from the person's record.
2. **Six fields.** One sentence, scope, source, recorded date, review date, status. A record missing any field cannot be used.
3. **Scopes stay apart.** Read only records in the scope of the current question. Cross a scope only when the person explicitly allows it for this question.
4. **What the person said wins.** Inside one scope, an inference does not override a record the person stated or a file they keep. An inference used on its own is labeled as an inference, and the agent asks before acting on it.
5. **Expired means unused.** If the status is not "active", or the review date is before today, leave the record out of the judgment. It may be listed as "needs review".
6. **Show conflicts.** If two active records in the same scope disagree, show both, with their dates and sources. Do not average them and do not hide one.
7. **Short, and owned by the person.** Paths are relative, with forward slashes. No secrets, account numbers, or a dump of every chat. The person keeps the files.
8. **No continuation without the person.** Use this protocol only while the person can confirm records. It does not write a testament, copy a voice, or train a stand-in.

## 3. Layout

```
<record-root>/
├── AGENTS.md
└── records/<one-matter>.md
```

## 4. Record

```markdown
# <one sentence>

- Scope: work
- Source: person-said
- Recorded: YYYY-MM-DD
- Review: YYYY-MM-DD
- Status: active

## Body

A passage that can be quoted.

## Retired by

Relative path of the newer record, if this one was replaced. Otherwise empty.
```

Source is one of `person-said`, `person-file`, `inferred`.

Status is one of `active`, `needs-review`, `retired`.

A person-file record names the relative path of that file. An inferred record names the record or observation it rests on. If it has no basis, do not create it.

## 5. Order of a judgment

1. Name the scope. If it is unclear, ask.
2. Open only active records in that scope whose review date is today or later.
3. If they conflict, show the conflict and stop before a single recommendation.
4. When recommending, attach each record's path, source, and review date.
5. If no record applies, say so. Answer the question as an ordinary question and mark that part as unsupported by the personal record.

## 6. Changing a record

- The fact changed: add a new record, set the old status to retired, and point "Retired by" at the new file. Do not overwrite the old body.
- The record was wrong: do the same.
- The review date has passed: set the status to needs-review. If the person confirms it, move the review date forward and set the status back to active. If they reject it, retire it.

## 7. Out of scope

- Automatically extracting a complete personal archive from chat.
- Merging scopes into a personality sketch.
- Writing an inference down as something the person said.
- A mode that keeps answering after the person can no longer confirm records.
