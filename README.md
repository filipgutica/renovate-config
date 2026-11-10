# renovate-config

Shared [Renovate](https://docs.renovatebot.com/) preset for `filipgutica` repositories.

Use it from a repository's `renovate.json`:

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>filipgutica/renovate-config"]
}
```

| Updates | What happens |
| --- | --- |
| `@filipgutica/*` packages | One grouped PR as soon as a version publishes, majors included and outside the PR limit; never automerged, because a bump changes what sites look like and needs screenshots |
| GitHub Actions, dev dependencies (minor, patch, pins), lockfile maintenance | A PR that merges itself once branch protection and CI pass |
| Other minor and patch updates | PRs on Monday before 6am UTC, at most 3 open |
| Major updates | Wait for approval on the Dependency Dashboard issue |

The base is `config:best-practices`: pinned Action digests, pinned dev dependencies, a 3-day minimum age for npm releases, and weekly lockfile maintenance.
