---
title: "Brew Maintenance"
date: 2019-10-15T22:51:08+09:00
categories:
    - tutorial
tags:
    - homebrew
keywords:
inspired:
motivation: ""
draft: true
---

# Homebrew Maintenance

[Keeping Your Homebrew Up to Date](https://www.safaribooksonline.com/blog/2014/03/18/keeping-homebrew-date/)

## [Keeping Your Homebrew Up to Date](https://www.safaribooksonline.com/blog/2014/03/18/keeping-homebrew-date/)

### Two Homebrew Caveats

Before we dive fully into Homebrew, two occasionally controversial Homebrew philosophies should be flagged.

__First__, Homebrew tries to work closely with the existing programs found on the Mac __rather than replacing them__. On the upside, this means that you're not going to end up with software that's out-of-sync with what Apple is doing.
On the downside, if you think that some of Apple's software is out-of-date (say, PHP), then you're stuck.
Fortunately, Homebrew has come up with an alternative method to deal with this problem: the tap. We'll touch upon taps shortly, and then we'll discuss how that affects PHP in a future article.

__Second__, Homebrew runs without using `sudo`. Instead, it creates a special version of `/usr/local` for installations that it has access to.
This has the benefit of keeping your administrative environment simpler and safer.
However, it can potentially cause problems if you want to install other things in `/usr/local` — though at present that's only likely to be a issue if you've installed things there with common names that clash with what Homebrew is doing.


### Tip 1: `brew update` to update your homebrew:

```
$ brew update
Already up-to-date.
```

### Tip 2: `brew list` and `brew info ...` to know what you have installed:

```
$ brew list
lynx    openssl wget
```

You can then use `brew info [package]` to get more info on an individual package:

### Tip 3: `brew uninstall ...` to uninstall unused software:

```
$ brew uninstall wget
Uninstalling /usr/local/Cellar/wget/1.15...
```

Uninstalling a package will not uninstall its dependencies, so you'll need to do that by hand, one package at a time.

>Note: Be sure that you're not uninstalling something used by another package, as Homebrew won't protect you from doing so.

### Tip 4: `brew update` to update your out-of-date software

You can automatically update everything with just a few commands.
It's safest to start out by seeing what's out-of-date. You want to `brew update` first to make sure your listings are up-to-date, and then you can `brew outdated`.
Once you've seen what's out-of-date, you can then update everything that was installed by Homebrew with a simple `brew upgrade` command:

```
$ brew upgrade
```

You may not want to upgrade certain packages, however.
In this case, you should protect the older software by __pinning__ it, so that it won't be upgraded. The following command would keep MySQL at its current version:

```
$ brew pin mysql
```

You can then run `brew upgrade` and everything but your pinned packages will be updated. At some point in the future you can choose to `brew unpin [package]` to unprotect the package in question.

```
$ brew upgrade wget
```

### Tip 5: `brew tap ...` to take control by tapping other repositories

The above tips all presume that you're in sync with Homebrew's master repository.
Sometimes you may want to access other repositories that include other packages.
This is done with the `brew tap` command.
You can find a list of interesting brew taps here:
[https://github.com/Homebrew/homebrew/wiki/Interesting-Taps-&-Branches](https://github.com/Homebrew/homebrew/wiki/Interesting-Taps-&-Branches).

If you want to access a tap, you can do so like this:

```
$ brew tap homebrew/science
```

You can then install directly from the new tap with the `brew install ...`.
You'll probably want to keep your brew taps up to date too, so that you don't inadvertently install things from taps that are old and out-of-date. You can always use `brew tap` to see the current list of taps that you're accessing. You can choose to “unsubscribe” from a tap with the `brew untap ...` command:

```
$ brew untap homebrew/dupes
Untapped 39 formula
```

# [Homebrew FAQ](https://github.com/Homebrew/brew/blob/master/docs/FAQ.md)

## How do I update my local packages?
First update the formulae and Homebrew itself:

    brew update

You can now find out what is outdated with:

    brew outdated

Upgrade everything with:

    brew upgrade

Or upgrade a specific formula with:

    brew upgrade $FORMULA

## How do I stop certain formulae from being updated?
To stop something from being updated/upgraded:

    brew pin $FORMULA

To allow that formulae to update again:

    brew unpin $FORMULA

## How do I uninstall old versions of a formula?
By default, Homebrew does not uninstall old versions of a formula, so
over time you will accumulate old versions. To remove them, simply use:

    brew cleanup $FORMULA

or clean up everything at once:

    brew cleanup

or to see what would be cleaned up:

    brew cleanup -n

## How do I uninstall Homebrew?
To uninstall Homebrew, paste the command below in a terminal prompt.

```bash
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/uninstall)"
```
Download the [uninstall script](https://raw.githubusercontent.com/Homebrew/install/master/uninstall)
and run `./uninstall --help` to view more uninstall options.

## How do I uninstall a formula?
If you do not uninstall all of the versions that Homebrew has installed,
Homebrew will continue to attempt to install the newest version it knows
about when you run `brew upgrade --all`. This can be surprising.

To remove a formula entirely, you may run `brew uninstall formula_name --force`.

Be careful as this is a destructive operation.

## Where does stuff get downloaded?

    brew --cache

Which is usually: `~/Library/Caches/Homebrew`

## My Mac `.app`s don’t find `/usr/local/bin` utilities!
GUI apps on macOS don’t have `/usr/local/bin` in their `PATH` by default.
If you’re on Mountain Lion, you can fix this by running
`launchctl setenv PATH "/usr/local/bin:$PATH"`. [More details
here](https://stackoverflow.com/questions/135688/setting-environment-variables-in-os-x/5444960#5444960),
including how to set this across reboots. If you’re pre-Mountain Lion,
[here’s an official
alternative](https://developer.apple.com/legacy/library/qa/qa1067/_index.html).

## How do I contribute to Homebrew?
Read [CONTRIBUTING.md](https://github.com/Homebrew/brew/blob/master/CONTRIBUTING.md).

## Why do you compile everything?
Homebrew provides pre-compiled versions for many formulae. These
pre-compiled versions are referred to as [bottles](Bottles.md) and are available
at <https://bintray.com/homebrew/bottles>.

If available, bottled binaries will be used by default except under the
following conditions:

* Options were passed to the install command, i.e. `brew install $FORMULA`
will use a bottled version of $FORMULA, but
`brew install $FORMULA --enable-bar` will trigger a source build.
* The `--build-from-source` option is invoked.
* The environment variable `HOMEBREW_BUILD_FROM_SOURCE` is set.
* The machine is not running a supported version of macOS as all
bottled builds are generated only for supported macOS versions.
* Homebrew is installed to a prefix other than the standard
`/usr/local` (although some bottles support this).

In order to completely disable bottled builds, simply add a value for
the environment variable `HOMEBREW_BUILD_FROM_SOURCE` to
your profile.

We aim to bottle everything.

## How do I get a formula from someone else’s branch?

    brew install hub
    brew update
    cd $(brew --repository)
    hub pull someone_else

Or:

`brew install https://raw.github.com/user/repo/branch/formula.rb`

Or:

`brew pull https://github.com/Homebrew/homebrew-core/pull/1234`

## Why does Homebrew prefer I install to `/usr/local`?

1.  **It’s easier**<br>`/usr/local/bin` is already in your
    `PATH`.
2.  **It’s easier**<br>Tons of build scripts break if their dependencies
    aren’t in either `/usr` or `/usr/local`. We
    fix this for Homebrew formulae (although we don’t always test for
    it), but you’ll find that many RubyGems and Python setup scripts
    break which is something outside our control.
3.  **It’s safe**<br>Apple has left this directory for us. Which means
    there is no `/usr/local` directory by default, so there
    is no need to worry about messing up existing tools.

**If you plan to install gems that depend on
brews then save yourself a bunch of hassle and install to
`/usr/local`!**

It is not always straightforward to tell `gem` to look in non-standard directories for headers and libraries. If you choose `/usr/local`, many things will "just work".

## Why does Homebrew say sudo is bad?
**tl;dr** Sudo is dangerous, and you installed TextMate.app without sudo
anyway.

Homebrew is designed to work without using sudo. You can decide to use
it but we strongly recommend not to do so. If you have used sudo and run
into a bug then this is likely to be the cause. Please don’t file a bug
report unless you can reproduce it after reinstalling Homebrew from
scratch without using sudo.

You should only ever sudo a tool you trust. Of course, you can trust
Homebrew ;) But do you trust the multi-megabyte Makefile that Homebrew
runs? Developers often understand C++ far better than they understand
make syntax. It’s too high a risk to sudo such stuff. It could break
your base system, or alter it subtly.

And indeed, we’ve seen some build scripts try to modify
`/usr` even when the prefix was specified as something else
entirely.

Did you `chown root /Applications/TextMate.app`? Probably
not. So is it that important to `chown root wget`?

If you need to run Homebrew in a multi-user environment, consider
creating a separate user account especially for use of Homebrew.

## Why isn’t a particular command documented?

If it’s not in `man brew`, it’s probably an external command. These are documented [here](External-Commands.md).

## Why haven’t you pulled my pull request?
If it’s been a while, bump it with a “bump” comment. Sometimes we miss requests and there are plenty of them. Maybe we were thinking on something. It will encourage consideration. In the meantime if you could rebase the pull request so that it can be cherry-picked more easily we will love you for a long time.

## Can I edit formulae myself?
Yes! It’s easy! Just `brew edit $FORMULA`. You don’t have to submit modifications back to *Homebrew/homebrew-core*, just edit the formula as you personally need it and `brew install`. As a bonus `brew update` will merge your changes with upstream so you can still keep the formula up-to-date **with** your personal modifications!

## Can I make new formulae?
Yes! It’s easy! Just `brew create URL`. Homebrew will then open the
formula in `$EDITOR` so you can edit it, but it probably already
installs; try it: `brew install $FORMULA`. If you come up with any issues,
run the command with the `-d` switch like so: `brew install -d $FORMULA`,
which drops you into a debugging shell.

If you want your new formula to be part of *homebrew/core* or want
to learn more about writing formulae, then please read the [Formula Cookbook](Formula-Cookbook.md).

## Can I install my own stuff to `/usr/local`?
Yes, brew is designed to not get in your way so you can use it how you
like.

Install your own stuff, but be aware that if you install common
libraries like libexpat yourself, it may cause trouble when trying to
build certain Homebrew formula. As a result `brew doctor` will warn you
about this.

Thus it’s probably better to install your own stuff to the Cellar and
then `brew link` it. Like so:

```bash
$ cd foo-0.1
$ brew diy
./configure --prefix=/usr/local/Cellar/foo/0.1
$ ./configure --prefix=/usr/local/Cellar/foo/0.1
[snip]
$ make && make install
$ brew link foo
Linking /usr/local/Cellar/foo/0.1… 17 symlinks created
```

## Why was a formula deleted?
Use `brew log $FORMULA` to find out! Likely because it had unresolved issues or
our analytics identified it was not widely used.

## Homebrew is a poor name, it's too generic, why was it chosen?
@mxcl was too concerned with the beer theme and didn’t consider that the
project may actually prove popular. By the time he realized it was, it was too
late. However, today, the first Google hit for “homebrew” is not beer
related ;-)

## What does "keg-only" mean?
It means the formula is installed only into the Cellar; it is not linked
into `/usr/local`. This means most tools will not find it. We don’t do
this for stupid reasons. You can still link in the formula if you need
to with `brew link`.

## How can I specify different configure arguments for a formula?
`brew edit $FORMULA` and edit the formula. Currently there is no
other way to do this.

## Is there a glossary of terms around?
All your terminology needs can be [found here](Formula-Cookbook.md#homebrew-terminology).
