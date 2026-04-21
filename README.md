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

Maintenance rule:

- if fixture content changes and a pinned self-ref should now point to that new
  state, add a follow-up commit that updates the SHA
- the committed fixture graph must always be intentional
- the test repository expectations must match that committed fixture graph

In practice:

1. change fixture content
2. decide which pinned self-refs should move to the new commit
3. commit the SHA updates
4. update the test repository expectations if the observed graph changed
