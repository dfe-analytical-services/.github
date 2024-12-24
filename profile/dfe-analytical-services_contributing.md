## Overview

This GitHub area is managed by the [explore education statistics platforms team](mailto:explore.statistics@education.gov.uk), and contains a wide variety of open source code.

We do not set specific standards for repositories unless deemed necessary for security reasons.

For the repositories we manage ourselves, we have some common working practices that we follow, these are optional, and included here in case they provide inspiration or a helpful guide for others managing their own repositories.

## Default branch

The default branch is **main**, and this should be changed by pull requests only.

The **main** branch should also be protected in the following ways:

- Require a pull request before merging
  - Require approvals (1)
  - Require approval of the most recent reviewable push
- Require status checks to pass before merging (incl the following where available):
  - lintr
  - shinytest2 UI tests
  - testthat unit tests
  - deploy test run
- Require conversation resolution before merging

## Branch naming conventions

We tend to adopt the following branch naming conventions for general work:

- new-feature/feature-name
- improvement/feature-name
- bugfix/bug-name
- data-update/release-period

And the following for our contributions to other's dashboards:

- eesp/accessibility-review
- eesp/dfeshiny-updates-vX.Y.Z
- eesp/workflow-maintenance

## Raising new changes

New changes should be made on a branch created from the latest version of work you wish to develop on. This would normally be **main**, but could be e.g. **development** if contributing to a larger upgrade to your product.

If you don't have access to push to the repo itself, you should either request membership of the associated contributor team or create a [fork of the repository](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo#forking-a-repository).

In the case of the latter, changes can then be made in a new branch in your own repo. Once ready, you should raise a PR in the main GitHub repository, pointing at the **main** branch and one of the repository maintainers will be able to review your changes.

Once a pull request is reviewed and ready to be merged in, all commits in the PR should be squashed as a part of the merge to keep the Git history shorter and easier to navigate.

## Security settings

By default, we recommend the following settings on repositories:

- Private vulnerability reporting
- Dependabot alerts & dependabot on Actions runners
- Code scanning (using lintr in the case of R development)
- Secret scanning & push protection

## License

Unless there's a reason otherwise, all repositories should use a GPL-3.0 license.