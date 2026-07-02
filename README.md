# rnd-the-fe

## WHAT I DID

1. vite, mui, tanstack/table/router/query, reach hook form
2. Rewrote stocktake page as a vertical slice with table input cells
3. Iterated and tested for a bit. chrome MCP referencing old app and claude checking old code of course
4. Ultracode replicate several other pages quickly
5. Change out mui for shadcn and tailwind
6. add line edit modal and new stock take button for stocktakes

99/89/100/82 lighthouse on 5000+ line stock take release build
old client initial gzip >1MB, this 200KB
Slow and horrible to quite fast! Much less cumulative layout shift, when the page loads it just pops in without everything rearranging multiple times.

### References

[reference doc](https://docs.google.com/document/d/1kkXyCc2Pf1McYCYDE5_ppvOCMEufVD1E2Z3Rlj0ayPk/edit?tab=t.0#heading=h.gokx2jgewyyw)

[that cli tool Craig suggested](https://github.com/szymdzum/browser-debugger-cli)

[bench-prompt.md](bench-prompt.md)

[reference data file](https://drive.google.com/drive/u/1/folders/1QJnS9_l5PQHUSUOD2ULrthkQMuSZnwQB), stocktake: 019f17d0-1444-795c-ac53-da2216c73cff, store_id: 5B28901C52396E4BB098B9862CCF5DF9, use v3.0.0-RC branch, enable in yaml: `debug_no_access_control: true`.

### Stocktake page

If I (Andrei) was implementing it, I would go step by step, measure performance stats and observing what updates when

- Create basic table
- graphql/codegen
- Filter
- Filter in url parameter
- Add checkbox on each row and delete button, delete button deletes selected row
- Add modal for editings stock lines
- After edits in modal table updates

### Examples of things/areas, as an alternative

- Auth and shell, how it's gated and routed, including initialisation (use this PR)
- Lighter version of JSON forms
- How to use AI for performance tests/evaluation
- Design pattern <-> implementations (how to keep those in sync, leverage AI)
- Plugins with vite
- What packager to use ?
