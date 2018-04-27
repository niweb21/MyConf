### extracts committed files

    git archive --format zip --output conf.zip master

### ignore new update localy

    git update-index --skip-worktree [<file>...]

### exlude file localy (untracked)

    echo [<file>...] >> .git/info/exclude
