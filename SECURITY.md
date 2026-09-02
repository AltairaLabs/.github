# Reporting a security problem

**Please don't open a public issue for a security problem.**

Every AltairaLabs repository has GitHub's private vulnerability reporting turned
on: go to the repository, then **Security → Report a vulnerability**. That opens
a private thread visible only to you and to us.

If you can't work out which repository it belongs to, report it against
[omnia-issues](https://github.com/AltairaLabs/omnia-issues/security/advisories/new)
and we'll move it.

## What helps

- **Which thing, and which version.** For PromptPack, PromptArena or PromptKit,
  the release. For Omnia, the chart version and the image tags.
- **What an attacker gets.** Read access to another workspace's sessions, a
  policy that can be bypassed, a redaction that doesn't hold, credentials in a
  log. The consequence matters more than the mechanism.
- **A reproduction**, however rough. A description of the shape of it is fine if
  a clean repro is hard.

Please give us a chance to ship a fix before describing it publicly. We'll tell
you what we found and when it goes out, and we'll credit you unless you'd rather
we didn't.

## Where the code is

PromptPack, PromptArena, PromptKit and the four deploy adapters are public, so
you can read them. Omnia is not — if you've found something in it from the
outside, that's worth more to us, not less.
