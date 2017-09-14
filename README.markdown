Git Spell Check
===============

This script is a Git pre-commit hook that spell checks changes in files which you are about to commit.


Instructions
------------

To use this script, clone the following repo:

    ~]$ git clone git://github.com/mprpic/git-spell-check.git

Place this script into the **.git/hooks/** directory in your repository. It must be called **pre-commit** and be executable. A Git hook only works in a single repository. You need to copy this hook into every repository you wish to use it in manually. Optionally, you can set up a symlink in the **.git/hooks/** directory pointing to the script. That way, each time the script is updated in the GitHub repo, you won't have to replace it in the **.git/hooks/** directory. To create a symlink in your repository, execute:

    book]$ ln -s ~/git-spell-check/pre-commit .git/hooks/pre-commit

You will need to install [`aspell`](http://aspell.net/).

On Mac:

	~]$ brew install aspell

On Ubuntu:

	~]$ apt-get install -y aspell

Each time you try to commit something, this script is run to spell check the content you are committing. If misspelled words are found, you can either save them into a custom Aspell dictionary (which means they will be ignored next time the script is run), or ignore them. The following options are available when the script is run:

    Add any of the misspelled words into your custom dictionary?
      * a[ll]     (add all words into dict, continue with commit)
      * s[ome]    (add some words into dict, fix others, no commit)
      * i[gnore]  (add some words into dict, ignore rest, continue with commit)
      * n[one]    (no commit)

Should you want to bypass the pre-commit hook (though not recommended), you can commit with **git commit --no-verify**.


To-Do
-----

* Aspell considers foo_bar two words, and **grep** greps for word boundaries around foo and bar.


Copyright
---------

Git Spell Check — spell checking pre-commit Git hook. Copyright (C) 2012 Martin Prpič

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program. If not, see [http://www.gnu.org/licenses/](http://www.gnu.org/licenses/).
