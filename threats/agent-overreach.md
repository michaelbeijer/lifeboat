# Local AI agent overreach

**The newest threat here, and the one with the least established practice.**

## What it looks like

You ask a coding agent for help with a project. In passing it mentions a file in your Downloads folder – helpfully, correctly, and entirely unbidden. It had a sensible reason: it needed something, and looking was faster than asking.

Nothing went wrong. But you have just learned that the thing you invited in can read your whole home directory, and that it will act on its own judgement about what is worth reading.

## Why it matters more for some people

If you hold confidential material – client documents under NDA, legal or medical text, unpublished work – then an agent reading it is not a data-loss event. It is a **confidentiality** event, and unlike lost files, you cannot restore your way out of it.

The default posture of most coding agents is broad read access across the home directory, with writes constrained to the working directory. That default can reach credential files and SSH keys.

## Controls

Ordered by value:

1. **Deny reads** on directories the agent has no business in: Downloads, client work, credential locations.
2. **Restrict network access** to an explicit allowlist. This turns "the agent was hijacked" into "the agent was hijacked and could not send anything anywhere".
3. **Use OS-level sandboxing** rather than per-action approval prompts. Approval fatigue is a predictable failure mode – nobody reads the hundredth dialog.
4. **Keep the runtime patched.** Sandbox escapes are an active bug class, and the interesting variants involve making the sandbox write something a trusted process outside it later consumes.
5. **Prefer scoped credentials** for anything the agent can reach.

## On dedicated products

A consumer security vendor now ships behavioural gating for agent actions, and others will follow. The category is real.

It is also months old, still labelled beta, and there is no independent testing of its accuracy – no published false-positive rates, no detection benchmarks. Treat it as plausible rather than proven.

The free controls built into the agent itself are more valuable, because they are deterministic. A denied directory is denied. A probabilistic filter is a guess.

## The wider point

This threat did not exist three years ago, and the guidance will change. It is here as a reminder that the threat model needs revisiting, not just the implementation.

Which is the argument for organising by principle rather than checklist. [Least privilege](../principles/03-least-privilege.md) already covered this before anyone had a name for it.
