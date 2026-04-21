# ensure-immutable-actions Test Custom Actions

This repository provides remote targets for manual validation of
`Wuodan/ensure-immutable-actions`.

## Remote targets

- `composite-actions/parent`
- `composite-actions/leaf`
- `.github/workflows/reusable.yml`

These are consumed by `Wuodan/ensure-immutable-actions-test`.

## Pinned Self-Refs

Some fixtures in this repository intentionally reference this same repository
by full commit SHA. That is part of what the live test suite validates.

This has an important maintenance consequence:

- if fixture content changes and a pinned self-reference should now point to the
  new fixture state, a follow-up commit must update that SHA
- the branch tip and the pinned SHAs inside the branch do not need to match at
  every commit, but the committed fixture graph must always be intentional
- the test repository expectations must match the committed fixture graph of the
  selected fixtures branch

In practice:

1. change fixture content
2. decide which pinned self-references should move to the new commit
3. commit the SHA updates
4. update the test repository expectations if the observed graph changed
