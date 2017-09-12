# pr

Here you will get to try out the so-called Forking workflow. Your
goal is to get a change merged to this repository (`wkillerud/pr`).

If you run into a word or term you don't understand it might be
explained in the
[Github Glossary](https://help.github.com/articles/github-glossary/).

You'll also find some links to other material on Git at the bottom
of this file.

## Prerequisites

* [Git](https://git-scm.com/), either via the terminal (recommended)
or via a GUI like the Github app, SourceTree, or TortoiseGit.
* A Github account so you can make pull requests to this repository.

It also helps if you've followed the
[Setting up Git](https://help.github.com/articles/set-up-git/) guide on Github

## PR 101

TL;DR - there are eight steps to creating a PR:

1. Fork this repository
2. Clone your fork to your PC
3. In your local clone, create a branch from `master`
4. Change or add a file
5. Commit your change
6. Push the changes to your fork
7. Create a pull request to the `master` branch of `wkillerud/pr`
8. I'll look over the pull request, and if it looks OK I'll merge it!

### Forking

You create a fork by pressing the Fork-button to the top-right of the
screen. Github takes a few seconds to create your fork. When the fork
is created it should say "forked from wkillerud/pr" to the top-left.

### Cloning

For all but the very basic changes you need to work on your PC. To get
the files and their history to your PC you need to clone your forked
repository. Click the "Clone or download" button to do this. Copy
the address to the repository and enter it in your terminal like so:

```
$ git clone https://github.com/DITT_BRUKERNAVN/pr.git
```

> If you get complaints that the client does not support HTTP(S), use
> the SSH variant instead. See Github help for how to set this up.

### Branching

Before making changes it it good practice to create a branch. This makes
it easier to track changes, work with other developers, and go back if
something breaks.

To create a branch and immediately start working, use this command:

```
$ git checkout -b feature/my-shiny-new-thing
```

`-b` makes Git create the branch `feature/my-shiny-new-thing` for you.
It's a short-hand form of this:

```
$ git branch feature/my-shiny-new-thing
$ git checkout feature/my-shiny-new-thing
```

### Make a change

This one is up to you. Create a new file, or change an existing one.
For instance you can add your name to the Contributors list, fix
spelling errors, or add new material on Git to the section at the
bottom.

### Commit your change

To share your change you have to "store" it in the Git repository.
Doing this is a two-step process in Git:

1. Prepare, or stage your change using `git add CONTRIBUTORS.md`
2. Commit your change using `git commit`

If you are short on words you can use this shortcut and type a log
message directly from the terminal:

```
$ git commit -m "Words are hard"
```

Plain `git commit` usually opens `vim`, a terminal based text editor,
so you can write a more detailed description of your change and the
reasoning behind it. This helps future developers get the proper context
when looking at a piece of code, and is very helpful! Take a look at this
repositorys commit messages using the command `git log`.

Try to avoid writing short messages when working with Git, especially with
other developer. I recommend using just the command `git commit` so you
are encouraged to flesh out the commit message. This does require some
knowledge of `vim` (the editor can be changed if you want to).

A crash course to using `vim` for commit messages: 

* Press `i` to enter _insert mode_, which lets you write text
* Press `ESC` to go back to _command mode_
* Press `:x` (colon, then x, then Enter) to save your message and exit
* If you want to abort, press `:q!` (colon, then q, then !)

### Push the changes to your fork

To make your changes ready for a pull request they need to be publbicly
available. To push your changes to your Github fork use the command
`git push origin HEAD`.

If everything went according to plan you should get something like this:

```
To github.com:DITT_BRUKERNAVN/pr.git
 * [new branch]      HEAD -> feature/my-shiny-new-thing
```

You can double check that your change made it to Github by checking the
list of branches in the dropdown to the top-left that says "Branch: master".

### Make a pull request!

Github is pretty clever, so if you look at your repository after pushing a
new branch it will show a helpful button to create a pull request. Click 
"Compare & pull request".

On the page you are taken to you can look over your changes and edit a proper
description of the pull request. You can also change the target for the pull
request, but the default settings should be what you want here.

If everything looks good, click "Create pull request".

### Merging

Well done! You have created a PR. Now you need to wait for the maintainer
(that's me!) to look over the PR, and if everything checks out it will be
merged.

#### What if something's off?

This is where things can get tricky. A maintainer may ask you to make changes
to the code, or perhaps even just to the commit log. Here you just have to work
with the maintainer to get to a solution, and use Google to your advantage.

### Bonus: use your new powers for good!

Now that you know your way around a pull request, why not use that knowledge
to help open source projects?

freeCodeCamp has [a great article](https://medium.freecodecamp.org/finding-your-first-open-source-project-or-bug-to-work-on-1712f651e5ba)
on where and how you can contribute to open source as a rookie.
If you ever get stuck on a pull request feel free to ping me (wkillerud)
here on Github and I'll see if I can help you _pull through_.

Go get 'em!

## Some material on Git

[Atlassian has an excellent guide.](https://www.atlassian.com/git/tutorials/what-is-version-control)
It starts with the basics, but goes on to cover several very useful topics like different workflows,
such as the forking workflow you've seen here.

Github also has some material to get you started:

* [Hello, world!](https://guides.github.com/activities/hello-world/).
* [Bootcamp](https://help.github.com/).

There's also a free book that goes in-depth when you feel ready:

* [Pro Git](https://git-scm.com/book/en/v2)
