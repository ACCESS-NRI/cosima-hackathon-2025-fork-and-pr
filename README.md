# COSIMA Hackathon 2025: Forking Repositories, Making Pull Requests

#### List of Contributors
- Boaty McBoatface, 18th August 2025
- Charles Turner, 18th August 2025

### This repository is an introduction to forking a repository in order to make a pull request

For GitHub repositories you didn't create yourself, the default way to contribute is:
1. *Fork* the repository.
2. *Create a new branch*.
3. *Push some changes* to that branch.
4. *Create a pull request*.

In this repository, we're going to walk through a pared down example of what that looks like. 

For repositories you do have write access to (if you don't know what that means don't worry!), the process is very similar, except you won't need to create a fork.
___

# Forking the repository

### What is forking?

Forking is a way of telling GitHub "create a carbon copy of this repository that I own". People might do this for lots of reasons - one of them being to take someone elses work, and do something new and different with it. Much like a fork in the road, this could then take the code down a new path - which is why we call it forking. 

When you fork a repository, you can also use a Pull Request to contribute it back to the original repository - which is what we're going to do today.

#### How do I fork a repository

https://github.com/ACCESS-NRI/cosima-hackathon-2025-fork-and-pr

It's as simple as clicking this button here!

<img width="1275" height="314" alt="Screenshot 2025-08-18 at 11 07 53 am" src="https://github.com/user-attachments/assets/1b82d0b1-d7d2-4bda-8371-415f13d4d5ae" />

This should then send you to a page like this:

<img width="1074" height="722" alt="Screenshot 2025-08-18 at 3 05 01 pm" src="https://github.com/user-attachments/assets/6cde6f61-2053-4b4f-8f9d-de2b78586d43" />

Hit Create Fork - you can change the name and description if you like - before redirecting you to a page like this:

<img width="1467" height="818" alt="Screenshot 2025-08-18 at 3 06 17 pm" src="https://github.com/user-attachments/assets/52925caa-d3ce-459c-ab3b-51cfc1395a07" />


# Creating a new branch

We'll be doing the next couple of bits from the command line - but don't worry if you've never used it before! If you're using a linux machine or a Mac, you should have a terminal installed already. If you're using a Windows machine, the easiest way to do this is to install WSL.

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

Now let's add our name to the list of contributors.

# Pushing changes



# Creating a Pull Request
