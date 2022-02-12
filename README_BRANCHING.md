# Branching #

This readme describes the branching scheme that you will use throughout the capstone. The `main` branch is the _**sacred**_ branch. No development should ever be done directly in this branch.

## Developer branches

Each team member has a branch with their name. This is the only branch in which the team member should do any of their development work.

Once a task is completed the developer should commit the changes to their branch and then merge the completed work back to the main branch.

**IMPORTANT** - the `main` branch should always have the lastest working code in it. In other words, it should NEVER have any merge conflicts pushed to it.

### Branching Workflow ###

#### Step 1 - Checkout your working branch

Each devolper begins by switching to (checking out) their own branch.

If my name is Gregor, then my branch would be called `gregor`, and I would switch to the branch as follows
```
git checkout gregor
```


#### Step 2 - Complete your task AND commit

Get the next task that is assigned to you.

Do ALL of your work in your branch, then commit and push your code

* Make your code changes
* Add and commit your code
```
git add -A
git commit -m "my very descriptive message about the task I completed"
git push
```

It is critical that you both commit and push your changes in this step so that your work is saved to the cloud in case there are merge conflicts in the next steps.

#### Step 3 - Pull the latest changes to the MAIN branch

Other team members will have committed changes to the main branch - you need to pull those changes to your computer.

* Switch to the `main` branch
```
git checkout main
```
* Pull the latest changes
```
git fetch
git pull
```

It is important to execute `git fetch` before you pull because it will ensure that your local repository is aware of all new changes that have been committed and pushed to the cloud.

#### Step 4 - Merge the latest changes into your branch

You first need to merge changes into your own branch. This is to ensure that if there are any merge conflicts, they will be confined to your branch. Remember, the `main` branch should be protected from any merge conflicts, or broken code.

* Switch to your branch
* Merge the `main` branch into your branch

```
git checkout gregor
git merge main
```

#### Step 4b - ONLY IF there are merge conflicts

If there are merge conflicts you **MUST** resolve them in **YOUR** branch

* Make all necessary code changes in your branch to resolve the conflicts
* **REPEAT** steps 2-4

#### Step 5 - Merge completed task into `main`

Once all conflics have been resolved you are ready to merge your code into the `main` branch.

* Switch to the main branch
* Pull changes again to ensure that no new code has been pushed
* Merge your code changes into the main branch
* Push your changes to main

```
git checkout main
git fetch
git pull
# this assumes that there are no new changes
git merge gregor
git push
``` 

#### Step 6 - IMPORTANT switch back to your branch

Repeat Steps 1-5
