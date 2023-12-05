---
title: "Github Issues"
weight: 1
desc: "How to use GitHub issues to track your work."
draft: false
---

# Version Control
*How to use GitHub issues to track your work.*

![Idea](https://img.shields.io/badge/status-idea-lightgrey)

{{< hint warning >}}
This page is still a draft because I'm still writing it.
{{< /hint >}}

## Aim
This page aims to outline how to use github issues to track feature requests,
bugs and general TO-DOs for your repositories.

## What are github issues
Issue are a way to track what needs to be done in a repository.
They can cover actual issues, like bugs and errors, but also ideas, conversations,
and more.

You can read about issues [in this guide by Github](https://docs.github.com/en/issues/tracking-your-work-with-issues/about-issues).

When you start making issues, you may ask yourself how to categorize them.
This is what *labels* are for.
When you add labels to issues you are categorizing them in order to look them
up faster.
Github has a [default list of labels for new repositories](https://docs.github.com/en/issues/using-labels-and-milestones-to-track-work/managing-labels),
but you can edit or delete them, or even make new labels yourself.

For single-developer projects, issues can still help to track your work as more
and more things to do pile on.
In such projects, I like this set of labels:
- `bug`: Something is broken and needs to be fixed.
- `enhancement` (or `feature`/`feat`): Something new needs to be added.
- `RFC`: An idea that needs to be thought over, perhaps with others (that's 
  what an [RFC](https://en.wikipedia.org/wiki/Request_for_Comments) is!).
- `documentation`: Something needs to be changed regarding documentation, either in the
  code itself (e.g. docstrings) but also in READMEs, LICENSEs, etc...
- `good first issue`: This issue is easy or new-dev-friendly. This label is best
  left as-is as it populates the repo's "contribute" page.
- `help wanted`: This issue is particularly hard or complicated, and more
  help is needed to address it.
- `invalid` and `wontfix`: Issues that are either no longer relevant or that
  will not be addressed by choice.
- `refactor`: Something could be refactored or optimized in some way, without
  changing the actual functionality.

This list differs from the default list of labels by just the `RFC` and `refactor` labels.
The `duplicate` label is missig (as it's almost never used) but you might as well
keep it - perhaps you might need it later.

You can also add the `urgent` label to mark things that are especially important
to do right away.

### Closing issues
When an issue is addressed, you can close it.
A closed issue does not show up in the default issue search (by default the
filter `is:open` is used).
When you close an issue, take a moment to:
- Specify what was changed (e.g. "Addressed this in `<commit>`: ...");
- Specify any thought processes that went into fixing the issue;
- Give credit to anyone who helped close the issue.
This is important as you might find yourself looking over old, closed issues
to make sense of what was changed and why.

You can reference issues in your commit messages with the `#<issue_number>` form.
Github will automatically mention such commits in the issue conversation.
Example of a good commit message:
- `fix: Fix #5 - Missing file descriptors cause crash`
Example of a bad commit message:
- `Fixes`

#### On writing git commit messages
A small detour on commit messages.
There are [tons](https://github.com/erlang/otp/wiki/writing-good-commit-messages)
of [guides](https://www.freecodecamp.org/news/how-to-write-better-git-commit-messages/)
to [writing good commit messages](https://www.theodinproject.com/lessons/foundations-commit-messages).
Check them out!

Making [atomic commits](https://www.pauline-vos.nl/atomic-commits/) also really
helps when writing commit messages.
Take a look at the [`git commit -p` and `git add -p`](https://gist.github.com/mattlewissf/9958704)
commands.
They can break down large changes into smaller chunks, which you can then submit
to the proper issue / give a proper commit message (so you can avoid committing
something like `fix #4, #6, #7 and #10`)
You should also follow the [conventional commits](https://www.conventionalcommits.org/en/v1.0.0/) convention
as it makes commit messages immediately identifiable.

### Projects and Milestones
You can use [Github projects](https://docs.github.com/en/issues/planning-and-tracking-with-projects/learning-about-projects/about-projects)
if you like a board or list-like view of your issues.
Github gives you views that can be customized to your liking, so you can work
with issues just like you would do with a [kanban](https://en.wikipedia.org/wiki/Kanban_(development))
board.

You can also appoint [milestones](https://docs.github.com/en/issues/using-labels-and-milestones-to-track-work/about-milestones)
that you'd like to reach and assign issues to that milestone (e.g. you could make
a "Submit preprint to arxiv" milestone that tracks all work needed to submit
your paper to the preprint archive).

You can also create `tracking` issues that are not specific to one particular
problem but track different other issues.
If you do go this way, I suggest creating and using the `tracking` label.

Github has a long list of articles about best practices when using [projects](https://docs.github.com/en/issues/planning-and-tracking-with-projects/learning-about-projects/best-practices-for-projects).
Start there if you want to learn more.
