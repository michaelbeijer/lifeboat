# Registrar or DNS failure

**The most under-rated threat in this list, and the only one that can be permanent.**

## Why it is worse than it sounds

Every other failure here is recoverable given enough time and persistence. A suspended account gets appealed. A destroyed machine gets replaced from backup.

A domain that expires and is registered by someone else is gone. There is no appeal, because nothing went wrong — you simply stopped paying, and the system worked as designed.

And your domain is the thing that made everything else portable.

## The realistic causes

Not attackers. In order of likelihood:

1. **An expired card on file.** Auto-renew is on, the charge declines, the failure notice goes to an inbox you are not reading, and the domain lapses.
2. **Renewals drawn from an account balance** that quietly runs dry. Auto-renew being enabled does not mean funds exist.
3. **Unverified registrant contact.** Registries can suspend a domain when the contact email fails verification — independently of payment or anything else.
4. **The circular dependency**, so you cannot get into the account to fix any of the above.

Every one of these is administrative. None involves anyone attacking you.

## Controls

- Registrar account email on the independent recovery identity ([principle 1](../principles/01-circular-dependencies.md))
- **Both** the account address and the per-domain contact address updated — they are separate fields
- Card, not account balance; check its expiry against the renewal date
- Register for five to ten years
- Registrar lock enabled
- Two-factor on the registrar, with backup codes on paper
- DNS hosted separately from the registrar, so a problem at one does not freeze the other
- Critical domains split across two registrars

## Diagnostic

Look at the renewal notices for each domain you own. Which address did they go to? Which card is on file, and when does it expire?

Most people cannot answer either question. Both are two minutes of work and they are the highest-value two minutes in this repository.
