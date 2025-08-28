# Creating a new branch

We'll be doing the next couple of bits from the command line - but don't worry if you've never used it before! If you're using a linux machine or a Mac, you should have a terminal installed already.
If you're using a Windows machine, this can be a bit more complicated. If you've already [installed WSL](https://learn.microsoft.com/en-us/windows/wsl/install), then using that should be the most straightforward way to do it.
If not, the easiest thing to do will be to use the ARE terminal: [click here](https://docs.access-hive.org.au/getting_started/are/) for instructions.

Then, you need to clone your repo: to do this, it's just `git clone`, followed by the url of your fork. You'll need to change this URL to your own fork!

```bash
$ git clone https://github.com/charles-turner-1/cosima-hackathon-2025-fork-and-pr
```

You then need to **c**hange **d**irectory (cd) into the repo:
```bash
$ cd cosima-hackathon-2025-fork-and-pr/
```

At this point, you can check what's going on with git by using git status:
```bash
$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```

Cool! We can see we're on the main branch, and everything is up to date. Time to create a branch! 

To do so, we're going use `git checkout -b`. What does this mean? 

- `checkout` generally means 'change to another branch`.
- `-b` means 'create a new branch'.

(There are a couple of other ways of doing it, but this is how I've always made new branches)

Now we need to decide on a branch name. I'm just going to add my name to the contributors, so let's call it that:

```bash
$ git checkout -b add-name-to-contributors
Switched to a new branch 'add-name-to-contributors'
$ git status
On branch add-name-to-contributors
nothing to commit, working tree clean
```

That's it! We've made our new branch! 

# Pushing changes

[Pushing changes](PUSH-CHANGES.md).
