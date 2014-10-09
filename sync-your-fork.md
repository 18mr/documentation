This file is a follow-up to [the one about editing content](https://github.com/18mr/documentation/blob/master/editing-content.md). Once a pull request has been processed or new code has been added to the main repository, you want to update yours so you have the most current content to work with. Basically, you're going to create and merge your own pull request from the master into your own repository.

Navigate to the fork in your _personal_ GitHub account (not the organizational one).

You'll be able to tell you need to update when you see the following message at the top of your fork's directory:

![behind-ghpages](https://cloud.githubusercontent.com/assets/2704279/4584287/9a5d6410-4ff9-11e4-9d6a-7fb35d5b821b.PNG)

_When working on websites hosted on GitHub Pages, you'll want to make sure you're in the gh-pages branch of the project!_

Click "Pull Request."

At first, you might get a message like this: 

![switchbase](https://cloud.githubusercontent.com/assets/2704279/4584289/9a67c946-4ff9-11e4-801b-5a3e58efb91c.PNG)

You'll need to switch the base. The default compare is assuming your fork, which you've edited, is _ahead of_ the master. But in this case, you're trying to catch your fork up to whatever's been going on in the master, so click "switching the base."

Now, you should see a list of new commits, and you can also review which files have been changed before creating the pull request. It'll look like this:

![createpullrequest](https://cloud.githubusercontent.com/assets/2704279/4584288/9a64d0e2-4ff9-11e4-8fcd-8c4c9c8a3b55.PNG)

Click "Create Pull Request."

Navigate back out to your repository. There should be a __1__ next to "Pull Requests" in your righthand menu. Click that.

Here, you will be given the option to review the merge and then confirm it. If you're just rolling through these steps, there shouldn't be any issues with your merge, and you should be able to merge automatically by scrolling down to the bottom of the page and merging that pull request.

![merge](https://cloud.githubusercontent.com/assets/2704279/4584291/9b3aed94-4ff9-11e4-8f93-299ca6d7a801.PNG)

And, you're done! Your personal sandbox fork should be 100% up-to-date.
