# 6. An unrehearsed plan is an intention

**If you have never restored it, you do not have it.**

## Why untested plans fail

They fail at the moment you need them, which is the worst possible time to discover:

- The backup has been silently erroring for four months.
- The archive is there but the software that reads it isn't.
- The recovery codes were regenerated and the printed copy is stale.
- The step you assumed would take five minutes needs a support ticket and a business day.

None of these are visible from a green tick on a dashboard. Only a restore reveals them.

## What to rehearse, and how often

**Every quarter — restore a real file.** Not "check the job succeeded". Pull something from six months ago off the backup, open it, confirm it is intact. Two minutes.

**Once — rehearse the switch.** Whatever your fallback is, run it on a quiet weekend. If it is a mail provider, repoint MX to it for an hour, send yourself a test, then repoint back. You will find at least one thing you had wrong.

**Once a year — read the runbook cold.** Give it to yourself as though you had never seen it. Steps that seemed obvious when you wrote them are frequently not.

## Write the runbook for the worst version of you

You will be reading it panicked, possibly on a phone, possibly on someone else's computer.

- **Print it.** A runbook stored in the account you have lost is a joke you will not find funny.
- **Number the steps.** Prose does not survive stress.
- **Start with diagnosis.** Is it you or is it the provider? Two minutes with a private window and a status page changes what you do next.
- **State what you are *not* doing.** Knowing you don't have to notify every client, because you own the domain, is worth as much as any instruction.
- **Keep it to one page.** Anything longer will not be current.

## The honest accounting

Rehearsal also tells you the size of the gap you cannot close.

There will be a window between a failure starting and your switch completing where some data is genuinely lost. Knowing that window is twenty minutes rather than three days is the difference between a plan and a hope — and the only way to find out is to run it.
