# team-up-with-git
Team version control practice repo

***

## Step 1: Clone the repo
Open your terminal, navigate to a place where you work on coding projects, and run the following command:
```
git clone https://github.com/abcdbug/team-up-with-git.git
```

If you have ssh setup on github you can do the following instead:
```
git clone git@github.com:abcdbug/team-up-with-git.git
```

## Step 2: Checkout a branch
First cd into the repo
```
cd team-up-with-git
```

And then checkout a new branch
```
git checkout -b unique-branch-name
```
Remember, DON'T WORK IN MASTER.

## Step 3: Make changes to the repo
Add a new file or modify an existing file, save your changes, then run the following command:
```
git status
```

## Step 4: Stage and commit your files
Run the following command to stage your files:
```
git add name(s)_of_file(s)_you_changed
```

Then commit your changes.
```
git commit -m "Added new file that does this and that"
```

## Step 5: Check status of your branch vis-a-vis master
Before pushing your code to the origin, first check to see if master has changed since you branched.
```
git co master
git fetch
git status
```

In an ideal world where everyone remembers not to work in master, you should always be able to `pull` master.
Since life doesn't always go as planned, fetch first.
If `git status` says you can fast-forward, then `git pull`.

## Step 6: Push your branch to origin
Assuming there are no changes on master since you branched, push your branch to origin.
```
git checkout unique-branch-name
git push -u unique-branch-name
```

If master, has changed, you will need to rebase on master and then `git push`.

```
git checkout unique-branch-name
git rebase master
git push -u unique-branch-name
```
If the rebase gives you an error, it means you and somebody else where touching the same part of the same files.
That's when we start to think about using the project management tools provided by github/gitlab.
