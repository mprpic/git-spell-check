Instructions
------------

This script is a Git pre-commit hook that spell checks any content you are about to commit.

To use this script, clone the following repo:

    ~]$ git clone git://github.com/mprpic/git-spell-check.git

Place this script into the **.git/hooks/** directory in your repository. It must be called **pre-commit** and be executable. A Git hook only works in a single repository. You need to copy this hook into every repository you wish to use it in manually. Optionally, you can set up a symlink in the **.git/hooks/** directory pointing to the script. That way, each time the script is updated in the GitHub repo, you won't have to replace it in the **.git/hooks/** directory. To create a symlink in your repository, execute:

    book]$ ln -s ~/git-spell-check/pre-commit .git/hooks/pre-commit

Each time you try to commit something, this script is run and spell checks the content you are committing.

Should you want to bypass the pre-commit hook (though not recommended), you can commit with **git commit --no-verify**.


To-Do
-----

1. Use **printf** instead of **echo**.

2. Global/Local dictionary for ignored words?
