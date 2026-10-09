# google-dev-style

A [Claude Code](https://claude.com/claude-code) skill that makes Claude write the way
the [Google developer documentation style guide](https://developers.google.com/style/)
says to write: answer first, active voice, present tense, no filler.

It applies to chat replies, status updates, explanations, READMEs, commit messages,
and anything else Claude writes for you.

## Before and after

Before:

> Great news! I just went ahead and fixed the deploy script. Basically the issue was
> that it was using the wrong node version, so it will now simply use node 20. You
> should be good to go, let me know if you hit any snags!

After:

> The deploy script now uses Node.js 20. The previous version pinned Node.js 16, which
> Firebase no longer supports. To confirm the fix, run the deploy:
>
> ```bash
> npm run deploy
> ```

## Install

Clone the repository into your personal skills folder:

```bash
git clone https://github.com/aaronparsons-dev/google-dev-style ~/.claude/skills/google-dev-style
```

Claude Code loads skills when a task matches the skill's description. To apply the style
to every reply, add this to `~/.claude/CLAUDE.md` (create the file if it doesn't exist):

```markdown
Write every reply in Google developer documentation style. Read and apply the
`google-dev-style` skill at `~/.claude/skills/google-dev-style/SKILL.md`.
```

To apply it to one project only, put the same lines in that project's `CLAUDE.md`.

### Claude.ai

Claude.ai doesn't read Claude Code files. Upload `SKILL.md` as a skill under
**Settings > Capabilities > Skills**, or paste its "Applying this in chat" section into
**Settings > Profile > Personal preferences**.

## What's inside

| File | Purpose |
|---|---|
| `SKILL.md` | The rules: voice and tone, structure, lists, code and UI formatting, notices, and common word fixes. |
| `references/word-list.md` | About 130 word-list entries grouped by category. Claude reads it when it needs a specific term. |

## The rules in brief

- Lead with the answer. Background comes after, if at all.
- Address the reader as "you". Use active voice and present tense.
- Use sentence case for headings, serial commas, and American spelling.
- Put code, filenames, and commands in code font. Put UI elements in bold.
- Use numbered lists only for sequences, one action per step.
- Cut filler: "just", "simply", "easy", "please", "note that", "currently", "will".
- Don't use exclamation points, metaphors, or slang.

## Update

```bash
git -C ~/.claude/skills/google-dev-style pull
```

## Contributing

Open an issue or pull request. When adding a word-list entry, link the matching entry
on the [Google word list](https://developers.google.com/style/word-list) so the source
stays traceable.

## License

MIT. See [LICENSE](LICENSE). The rules are adapted from Google's style guide, which is
published under
[Creative Commons Attribution 4.0](https://creativecommons.org/licenses/by/4.0/).
Google isn't affiliated with this project.
