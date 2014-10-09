Yet Another Git-Focused Shell Prompt Customisation Script
=========================================================

Does exactly what it says on the tin.

## Contents ##

1. [Rationale](#why-there-are-too-many-already)
2. [Example Output](#okay-fine-lets-see-it-then)
3. [Output Explained](#looks-cool-what-do-the-things-mean)
4. [Sources](#as-if-you-did-this-all-yourself)
5. [What's Next?](#to-do)
6. [License](#license)

## WHY?! THERE ARE TOO MANY ALREADY!! ##

Well, you see, I'm on Windows. Using the bash environment that came with Git 1.9.4-preview20140611 (I think it's MINGW or something) which isn't entirely compatible with a whole load of stuff available in the proper Linux bash.

As a specific example, I had to manually update the `grep` executable because mine didn't have the `-o` flag.

It also can't display unicode, for some reason, so things that are often used to display branch status in existing prompt scripts - like `echo -e '\u2191'` (&uarr;) - just don't work.

A lot of them also customise the non-Git aspects of the prompt - which admittedly this does as well* - and I'd already customised that myself and got it how I wanted it, so I'd rather not switch to someone else's script and have to hack it to format how I want it.

Finally, I am yet to find one that is extensible. They're all very procedural, and have little in the way of exposed options for easy tweaking. I've tried to build this from the ground up to be easy to chop-and-fix however you want it.

*Unfortunately, this is currently not as "modular" as the Git aspects of the script. I'm planning on updating it soon to be more flexible in that respect as well.

[Top](#yet-another-git-focused-shell-prompt-customisation-script)

## Okay, fine, lets see it then... ##

![gitprompt example](http://puu.sh/c41OY/f2bd7e4740.png)

[Top](#yet-another-git-focused-shell-prompt-customisation-script)

## Looks cool, what do the things mean? ##

There 3 aspects of the output (5 including colours) that change depending on your branch's status:

__Brackets__

* `(branch)` ~ round brackets mean that, as far as I can tell, you're completely in-sync with `origin`
* `{branch}` ~ curly braces mean that something is different compared with `origin`

__Commits__

* `a#` ~ `a` stands for "ahead" and `#` is by how many commits
* `b#` ~ `b` stands for "behind" and `#` is by how many commits
* if you are "diverged" according to Git-speak you'll see something like `a2b1`

__Files__

* `+#` ~ how many new files are going to be added by the commit
* `-#` ~ how many files are going to be deleted by the commit
* `~#` ~ how many files are going to be modified by the commit
* `/#` ~ how many files are going to be renamed by the commit
* `*#` ~ the number of untracked objects present
* `x#` ~ the number of conflicted files

[Top](#yet-another-git-focused-shell-prompt-customisation-script)

## As if you did this all yourself! ##

Actually, you're right.

I was inspired by the awesomeness of bash itself and the abundance of existing prompt customisation scripts/tutorials available.

I heavily referenced online manuals, guides and StackOverflow questions to help negate my lack of bash knowledge.

And the main `if` block that determines whether or not your working directory is clean is a modified version of the one found in [MediaDoneRight's "Ultimate GIT PS1 bash prompt" article](http://mediadoneright.com/content/ultimate-git-ps1-bash-prompt). I am also using `Time12h` and `PathShort` from their article, as I had no idea such handy flags existed.

Although the colour codes I'm using look identical to those in MDR's post, I actually already had them. I can't remember where I got them from, though, sorry. Just use MDR's as a reference if you don't like the ones I've used.

[Top](#yet-another-git-focused-shell-prompt-customisation-script)

## To Do ##

* update screenshot
* make colour names more meaningful
* write customisation section in README
* put non-Git stuff into functions
* move main branch `if` block into function
* add toggle for running `fetch`?
* OPTIMISE!!

[Top](#yet-another-git-focused-shell-prompt-customisation-script)

## License ##

As usual with my work, this project is available under the BSD 3-Clause license. In short, you can do whatever you want with this code as long as:

* I am always recognised as the original author.
* I am not used to advertise any derivative works without prior permission.
* You include a copy of said license and attribution with any and all redistributions of this code, including derivative works.

For more details, read the included LICENSE.md file or read about it on [opensource.org](http://opensource.org/licenses/BSD-3-Clause).

[Top](#yet-another-git-focused-shell-prompt-customisation-script)