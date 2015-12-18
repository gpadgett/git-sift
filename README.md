git-sift
========

git-sift is a small program to easily sift file changes into one of
possibly many commits on a local branch.

It works on the premise that you have one or more local commits that
you'd like to amend on a per-file basis.  After completion, the changes
to those files will be in the existing local commits.  It can be useful
in cases where you have a series of several local commits that alter
different files.

When run, for each unstaged, modified file it will show a numbered list
of local commits (ie not upstream) and give the option to choose one--
by default the last one that touched the file.  Alternatively you can
choose to create a new commit or skip the file.

After creating the commits, it offers to rebase --autosquash and will
stash skipped files if necessary.  There is also an auto mode that will
choose the defaults automatically, ask for confirmation, then offer to
rebase.

Usage
-----

Copy git-sift somewhere on your $PATH, then inside the desired repo:

    git sift

Options include:

    -a|--auto     Auto mode: choose the default commits automatically
    -n|--dry-run  Don't actually commit anything (it may still rebase!)

