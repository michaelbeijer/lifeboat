# 3. Least privilege, everywhere

**Every process gets the narrowest access that lets it do its job, and nothing more.**

The most transferable idea here. It appears in places that look unrelated until you notice they are the same shape.

## Backups

A backup job needs to **write** new files. It does not need to **delete** old ones.

If the credentials saved on your workstation can delete or expire snapshots, then malware that owns the workstation owns the backups too. Modern ransomware searches for backup targets specifically; destroying the recovery path is the point of the exercise.

Give the backup job a dedicated account with append-only rights. Manage retention on the storage device itself, under an admin account whose password is not stored on the machine being backed up. Where the platform supports immutable or locked snapshots, use them.

The change is small. It converts a catastrophe into an inconvenient afternoon.

## Local AI agents

A coding agent typically has read access to your entire home directory by default, with writes restricted to the working directory. That default lets it read credential files, SSH keys, and whatever happens to be sitting in Downloads.

Most of the time this is convenient. Occasionally it is a confidentiality breach — and if you hold client material under NDA, it is one your clients would care about.

- Deny reads on directories the agent has no business in: Downloads, client work, anything holding credentials.
- Restrict network access to an explicit allowlist, so a hijacked agent cannot exfiltrate what it read.
- Use OS-level sandboxing rather than clicking "approve" repeatedly. Approval fatigue is a real failure mode.
- Keep the runtime updated. Sandbox escapes are a live bug class.

## Account access

- Revoke third-party app authorisations you are not actively using. Each is a standing grant that survives password changes.
- API keys belong in a secrets store or environment variables, never in files or repositories.
- Prefer scoped tokens over full-account credentials.

## The common shape

In each case the question is the same: *what is the minimum this needs, and what does it currently have?*

The gap between those two is your exposure, and it is almost always larger than you assumed — because permissions are granted once, when granting them is convenient, and reviewed never.
