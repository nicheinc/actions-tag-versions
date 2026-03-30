# actions-tag-versions

`actions-tag-versions` is a reusable
[GitHub Actions](https://docs.github.com/en/actions) workflow for updating the
corresponding major version tag whenever a semver tag of the form vX.Y.Z is
released.

For an example calling workflow, see
[release.yaml](.github/workflows/release.yaml). Note that it's important to use
a `push` trigger filtered as follows, to prevent the workflow from possibly
triggering itself:

```
on:
  push:
    tags:
      - "v[0-9]+.[0-9]+.[0-9]+"
```
