# COSIMA Hackathon 2025: Forking Repositories, Making Pull Requests

#### List of Contributors
- Boaty McBoatface, 18th August 2025

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

That's it! We've made our new branch! 

# Pushing changes

Now let's add our name to the list of contributors. I've done this with `vim`: `$ vim README.md`, but use whatever editor you're comfortable with:

<img width="1717" height="933" alt="Screenshot 2025-08-18 at 3 42 52 pm" src="https://github.com/user-attachments/assets/a2be3cc3-5e27-405b-8dcd-25e59bad06e6" />

Once we've saved our changes, let's run `git status` again to check what's changed:
```bash
$ git status
git status                                                                         
On branch add-name-to-contributors
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```

Git can see that we've updated the `README.md` file, and it knows we're on the `add-name-to-contributors` branch. Let's run `git diff` to check our changes:
```diff
$ git diff                                                                   
diff --git a/README.md b/README.md
index b26dd66..bbcfa33 100644
--- a/README.md
+++ b/README.md
@@ -2,6 +2,7 @@

 #### List of Contributors
 - Boaty McBoatface, 18th August 2025
+- Charles Turner, 18th August 2025

 ### This repository is an introduction to forking a repository in order to make a pull request
```

So git can see *that* we've made a change, *where* our changes are, and *what* we've changed. So lets send our changes back to github. This is a 3 step process: `add`, `commit`, and `push`.


#### Step 1: Adding changes

The first thing to do is add your changes. There are a couple of ways to do this:
1. Be specific
```bash
$ git add $FILENAME
```

This adds whatever you put in `$FILENAME` to your 'staging area'. You can add multiple files at once:

```bash
$ git add $FILENAME1 $FILENAME2
```

In this instance, it would be `$ git add README.md`.

2. Add everything *I've updated*.

If you are feeling a little more carefree, you can use 
```bash
$ git add --update
```

This will add every file which git already knows about and you have changed to your staging area. This is generally a bit easier to use, but slightly more error prone.

3. Add *everything*.

If you want to throw caution to the wind, you can use
```bash
$ git add .
```

This will add everything in your current directory and it's subdirectories to your staging area. This can go wrong - if you've added lots of files (by accident or not), they can all get added when you do this. Best to try to avoid this is possible - it's a bit like `$ git add --YOLO`.

___

However, in this instance, all 3 of these methods will lead to the same outcome:
```bash
$ git status
On branch add-name-to-contributors
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	modified:   README.md
```

### Step 2: Committing changes

This is pretty straightforward: you can either just run 
```bash
$ git commit
```

Git will then throw you into an editor to add a commit message. Alternatively, you can run
```bash
$ git commit -m "My commit message"
```

In my instance, I'm going to do the latter:
```bash
 git commit -m "Add name to contributors (CT)"                                   
[add-name-to-contributors 18a5f4a] Add name to contributors (CT)
 1 file changed, 1 insertion(+)
```

Try to write a descriptive message - if you come back to just "WIP" (Work In Progress), you might wish you'd given future you more context.

Let's run `git status` again and see what's happened:
```bash
$ git status
git status                                                                   
On branch add-name-to-contributors
nothing to commit, working tree clean
```

At this point, we can also run `git log` to see what we committed:
```bash
$ git log
commit 18a5f4a4f7de101f89cb7450ce2b72c56a538525 (HEAD -> add-name-to-contributors)
Author: Charles Turner <charles.turner@anu.edu.au>
Date:   Mon Aug 18 15:59:57 2025 +0800

    Add name to contributors (CT)

commit d53654aa1a2ec8aa75dd3d5279729ced484ed1fe (origin/main, origin/HEAD, main)
Author: Charles Turner <52199577+charles-turner-1@users.noreply.github.com>
Date:   Mon Aug 18 17:34:36 2025 +1000

    Update README.md

    Sketch out tutorial

commit 5a61b52ba4ecc0d2ff0add95fdb60f6addbd8488
Author: Charles Turner <52199577+charles-turner-1@users.noreply.github.com>
Date:   Mon Aug 18 12:55:24 2025 +1000

    Initial commit
```
You can see the commit we just made, as well as the previous ones.

### Step 3: Push our commit

To push our commit, just run `git push`:
```bash
$ git push

fatal: The current branch add-name-to-contributors has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin add-name-to-contributors

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'.
```

Unless you've configured `push.autoSetupRemote`, **this will fail**. However, it helpfully tells us exactly how to fix it, so let's try that (I still do this every time): 

```bash
$ git push --set-upstream origin add-name-to-contributors
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 11 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 545 bytes | 545.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
remote:
remote: Create a pull request for 'add-name-to-contributors' on GitHub by visiting:
remote:      https://github.com/charles-turner-1/cosima-hackathon-2025-fork-and-pr/pull/new/add-name-to-contributors
remote:
To https://github.com/charles-turner-1/cosima-hackathon-2025-fork-and-pr
 * [new branch]      add-name-to-contributors -> add-name-to-contributors
branch 'add-name-to-contributors' set up to track 'origin/add-name-to-contributors'.
```

If you look at your fork now, you should see something like this:

<img width="941" height="721" alt="Screenshot 2025-08-18 at 4 06 40 pm" src="https://github.com/user-attachments/assets/0dc046e1-44c2-4e12-b11b-cd7c08966363" />

Handily, the output of `$ git push` above also told us how to make a Pull Request: so let's do that!

# Creating a Pull Request

From our previous commit, we can see this line:
```bash
$ git push --set-upstream origin add-name-to-contributors
...
remote: Create a pull request for 'add-name-to-contributors' on GitHub by visiting:
remote:      https://github.com/charles-turner-1/cosima-hackathon-2025-fork-and-pr/pull/new/add-name-to-contributors
...
```

Lets follow that link to make our pull request! Click on it, and it should take you to something like this:

<img width="1511" height="942" alt="Screenshot 2025-08-18 at 4 08 52 pm" src="https://github.com/user-attachments/assets/fb80c4aa-453b-4b04-baca-daada011595b" />

All we need to do now is add a useful description, and then click Create Pull Request:

<img width="918" height="585" alt="Screenshot 2025-08-18 at 4 10 20 pm" src="https://github.com/user-attachments/assets/f8b6a1c4-5c30-43ec-b0a6-24c25a7d4b0f" />

Once you've done this, your Pull Request should be visible [here](https://github.com/ACCESS-NRI/cosima-hackathon-2025-fork-and-pr/pulls)! That's it!

<img width="1391" height="461" alt="Screenshot 2025-08-18 at 4 10 51 pm" src="https://github.com/user-attachments/assets/b20eea8f-47c6-457c-a5d8-5f5db0347b13" />

___
# Pushing changes to Jupyter notebooks
