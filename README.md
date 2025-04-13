# git-cu

The `git-cu` ("see you") command is meant to simplify the workflows for
projects which are based on Mailing List, using patchwork as the main
interface.

The command is fully written in `/bin/sh` and it doesn't require any external
dependences but `curl` and `jq`, which are included in any Linux distribution.

This command is inspired by the [b4](https://github.com/mricon/b4) project.

## Main functionalities

* fetch and apply patches/series from patchwork
* keep track of patch-series and revisions

## Simple workflow

The following workflow shows a common use case. Please use `git cu` command to
check available options.

    # create a new branch by tracking base commit
    # new branch name will have a "cu-" prefix
    git cu --new mybranch

    # optional: apply patches/series from patchwork
    git cu --apply-patch 128765
    git cu --apply-series 238973

    # create a new commit
    git add .
    git commit

    # edit cover letter
    git cu --edit-cover

    # send patches to the mailing list
    # revision will be incremented automatically
    git cu --send

    # archive branch once merge request has been accepted
    git cu --archive cu-mybranch
