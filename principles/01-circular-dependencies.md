# 1. No circular dependencies

**The key to the box must not be inside the box.**

## The shape of the problem

A circular dependency exists when recovery for A runs through B, and recovery for B runs through A. Each looks fine on its own. Together they form a closed loop with no entrance.

The canonical example, and an extremely common one:

- Your domain is registered with a registrar.
- The registrar account's email address is a mailbox on that domain.
- The mailbox is served by whichever provider your MX records point at.
- Changing the MX records requires logging into the registrar.


```mermaid
flowchart LR
    M[Mailbox] -->|resets password for| R[Registrar]
    R -->|controls| D[MX / DNS]
    D -->|points at| P[Mail provider]
    P -->|serves| M
```

Lose the mailbox and you cannot reset the registrar password. Cannot reset the registrar password, cannot repoint the mail. The failure is total, and it is invisible until the day it isn't.

## Why it hides

Every individual link is a sensible decision made on a different day. Nobody sets out to build a loop. You use your work address for your registrar because it is your work address. You point your domain at your mail provider because that is what domains are for.

Loops are only visible when you draw the whole graph, which is why mapping comes before everything else.

## The fix

**One identity that depends on nothing else you own.**


```mermaid
flowchart LR
    X[Recovery identity<br/>elsewhere] -->|resets password for| R[Registrar]
    R -->|controls| D[MX / DNS]
    D -->|points at| P[Mail provider]
    P -->|serves| M[Mailbox]
    M -.-x R
```

The recovery identity depends on nothing in the loop, so the loop has an entrance.

Its requirements are unusual, and mostly the opposite of what makes a good working address:

- **On a provider's own domain**, not a domain you control. A domain is only as available as your registrar account and your last renewal payment. An address on the provider's own domain has no DNS dependency and no renewal you can miss.
- **At a different company** from the one it is protecting you against.
- **Never used for correspondence.** It exists to sit in account-recovery fields.
- **Not guessable.** It is the recovery address for your registrar and your bank. If it is `yourname@provider.com`, it is the first thing an attacker tries.

Then make it the account email for the accounts at the root of the tree: registrar, DNS, banks, tax authority, password manager.

## Second-order loops

Breaking the obvious loop often leaves smaller ones behind. Check specifically:

- **Your password manager's second factor.** If your authenticator app syncs to the identity provider you are escaping from, the vault you built to survive a lockout depends on the thing locking you out.
- **Recovery addresses on the recovery identity itself.** If the fallback mailbox sends its own password resets to the primary one, it is decorative.
- **Separate fields on the same account.** A registrar may hold both an account login address and a per-domain contact address. Changing one does not change the other.
- **Being someone else's recovery address.** If your mailbox is the recovery route for family members' accounts, your lockout is also theirs.

## The test

Pick any account that matters. Ask: *if I lost access to my primary email right now, what sequence of steps gets me back into this?*

If any step in that sequence requires the primary email, you have found a loop.
