This repository contains [reusable workflows](https://docs.github.com/en/actions/using-workflows/reusing-workflows) for use by the [Synapse team](https://github.com/orgs/matrix-org/teams/synapse-core).

The intent is to keep our various projects' CI configuration consistent without having to update N yaml files across N repositories.

# Releases

We follow [GitHub's advice for versioning actions](https://docs.github.com/en/actions/creating-actions/about-custom-actions#using-release-management-for-actions). In short:

- Use [semver](https://semver.org/) release numbering.
- Test changes by publishing them to a named branch, and have test consumers cite that branch.
- For each major version 1, 2, ...:
  - Maintain branches `release/v1`, `release/v2` which track development of a release.
  - From these branches, cut releases 1.x.y, 2.x.y as needed. Tag as `v1.x.y` etc.
  - Maintain a tag `v1`, `v2`, ... which points to the latest release in the 1.x, 2.x series. These tags will need to be force-recreated and force-pushed.
- Consumers that trust this repo should use tagged major versions (`v1`, `v2`,...) of these workflows.
- Consumers that don't should use specify a commit hash when using a workflow.
