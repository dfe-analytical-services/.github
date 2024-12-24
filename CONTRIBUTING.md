## Overview

This GitHub area is managed by the [explore education statistics platforms team](mailto:explore.statistics@education.gov.uk), and contains a wide variety of open source code.

## Governance
We want dfe-analytical-services to be as open as possible to all working in analysis in DfE. You should considering hosting your code here if all of the following are true:

* Your code does **NOT** contain any sensitive or unpublished data
* Your code does **NOT** share information about DfE internal systems
* Your code may be useful to others outside of DfE. For example, to give transparency of code for published analysis or services, share common components or packages, or for other resources such as training materials.

If you are unsure about any of the above statements, you must contact us before starting.

## Standards for repositories

We do not set specific standards for repositories unless deemed necessary for security reasons.

### Security settings

By default, we recommend the following settings on repositories:

- Private vulnerability reporting
- Dependabot alerts & dependabot on Actions runners
- Code scanning (using lintr in the case of R development)
- Secret scanning & push protection

### License

Unless there's a reason otherwise, all repositories should use a GPL-3.0 license.

### Branch conventions

In general, anytime we make a contribution to a respository other than our own in our administrator capacity, we will start the branch name with:

- eesp/

## Working practices

For the repositories we manage ourselves, we have some common working practices that we follow, these are optional, and included here in case they provide inspiration or a helpful guide for others managing their own repositories.

### Default branch

The default branch is **main**, and this should be changed by pull requests only.

The **main** branch should also be protected in the following ways:

- Require a pull request before merging
  - Require approvals (1)
  - Require approval of the most recent reviewable push
- Require status checks to pass before merging (including the following where available):
  - lintr (R specific)
  - shinytest2 UI tests (R Shiny specific)
  - testthat unit tests (R specific)
  - deployment test run
- Require conversation resolution before merging

### Branch naming conventions

We tend to adopt the following branch naming conventions for general work:

- new-feature/[feature-name]
- improvement/[feature-name]
- bugfix/[bug-name]
- data-update/[release-period]

And the following for our contributions to other R Shiny dashboards:

- eesp/accessibility-review
- eesp/dfeshiny-updates-vX.Y.Z
- eesp/workflow-maintenance

### Raising new changes

New changes should be made on a branch created from the latest version of work you wish to develop on. This would normally be the **main** branch, but could be another branch e.g. **development** if contributing to a larger upgrade to your product.

If you don't have access to push to the repo itself, you should either request membership of the associated contributor team or create a [fork of the repository](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo#forking-a-repository).

In the case of the latter, changes can then be made in a new branch in your own repo. Once ready, you should raise a PR in the main GitHub repository, pointing at the **main** branch and one of the repository maintainers will be able to review your changes.

Once a pull request is reviewed and ready to be merged in, all commits in the PR should be squashed as a part of the merge to keep the Git history shorter and easier to navigate.

### General settings

Unused features should be turned off to reduce clutter, e.g. Wikis, Dicussions, Projects. For most repositories only Issues and Preserve this repository should be turned on.

Allow merge commits and Allow rebase merging should be turned off, to encourage the use of squash merging from pull requests.

Always suggest updating pull request branches should be turned on to give the prompt to easily rebase or update branches in open pull requests.

Head branches should be set to be deleted automatically - once a branch is merged in you should be deleting it and then starting new branches for any further contributions.
