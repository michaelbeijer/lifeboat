# Ransomware and credential theft

Two different threats, frequently conflated, with different mitigations.

## Ransomware

Encrypts your files and demands payment. Loud, obvious, and **the mitigation is backups, not antivirus.**

Assume detection fails. The question is not whether malware gets in; it is whether your snapshots survive it.

Modern ransomware hunts for backup targets specifically — network shares, cloud sync folders, attached drives. Destroying the recovery path is what makes the extortion work.

So the control is [least privilege](../principles/03-least-privilege.md): a dedicated backup account with write-but-not-delete rights, retention managed on the storage device under separate credentials, and immutable snapshots where available.

With that in place, ransomware is an annoying afternoon. Without it, it is a business-ending event no matter how good the backup schedule looked.

## Infostealers

Quieter, more common, and for many small businesses more dangerous.

They do not encrypt anything. They copy browser-saved passwords, session cookies, and API keys, then leave. You may never know.

**Backups do not help at all.** The mitigations are entirely different:

- Credentials in a password manager, not the browser. Browser stores are the first place these tools look.
- Session cookies bypass two-factor entirely — a stolen session skips the login. 2FA guards the door, not the room.
- API keys in environment variables or a secrets store, never in files or repositories.
- Caution with trial software, installers, and unfamiliar packages. This is the primary vector, and it disproportionately affects people who install a lot of tools.

## Two habits that matter more than any product

**Never leave plaintext credential exports on disk.** Password manager migrations produce CSV files containing every password you own. Delete them immediately, empty the recycle bin, and confirm they did not sync anywhere. Treat one as an emergency until it is gone.

**Assume the built-in antivirus is adequate and spend the effort elsewhere.** Independent testing has put the major free option at parity with paid suites for years. Software you argue with is software you eventually disable — and a disabled control protects nobody.
