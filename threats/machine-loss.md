# Machine loss

**Fire, theft, drive failure, liquid, or simple old age.**

## Why the obvious answer is usually wrong

"It's backed up to my NAS" is a good answer to drive failure and a poor answer to everything else, because the NAS is in the same building as the machine.

One fire, flood, surge or burglary takes both. A NAS is a conspicuous box of electronics next to a conspicuous computer.

If the only offsite copy is a cloud provider you are also trying to become independent of, the risks are correlated: losing that provider removes your protection against the physical disaster, and vice versa.

## What actually needs to survive

- Client deliverables and working files
- Translation memories, glossaries, termbases — often irreplaceable, and often overlooked because they live inside application directories rather than in Documents
- Local mail and contact archives
- Source code and repositories not yet pushed anywhere
- Licence files and activation records
- The printed recovery sheet, which should not be in the building either

## The arrangement

- **Scheduled backup with versioning** to local storage — fast restore for the common case
- **An offsite copy pushed from that storage**, not from the workstation
- **Encryption with a key you hold**, decided before the first upload
- **Full-disk encryption** on the machine itself, so theft is a hardware loss rather than a confidentiality incident
- **Periodic frozen snapshots** that nothing upstream can reach back and alter

## Test it

Restore something from a year ago and open it. Quarterly.

Most backup systems that have never been restored from do not work, and the owner has no idea. This is not pessimism; it is the ordinary result of never checking.
