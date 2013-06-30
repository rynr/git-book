git
===

Git was created by Linus Torwalds, after the SCM (Source Control Management)
used for the Linux-kernel was not permitted to use free any more. In april
2005, Linus started with the code. The first release of Linux using git was
done the 16 june 2005, the release of version 1.0 was on 21 december 2005.

Examples in this book
---------------------

This book does cover the command-line usage of git. All examples are formatted
like `this`. When ever an example contains parts that can be replaced, the
parts are surrounded by < and >, what looks like `<this>`.

Most examples are shown, like they look on Unix or Linux systems. If you use
Windows, it will looks a bit different, but the usage will be the same. Most
functions are available with the different Interfaces, please refer to the
documentation of the tool you prefer to use.

 - At the end of each chapter, there will be some Gotchas, ...

Installation
------------

The installation is greatly described at the git-site, so take a look at the
download-section on http://git-scm.com/. After installing git, take a short
look at the minimal Configuration below.

Graphical User Interfaces
-------------------------

Git itself is only a executable to use within a shell (linux) or command-window
(Windows). There are multiple Graphical Interfaces, that can be downloaded
depending on the development-system you use. You can find them listed on
http://git-scm.com/downloads/guis. Which one you prefer is really depending on
your own needs. If you get deeper into git, you will probably use less
graphical interfaces and more the console-tool.

Configuration
-------------

Git differs between global an local configuration. When you start using git,
it's recommended to setup your identity first, including a email-address and
your name. These values are retrieved by the system, if not provided. If you
try to use git without this main configuration, it will ask you to configure
it like this:

    Your name and email address were configured automatically based
    on your username and hostname. Please check that they are accurate.
    You can suppress this message by setting them explicitly:

      git config --global user.name "Your Name"
      git config --global user.email you@example.com

So, let's do this:

> user:~$ git config --global user.name "Rainer Jung"
> user:~$ git config --global user.email "Rainer.Jung@gmail.com"

The configuration is now stored in `~/.gitconfig`. If you omit `--global`, the
configuration will be stored in the with the current repository at
`.git/config`. There's a system configuration too, it's provided by the system
at `/etc/gitconfig`.

The configuration now looks like this:

> [user]
>         name = Rainer Jung
>         email = Rainer.Jung@gmail.com

Editor
------

For some interaction, git will invoke a editor (for example to get a comment of your changes). By default the environment-variable EDITOR will be used. You can overwrite this by setting core.editor (globally, or per repository).

Further configurations
----------------------

Gadgets
=======

Bash-Completion
---------------

If you use the bash, you should have bash-completion installed.

Prompt
------

You can show information about the current git-project within the prompt.
There's a command available by git called with `__git_ps1`. Here's a example
to put in your `.bashrc`, the name of the current branch will be included in
the prompt.

> export PS1='\u@\h:\w$(__git_ps1 "(%s)")\$ '
