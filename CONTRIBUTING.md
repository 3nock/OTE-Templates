# Template Contribution Guidelines

This documentation contains a set of guidelines to help you during the contribution process. We are happy to welcome all the contributions from anyone willing to improve/add new templates to this project. Thank you for helping out and remember, no contribution is too small.

# Submitting OTE Templates

Below you will find the process and workflow used to review and merge your changes.

## Step 1 : Find existing templates

- Take a look at the [Existing Templates](https://github.com/3nock/OTE-Templates/tree/main/templates) before creating new one.
- Take a look at Existing Templates in [GitHub Issues](https://github.com/3nock/OTE-Templates/issues) and [Pull Request](https://github.com/3nock/OTE-Templates/pulls) section to avoid duplicate work.

## Step 2 : Fork the Project

Fork this Repository. This will create a Local Copy of this Repository on your Github Profile. Keep a reference to the original project in upstream remote.

``` bash
git clone https://github.com/<your-username>/OTE-Templates
cd OTE-Templates
git remote add upstream https://github.com/3nock/OTE-Templates
```

- If you have already forked the project, update your copy before working.

```bash
git remote update
git checkout master
git rebase upstream/master
```

## Step 3 : Create your Template Branch

Create a new branch. Use its name to identify the issue your addressing.

```bash
# It will create a new branch with name template_branch_name and switch to that branch
git checkout -b template_branch_name
```

## Step 4 : Create Template

- Create your template.
- Add all the files/folders needed.

## Step 5 : Commit

- After you've made changes or completed template creation, add changes to the branch you've just created by:

```bash
# To add all new files to branch template_branch_name
git add .
```
- To commit, give a descriptive message for the convenience of the reviewer by:

```bash
# This message get associated with all files you have changed
git commit -m "Added/Fixed/Updated XXX Template"
```

_NOTE:_
- A Pull Request should have only one unique template to make it simple for review.
- Multiple templates for same technology can be grouped into single Pull Request.

## Step 6 : Push Your Changes

- Now you are ready to push your template to the remote (forked) repository.
- When your work is ready and complies with the project conventions, upload your changes to your fork:

```bash
# To push your work to your remote repository
git push -u origin template_branch_name
```
## Step 7 : Pull Request

- Fire up your favorite browser, navigate to your GitHub repository, then click on the New pull request button within the Pull requests tab. Provide a meaningful name and description to your pull request, that describes the purpose of the template.

- Voila! Your Pull Request has been submitted. It will be reviewed and merged by the moderators, if it complies with project standards, otherwise a feedback will be provided.
