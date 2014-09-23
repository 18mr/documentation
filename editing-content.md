This file is a quick and easy guide for campaigners who want to start editing content themselves in the new stack. It assumes you're already up and running with all of the basic tools that power 18MR's new stack: GitHub, prose.io, and ActionNetwork.

The reason that this workflow exists is that once changes are pushed to the GitHub server, they're live on the web. We want to avoid publishing mistakes and breaking the website at all costs, and this also helps the tech team monitor who's making which edits, and help you out whenever necessary.

## Step One: Fork It!

First, you need to create your own branch of the repository you want to work with. Navigate to the repository that you want to make a copy of.

<img src="https://cloud.githubusercontent.com/assets/2704279/4381217/b986275c-4372-11e4-8e0d-d5fda92fd6c0.PNG">

Then, go ahead and fork it by clicking "fork" in the upper righthand corner. Land the fork in your personal GitHub account.

Now you can edit your fork without affecting the production site! You know, to prevent any untoward mistakes.

## Step Two: Edit Your Content in Prose

Go to [prose.io](http://prose.io) and authorize it to access your GitHub account. Prose is amazing because it not only helps you learn Markdown, the markup format that we use to write pages for the website, but it also lets you preview the things you write so you know what you're getting yourself into.

Open up your personal GitHub account and find the repository you want to edit. Then, go to town!

<img src="https://cloud.githubusercontent.com/assets/2704279/4381492/02c19c0e-4377-11e4-9325-2f049a24864b.PNG">

### Markdown

You'll notice that Prose uses this funny markup and plain text. This markup is called Markdown, and Prose's help (the ? in the top menu) will explain some basics. You can also (dive into the more complex Markdown documentation here](http://daringfireball.net/projects/markdown/basics).

_N.B.: image insertion seems to be broken in Prose. If you're going to add images to the site, [let Cayden know](mailto:cayden@18millionrising.org), or you may set up Git on your desktop computer (tutorial coming soon)._

When you're done making your edits, save your changes using the disk icon. Saving in GitHub is called making a "commit." You'll be asked to describe your change--this is standard procedure for making commits, so other team members can quickly ascertain what you did, and every file that is changed in that commit will be labeled accordingly.

## Step Three: Create a Pull Request

Once you've made your commit, navigate back to your forked version of the repository in GitHub. You'll notice a little green button next to the branch dropdown.

<img src="https://cloud.githubusercontent.com/assets/2704279/4381570/3059548a-4378-11e4-905e-902b44173fa4.PNG">

Click the little green button. You'll be placed on the page to create a pull request, which means you're asking for your code to be checked out and committed to the production site's branch. If nothing appears, or if you can't create a pull request because there's nothing to compare, click the "edit" button to pick a new set of branches.

<img src="https://cloud.githubusercontent.com/assets/2704279/4381573/338300de-4378-11e4-843f-89226d6af046.PNG">

You'll be able to choose which repositories you're comparing, and then which branches. Because most sites will be located in the _gh-pages_ branch, you'll want to choose that branch in both the base fork (on 18mr's organizational account) and the head fork (the one you created in your personal GitHub account). It'll look like this: 

<img src="https://cloud.githubusercontent.com/assets/2704279/4381750/f14fbd6c-437a-11e4-993e-fbfd6670e481.PNG">

Now you're ready to add a little detail to explain your pull request, and click _Create Pull Request_. You're done! Cayden and/or the tech team will review your code and decide if they want to merge it with the production branch.