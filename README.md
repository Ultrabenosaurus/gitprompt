Yet Another Git-Focused Shell Prompt Customisation Script
=========================================================

Does exactly what it says on the tin.

## WHY?! THERE ARE TOO MANY ALREADY!! ##

Well, you see, I'm on Windows. Using the bash environment that came with Git 1.9.4-preview20140611 (I think it's MINGW or something) which isn't entirely compatible with a whole load of stuff available in the proper Linux bash.

As a specific example, I had to manually update the `grep` executable because mine didn't have the `-o` flag.

It also can't display unicode, for some reason, so things that are often used to display branch status in existing prompt scripts - like `echo -e '\u2191'` (&uarr;) - just don't work.

A lot of them also customise the non-Git aspects of the prompt - which admittedly this does as well* - and I'd already customised that myself and got it how I wanted it, so I'd rather not switch to someone else's script and have to hack it to format how I want it.

Finally, I am yet to find one that is extensible. They're all very procedural, and have little in the way of exposed options for easy tweaking. I've tried to build this from the ground up to be easy to chop-and-fix however you want it.

*Unfortunately, this is currently not as "modular" as the Git aspects of the script. I'm planning on updating it soon to be more flexible in that respect as well.

## Okay, fine, lets see it then... ##

![gitprompt example](http://puu.sh/c41OY/f2bd7e4740.png)

## Looks cool, what do the things mean? ##

__Brackets__

* `(branch)` ~ normal round brackets mean that, as far as I can tell, you're completely in-sync with `origin`
* `{branch}` ~ curly braces mean that something is different compared with `origin`, hopefully there'll be a flag as below

__Branch Status__

* `a#` ~ `a` stands for "ahead" and `#` is by how many commits
* `b#` ~ `b` stands for "behind" and `#` is by how many commits
* if you are "diverged" according to Git-speak you'll see something like `a2b1`

__File Status__

* `/U` ~ there are untracked objects present (haven't figured out how to count them, yet)
* `+#` ~ how many new files are going to be added by the commit
* `-#` ~ how many files are going to be deleted by the commit
* `~#` ~ how many files are going to be modified by the commit

## To Do ##

* write customisation section in README
* make colour names more meaningful
* put non-Git stuff into functions
* move main branch `if` block into function
* OPTIMISE!!

## License ##

As usual with my work, this project is available under the BSD 3-Clause license. In short, you can do whatever you want with this code as long as:

* I am always recognised as the original author.
* I am not used to advertise any derivative works without prior permission.
* You include a copy of said license and attribution with any and all redistributions of this code, including derivative works.

For more details, read the included LICENSE.md file or read about it on [opensource.org](http://opensource.org/licenses/BSD-3-Clause).