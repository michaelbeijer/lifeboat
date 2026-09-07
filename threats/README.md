# Threat models

Each file describes a failure, what it actually takes from you, and which principles apply.

These are ordered by a rough product of likelihood and damage, not by how dramatic they sound. The mundane ones do more harm.

| Threat | Likelihood | Recoverable? |
|---|---|---|
| [Identity provider lockout](identity-provider-lockout.md) | Low, but non-zero and rising | Usually, slowly |
| [Registrar or DNS failure](registrar-failure.md) | Higher than you think | **Sometimes not** |
| [Machine loss](machine-loss.md) | Moderate | Yes, if offsite exists |
| [Ransomware and credential theft](ransomware-and-stealers.md) | Moderate | Yes, with immutable snapshots |
| [Local AI agent overreach](agent-overreach.md) | Rising fast | Confidentiality: no |
| [Vendor withdrawal](vendor-withdrawal.md) | Low per vendor, certain in aggregate | Yes, with notice |

Note the second row. Domain loss is the only entry here that can be permanent, and it is caused by an expired card rather than an attacker.
