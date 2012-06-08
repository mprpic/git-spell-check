Instructions
------------

This script is a Git pre-commit hook that spell checks any content you are about to commit.

To use this script, clone the following repo:

    ~]$ git clone git://github.com/mprpic/git-spell-check.git

Place this script into the **.git/hooks/** directory in your repository. It must be called **pre-commit** and be executable. A Git hook only works in a single repository. You need to copy this hook into every repository you wish to use it in manually. Optionally, you can set up a symlink in the **.git/hooks/** directory pointing to the script. That way, each time the script is updated in the GitHub repo, you won't have to replace it in the **.git/hooks/** directory. To create a symlink in your repository, execute:

    book]$ ln -s ~/git-spell-check/pre-commit .git/hooks/pre-commit

Each time you try to commit something, this script is run to spell check the content you are committing. If misspelled words are found, you can either save them into a custom Aspell dictionary (which means they will be ignored next time the script is run), or ignore them. The following options are available when the script is run:

    Add any of the misspelled words into your custom dictionary?
      * a[ll]     (add all words into dict, continue with commit)
      * s[ome]    (add some words into dict, fix others, no commit)
      * i[gnore]  (add some words into dict, ignore rest, continue with commit)
      * n[one]    (no commit)

Should you want to bypass the pre-commit hook (though not recommended), you can commit with **git commit --no-verify**.
