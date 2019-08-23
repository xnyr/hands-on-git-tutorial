# Hands-on git Tutorial
Welcome! This tutorial is meant to be a fairly short, hands-on demonstration of how to use git/GitHub, designed for those new to the technology or platform. Note that git is the version control system, while GitHub is simply a platform used for hosting.

## Forking
Let's start off with forks. In areas where version control is used (such as software development), it is often that people will be joining existing projects instead of starting completely new ones. If everyone were to work in collection of files, it would get messy very quickly. Forks allow us to avoid that mess by creating a separate copy of a repository, then work by ourselves or in a smaller group, and later request for the changes we make to be merged with the main repository.

Let's do that now. In the upper-right corner of the GitHub layout there are three buttons. The furthest one to the right is fork. Press that, and you'll be prompted to create your own copy. Select your profile, and give GitHub a few seconds to work its magic. Hopefully all went well and you now have your very own copy of this repository!

## Cloning
While we could technically alter some things from the GitHub interface online, that wouldn't be done in a professional setting. Instead, we're going to "clone" our repository to make changes to our files locally. Cloning is essentially our initial copying of our files from GitHub to our local setup.

First, create a directory (folder) for your project to go. Then, navigate to that folder using your command line. Back on the page for your GitHub repo, find the green button to the right that says "Clone or Download". Click that, then copy the link in the box towards the bottom. Then, in the terminal where you're inside your newly-created directory, enter the following:

```
git clone your_clone_link
```

...replacing "your_clone_link" with that link you just copied from your page. Paste in the terminal by either right-clicking and selecting Paste, or with ctrl-shift-v.

Once you press enter you should notice that git downloads the files you have in your repository. Use the command "ls" (Mac and Linux) or "dir" (Windows) and you should be able to see that you've correctly downloaded the files.

## Branching

Branches are much like forks, but contained within your own copy of the repository. Creating a branch will allow you to make changes to your copy without fear of ruining something or having to find a way to undo what was done. To create a branch and start making changes from within that branch, use the following commands:

```
git branch testing
git checkout testing
```

The branch command is used to create a new branch. The checkout command will put us into that branch. Every repository starts with a default branch called 'master'. The set of commands above creates and puts us into a branch called 'testing'. You can check with with the status command:

```
git status
```

The first line of output should be 'On branch testing', if you've been following along so far. The lines below that will show tracked and untracked files, which will be useful later on.

## Making Changes

Now that we've got a testing branch, let's make changes to the text file in the repository. Open it and you'll find that it contains the following:

```
Hello, world! Welcome to my git tutorial!

```

Let's change that line a bit and add a new one, so that it looks something like this:

```
Hello, GitHub! Welcome to my git tutorial!

I'm getting a good grasp on this!

```


We're making good progress so far! Now that we've made some changes locally, we need to update our repository so that those changes are reflected online. We can do this with the series of commands below:

```
git add hello-git.txt
git commit -m "commit message"
git push origin testing
```

The add command allows us to add files that we have changed or added to our list of things to send to the repository. Using commit -m "message" stages all the files that we've added and allows us to attach a message (within the quotation marks) to our changes in order to document them. Once we've commited our changes, the push command will allow us send them to our repository on GitHub. Since we're intending to have multiple branches, we specify "origin testing" as well. Since the repository doesn't have the testing branch quite yet, it'll create it during this process as well.

## Merging branches

Now that we've made changes to our testing branch and pushed them to GitHub, we're at a point where we can merge our branches with the following commands:

```
git checkout master
git merge testing
git push
```

First we make sure we're on the master branch. Then, we merge our testing branch. Lastly, push the changes so that they're reflected in the master branch on GitHub. You are now free to delete the branch as well, if you so desire.

Congratulations! You've successfully forked an existing repository and made changes to it!

## Extras

Typically, once you're at a point where you're ready to contribute to an existing project, you would open a "pull request" in the repository that your project is forked from. This can be done near the top of GitHub's interface on a fork. That pull request would then be reviewed and (hopefully) merged by someone with the know-how and permissions to do so.

Beyond that, an issue of merge conflicts can also arrise. The difficulty in solving a conflict depends on its severity. I won't include any information on that here, as it's a bit of an advance topic and can strongly depend on the situation. Just know that at some point it may be an issue that requires some more in-depth searching.


