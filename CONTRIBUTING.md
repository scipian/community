# Contributing to Scipian

Thank you for your interest in contributing to Scipian! There are many ways
you can contribute and we appreciate all of them.

* [Feature Requests](#feature-requests)
* [Bug Reports](#bug-reports)
* [Issue Triage](#issue-triage)
* [Toolchain](#toolchain)
* [Pull Requests](#pull-requests)
* [Committing](#committing)
* [Documentation](#documentation)

## Feature Requests

To request a change to the way that Scipian works, please open an issue inside 
the [scipian/rfcs][rfcs] repo and we will be happy to discuss and see if it 
meets the acceptance criteria for an initiative to be created.

Please use the Feature Request issue template when submitting a feature request.

[rfcs]: https://github.com/scipian/rfcs

## Bug Reports

Let's face it, bugs are unfortunate, but they're a reality in software. We 
cannot fix what we do not know about, so please report liberally. If you're not 
sure something is a bug or not, feel free to file anyway.

If you have a chance, please search existing issues, as it's possible someone 
else has already reported your error. However, we won't mind if you 
accidentally file a duplicate.

We would like issues filed in the respective repo the bug belongs to, but if
you're not sure which repo, default to the [scipian/community][community] repo.

Please use the Bug Report issue template when submitting a bug. 

[community]: https://github.com/scipian/community

## Issue Triage

We use [ZenHub][zenhub] within the team to triage and work on issues. Although 
not required, we highly recommend you use it as well. Since Scipian is a public 
account and an open source project, ZenHub is free! Thanks ZenHub!

To use, look over the [guides][zh-guides].

[zenhub]: https://www.zenhub.com/
[zh-guides]: https://www.zenhub.com/guides

### Glossary

- `Initiative` - An overarching feature set to add to the Scipian Platform as a
  whole. For an example, look at the issues in [scipian/rfcs][rfcs]. Later an
  initiative will be broken down into `Epics`.

- `Epic` - An oversized user story that must be broken into a set of smaller,
  connected backlog items and usually takes multiple iterations to complete.

- `Story` - Also know as `User Story` is a set of information that includes
   the needs of the user, business value, acceptance criteria, and any
   supporting information (images, user flows, designs, etc.) needed by the
   team to ensure understanding and delivery of a required set of work.

  *Tip: When creating stories, follow the `INVEST` principle.*
  > 1. **I**ndependent
  > 2. **N**egotiable
  > 3. **V**aluable - Business Value
  > 4. **E**stimable
  > 5. **S**mall - 1 to 2 person days
  > 6. **T**estable

- `Task` - A generic, "one-off' work item that stands alone - no other work or
   effort is needed to complete it.

- `Bug` - A feature or functionality that is not working as intended and 
   provides value when resolved.

- `Test` - A specific task to add an automated test that stands alone.

### Pipelines

- **Triage**

  This is the pipeline we review and prioritize issues. Not all issues will be
  accepted. However, we need a place for us to create and get them out of our
  head. We can discuss the issue later when we triage.

  New issues land here automatically. They should be dragged to another 
  pipeline as soon as possible with the appropriate labels or closed.

  *Tip: Use templates to help with creating new issues.*

- **Backlog**

  Issues in this pipeline aren't the current focus. You'll usually see issues
  here that have been triaged, but that are not necessarily complete yet and
  haven't been assigned an iteration. Consider this pipeline part of our 
  product backlog. Once a milestone is assigned, consider them part of the 
  iteration back log.

  For some issues, this may be the farthest it goes. Every week, we'll pick 
  from the backlog the issues that add value to what we are doing. Yeah, most 
  issues add value, but as a project gets more mature, the issues may not be 
  worth doing and will lose value.

- **Ready**

  Issues in this pipeline are well-defined and are the current focus for the
  team. As issues flow into this pipeline, order them by priority. This is 
  where we'll assign issues to ourselves from. Issues should be worked in the 
  order they are presented in the pipeline. No cherry picking.

- **Current**

  This pipeline shows the issues we're currently working on in this iteration.
  Each team member should be working on just one thing at a time. When you 
  start on an issue assigned to you in the Ready pipeline. Drag the issue to 
  this pipeline. When you're ready for a code review, issue a PR and make sure 
  the PR is within the Review pipeline. You can issue a PR at any point, it 
  just depends on when collaboration is needed.

- **Review**

  This pipeline shows current PR's for review to enforce our Definition of 
  Done.

- **Done**

  Once an issue satisfies what we call done, the PR will be accepted and the
  issue will be dragged here.

  What constitutes as done? Before being merged in and deployed, every code
  change must have the following:

  1. **Automated Tests** that test the functionality being introduced.
  2. **Documentation** that explains the change and how to use it.
  3. **Styling** that correlates with the project styling guidelines.
  4. **Signed** Contributor License Agreement (CLA)?
  5. **Signed off by commit**, if an outside contributor.
  6. **History** clean and squashed?
  7. **Latest** changes from `master` rebased?

- **Closed**

  Once an issue has been merged, drag it to this pipeline where it will be
  automatically closed.

  *Disclaimer: Reason we do not close an issue after Done, is to allow us to 
  add pipelines if needed in the future.*

#### Iteration -> Milestone

- Every iteration will have a milestone.
- Iteration length can be dependent on milestone goals.
- Every milestone will culminate the initiatives that we want to deliver within
  said time frame.

### Labels

- Type
  - Initiative
  - Epic
  - Story
  - Task
  - Question
  - Spike
  - Pull Request

- Problem
  - Bug
  - Security

- Improvement
  - Enhancement
  - Refactor
  - Optimization

- Blocked
  - Documentation
  - Development
  - Design
  - Test
  - RFC
  - CLA

- Priority
  - Critical
  - High
  - Medium
  - Low

- Status
  - Accepted
  - Ready
  - Assigned
  - Done

- Inactive
  - Duplicate
  - On-Hold
  - By-Design
  - Invalid
  - Abandoned

#### Assigned Colors

| Category | Color | Hex |
| --- | --- | --- |
| Type | Blue - Medium | #84b6eb |
| Problem | Red | #ff9999 |
| Improvement | Blue - Light | #c5def5 |
| Blocked | Orange | #ffa500 |
| Priority | Yellow | #fef2c0 |
| Status | Green | #c2e0c6 |
| Inactive | Gray | #cccccc |

## Toolchain

TODO(dwr): Need an issue to track this work

## Pull Requests

Pull requests are the primary mechanism we use to change Scipian. To learn 
more, GitHub itself has some [documenation][github-prs] on using the Pull 
Requests feature.

Please make pull requests against the `master` branch. Refer to
[Issue Triage](#issue-triage) above to see what is needed before your PR is 
merged into `master`.

[github-prs]: https://help.github.com/articles/using-pull-requests/

## Committing

If you are a core contributor, please sign your commits when merging in PR's or 
working on issues. GitHub has documentation on how to setup GPG to 
[sign commits][sign-commits].

[sign-commits]: https://help.github.com/articles/signing-commits-with-gpg/

If you're not part of the core team, you are not required to sign your commits, 
but you are required to include the sign-off message in your commit. To do 
that, add the `-s` option to the commit command.

```
git commit -s
```

### Git Commit Template

As a team, we use a template for our commit messages to make reading the log
a little easier and it also has other [advantages][commit-style-advantages]. 
The easiest way to remember what it is, is by saving the template below to
`~/.gitmessage`. Then, in your terminal, run 
`git config --global commit.template ~/.gitmessage` to set it as your global 
git message template. Make sure you save a few empty lines at the top for your 
message to go.  

```


# http://chris.beams.io/posts/git-commit/
# 50-character subject line
#
# 72-character wrapped longer description. This should answer:
#
# * Why was this change necessary?
# * How does it address the problem?
# * Are there any side effects?
#
```

In case the formatting isn't very clear above, I created a 
[gist][commit-format] you can use as reference.

When you issue `git commit`, the above template will show up in the editor you 
have configured. Normally this is vim, if you haven't configured `EDITOR` 
environment variable.

[commit-style-advantages]: http://chris.beams.io/posts/git-commit/
[commit-format]: https://gist.github.com/dragan/7cf1809daf6668f7edd2

## Documentation

Documentation improvements are very welcome and is an awesome way to get 
started with open source.

## Creating Repositories

### Initializing a Repository

```sh
git init
git commit --allow-empty -s -S -m "Initialize repository"
git remote add origin [repo-ssh-url]
git push origin master
```

### Setting Up Labels

View `scipian/community/data/labels/README.md`

```sh
git-labelmaker
# Set token if you haven't already
# Select `Use Saved Token`
# Select `Add Labels From Package`
# Enter path to each category json file
```
