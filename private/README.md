# private/ – not published

This directory holds only this file. The private working copy – the actual configuration, the real dependency map, the runbook with real account names – lives in a **separate folder outside this repository**, where git cannot see it at all.

**Nothing from that folder is ever committed to a public remote.**

## Why the split

The public half of this repository is about principles and is safe to share. The private half is a description of exactly where the valuable things are and which one is not yet fixed. Published, it is a reconnaissance document – the threat models explain why in detail.

## Why outside the repository, not just gitignored

`.gitignore` is a convention, not a boundary. One `git add -f`, one edited ignore rule, or one tool that copies the working tree, and the private material is in history – and git history is difficult to scrub. A sibling folder has no such failure mode. The ignore rule for `private/` stays in place as a second line of defence, not the first.

## Suggested contents of the private folder

- `dependency-map.md` – every account that matters, which address is on file, whether it uses SSO, and its current status
- `runbook.md` – the numbered steps for each scenario. Keep to one page. **Print it.**
- `inventory.md` – hardware keys and their locations, where the paper sheet lives, what is on each backup target
- `log.md` – what was changed and when. Useful for spotting drift, and it becomes the source material for anything you write publicly later.

## Handling

- Consider keeping the private folder in an encrypted container.
- The paper copies are the authority. The private folder is a convenience.
