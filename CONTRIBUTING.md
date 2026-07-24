# Contributing to Awesome Buzz

## Entry format

```
- [Name](url) - One-line description, ending in a period.
```

- Description is one sentence. State what it is and what it does, no adjectives ("ultimate", "amazing", "powerful").
- No emoji in entries.
- Link directly to the resource (repo, file, or page), not to a redirect or shortener.
- GitHub file links point at `main` (or the default branch), not a commit hash, so they stay current.

## Ordering

Entries are alphabetical by name within each section, except:

- **Official** stays in its existing order (canonical links, not a growing list).
- **Articles & Teardowns** and **Videos** are chronological by publish date, oldest first, since they document launch-week coverage.

## Criteria for inclusion

- **Working**: the link resolves (checked with a HEAD/GET request before merge). Broken links get removed, not fixed in place.
- **Buzz-specific**: the resource is about Buzz directly (the relay, a Buzz crate, a Buzz deployment asset, an ACP harness configuration for Buzz, independent analysis of Buzz). General Nostr or ACP resources belong only in [Related Nostr Tooling](README.md#related-nostr-tooling), and only if a Buzz user would plausibly reach for them.
- **Maintained or historically accurate**: for tools, no sign of abandonment for the stated purpose. For articles and videos, factually accurate at time of adding; outdated but historically relevant pieces stay with their original context, not the current state of the project.
- **No self-promotion**: don't add your own project, blog, or channel. Open a PR and let someone else merge it, or disclose the conflict in the PR description and let a maintainer decide.

## Adding an entry

1. Fork and add your entry to the relevant section, in alphabetical order (see [Ordering](#ordering)).
2. Confirm the link works and the description is accurate.
3. Open a PR with a title like `Add crates/foo to Deployment & Ops`.
4. One entry per PR, unless you're adding several closely related items (e.g. a set of docs for the same tool).

## Removing an entry

Broken links, abandoned projects, and content that no longer meets the criteria above get removed. Open a PR stating why.
