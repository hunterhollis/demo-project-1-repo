# Git Branching Workflow

1. Create an issue on GitHub
2. Create a branch from the issue on GitHub
3. Submit a Pull Request

**Important!** Always use one of the `*-dev` branches as the base branch for all work. Never submit a PR to a production branch because those have to be updated with coordination to class schedules.

## Creating an issue

Click the [New issue](https://github.com/coding-boot-camp/DataViz-Lesson-Plans/issues/new/choose) button.

Choose the Dev Issue Template.

![Dev Issue Template](Images/dev-issue-template.png)

Adjust the title to include the product dev branch that will be impacted along with any modules. The title should also include a short description of the issue in the title.

Example:

```text
[v1.2-dev]: Module 3 - Fix Day 3 Activty 5
```

Example:

```text
[v1.1-dev]: Modules 3-6 - Update Copyright
```

You can optionally add details to the issue body.

## Create a Branch from the issue

After submitting the issue, you will have an option under the Development side menu to create a branch for this issue.

![Create a branch](Images/create-a-branch.png)

This will launch a modal where you can adjust the branch name if needed. You will also need to change the branch source to the dev branch of the product version that needs updated.

![Create branch modal](Images/create-branch-modal.png)

In this example, the issue refers to v1.2-dev, so the base branch should be set to match.

![base-branch-change](Images/base-branch-change.png)

This new branch can then be checked out locally and updated.

```shell
git fetch origin
git checkout 5438-v1.2-dev-module-3-fix-day-3-activity-5
```

Once complete, commit and push changes back to GitHub and open a pull request.

```shell
git add .
git status
git commit -m "Fixes 3.3.5 activity"
git push
```

## GitHub Pull Request

Once work has been completed, submit a GitHub pull request for the work by visiting the [following link](https://github.com/coding-boot-camp/DataViz-Lesson-Plans/compare).

The base branch should be the dev branch for the product that will be updated. In this example, v1.2-dev.

The compare branch should be the issue branch that was created and updated in previous steps. In this example, 5438-v1.2-dev-module-3-fix-day-3-activity-5.

Confirm the branches and the changes and then select `Create pull request`.

![Create pull request](Images/create-pull-request.png)

You can now enter details for the pull request. Please take time here to change both the title and the pull request body to include details of the change.

The title should be formatted to mimic the issue title with the product dev branch listed first in square brackets.

```text
[v1.2-dev] Module 3 - Fixes day 3 activity 5 linting
```

The body should at minimum include a line that closes the issue. GitHub will use this line to automatically close the issue when the pull request is merged.

```text
closes #5438
```

![Pull request details](Images/pull-request-details.png)

Finally, request a peer tech review for the pull request.

The current protocol for pull requests is that the reviewer will either approve or request changes. If changes are requested, the submitter can respond to the requests for discussion or fix issues in the branch and push them back to GitHub. For any change request updates, reply to the comments that changes were made, but only the reviewer can mark the change request as resolved. Once all change requests are resolved and approved, the pull request can be merged to the dev branch.
