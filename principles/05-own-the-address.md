# 5. Own the address, rent the mailbox

**Portability beats loyalty.**

## The asymmetry

If your professional address ends in a provider's domain, your identity belongs to that provider. Lose the account, lose the address, and every client, contract and account that referenced it now points at nothing.

If it ends in a domain you control, the provider is a tenant. Switching mail hosts is a DNS change. Clients keep writing to the same address and never learn anything happened.

For a business, this is the single highest-leverage decision in the whole subject, and it costs about ten pounds a year.

## The obligation that comes with it

Owning the address means the domain is now load-bearing, and domain loss is the only failure in this entire field that is genuinely permanent. Accounts get appealed and restored. A lapsed domain that someone else registers is gone.

So:

- Renew for years at a time, not annually.
- Pay by card, not from an account balance that can silently run dry.
- Keep the registrar contact address verified. Registries can suspend a domain over an unverified contact, independently of anything else.
- Check the renewal card's expiry date as diligently as the domain's.
- Consider splitting critical domains across two registrars.

## Portability as a selection criterion

When choosing any provider, ask what leaving looks like before you ask what joining looks like:

- Can you export everything, in a standard format, without a support ticket?
- Are open protocols supported directly, without a proprietary bridge application?
- Does the data live in files you can read with other software?

A provider that makes leaving easy has to keep you by being good. One that makes leaving hard doesn't.

## The trade nobody names

Maximum confidentiality and maximum portability pull in opposite directions.

End-to-end encrypted providers genuinely cannot read your data. That same property means no open protocols, proprietary sync bridges, and a narrower exit.

Neither is wrong. But they answer different questions — *nobody can read this* versus *nobody can lock me out of this* — and you should know which one you are actually asking. Most people never notice they were asked to choose.

## Keep a local copy regardless

Repointing DNS restores delivery within minutes. It does nothing for twenty years of archived correspondence sitting on the old provider's servers.

Continuous local sync via open protocols covers that. Periodic frozen snapshots cover what sync can't — because sync reproduces deletions too.
