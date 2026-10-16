# Working style

*Shared rule: an identical copy sits in `.claude/rules/family/` of every ume repo. Change all copies together (`family/family.md`).*

How to approach any change. The repo's own rules win wherever they are more specific: they decide layout, comments, types and checks. "Match the existing style" means match those rules, not strip what they require (banners, `%` bars, `--- @class`, required splits).

## Think before coding

- Ask when the request leaves a product choice open: which system, which environment, which id, what a player or user sees. Don't ask about what a rule already decides; read the rule and apply it.
- State the assumptions you make. When a request has several readings, name them instead of picking one silently.
- If a simpler design meets the request and the rules, say so before building the larger one. If something is unclear, name the gap and stop.

## Simplicity

- Ship the request. No features, settings, options, fallbacks or abstractions nobody asked for.
- No error handling for cases that can't happen. Fail fast where the repo's rules say so.
- If 200 lines could be 50, write 50.

## Surgical changes

- Every changed line traces to the request, or to a rule on a line the request made you touch.
- Leave untouched code, comments and formatting alone. Don't refactor what isn't broken.
- A function you edit follows the rules in full. Don't restyle the rest of the file to get there.
- Remove the locals, imports and functions your change made unused. Mention unrelated dead code; delete it only when asked.

## Checks

- Before calling a change done, run a check that exists in this repo: the commands in its testing or tooling rule, a build, or an observable in Studio or the editor. "Make it work" is not a check.
- For multi-step work, state a short plan with a check on each step:

```
1. [Step] → verify: [check]
2. [Step] → verify: [check]
```

- Say what you verified and what you couldn't.
