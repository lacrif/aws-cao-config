# Repository agent guidelines

## Scope and source of truth

This document is the canonical, versioned guidance for AI agents working in
this repository. It applies throughout the repository unless a more-specific
instruction file in a subdirectory explicitly narrows its scope.

`AGENTS.md` and `CLAUDE.md` at the repository root are discovery entry points,
not independent policy documents. Keep shared instructions here so that agents
using either convention receive the same guidance without parallel copies.

## Repository context

This repository contains CAO feature-delivery profiles. Each Markdown file in
`profiles/` defines an agent profile; consult [README.md](../README.md) and the
profile being changed before editing. Preserve the human-gated workflow and the
role boundaries documented there.

## Instruction precedence

Follow instructions in this order when they conflict:

1. Platform, system, and tool instructions.
2. The current user request.
3. The closest applicable repository instruction file; a subdirectory file
   may add or override this document only for that subtree.
4. This document and the root entry points that reference it.
5. General project documentation, including `README.md`.

If two instructions at the same level conflict or their scope is unclear, stop
and ask the human rather than choosing one arbitrarily.

## Working conventions

- Keep changes focused on the requested profile or documentation.
- Do not weaken the required human approval gates or role restrictions.
- Update relevant documentation when a profile's behavior, required inputs, or
  workflow changes.
- Preserve unrelated user changes in the working tree.

## Maintenance and verification

When changing shared agent guidance, edit this file first. Update a root entry
point only when its link, scope statement, or agent-specific bootstrap detail
needs to change; do not copy shared rules into it.

Before handing off an instruction change, verify that:

- links from both root entry points resolve to this file;
- the shared guidance exists only here;
- any deeper instruction file declares its scope and does not silently
  contradict a higher-precedence instruction; and
- the guidance remains consistent with the repository's `README.md` and the
  affected profile.

If a particular agent cannot follow a Markdown reference, add only the minimum
imperative bootstrap text required for that agent, label it as a compatibility
exception, and keep it byte-for-byte aligned with the corresponding canonical
text above.
