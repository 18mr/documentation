Once a pull request has been processed or new code has been added to the main repository, you want to update yours so you have the most current content to work with. Basically, you're going to create and merge your own pull request from the master into your own repository.

Navigate to the fork in your _personal_ GitHub account (not the organizational one).

Click the button that says "New Pull Request." You can find it next to the branches dropdown.

You'll get dropped on a screen that assumes you're trying to take changes you made and integrate them into the master production website. This is what you'd _usually_ do if you were trying to ship a new campaign or blog post. However, we're trying to go in the opposite direction.

On GitHub, a _base fork_ is the version of the project you're trying to add new code to. The _head fork_ is the place you're pulling that new code from. Thus, you should make sure your _base fork_ is your personal project, and the _head fork_ is the master repo, or 18mr/action, for instance. You may need to _compare across forks_. The link to do so is at the start of the "Open New Pull Request" page, like below.

![open a new pull request](https://github.com/18mr/documentation/blob/master/images/comparison.PNG?raw=true)

When you're reviewing your update, your comparison should look like the one below:

![personal is the base fork, organizational is the head fork](https://github.com/18mr/documentation/blob/master/images/compareacross.PNG?raw=true)

Great. Now create that pull request. You'll then be put on a page describing all the changes you're committing. When you scroll down to the bottom, there should be a green box that says 

![this branch has no conflicts with the base branch](https://github.com/18mr/documentation/blob/master/images/noconflicts.PNG?raw=true)

Press that button, confirm the merge, and all the changes will be added to your repository.

Finally, open up your GitHub GUI and synchronize your local files with your remote files. And you're done!

### Why do I have to sync every time?

If you aren't making straightforward changes, you'll have to settle the differences between those changes on the command line. Unless you _want_ to learn the Git command line, we've set this up so you can avoid it by following a couple simple conventions. If you have problems anywhere along the way, let tech know.
