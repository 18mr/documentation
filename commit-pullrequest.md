Here's how you get code from something you write on your computer onto the production server.

## Create a Commit

When you're done making your edits, save your changes in your text editor and create your commit. Saving in GitHub is called making a "commit." You'll be asked to describe your change--this is standard procedure for making commits, so other team members can quickly ascertain what you did, and every file that is changed in that commit will be labeled accordingly.

You can easily make your commit using the GitHub application. Describe the commit, then confirm the commit.

![commit](https://cloud.githubusercontent.com/assets/2704279/5173281/2e638918-73dc-11e4-8a37-8d3cd29a4c30.PNG)

As you can see, we're making a commit to the gh-pages branch. This is where it should be if you want it to be part of the site!

You'll also notice that a little flag pops up next to "Sync" in the upper righthand corner. Sync your work to the server.

## Create a Pull Request

Once you've made your commit, it's time to add it to the production site. Back in your repository on GitHub.com, you'll see that there's a little green button in the upper lefthand corner.

<img src="https://cloud.githubusercontent.com/assets/2704279/4381570/3059548a-4378-11e4-905e-902b44173fa4.PNG">

Click the little green button. You'll be on the page to create a pull request, which means you're asking for your code to be checked out and committed to the production site's branch. If nothing appears, or if you can't create a pull request because there's nothing to compare, click the "edit" button to pick a new set of branches.

<img src="https://cloud.githubusercontent.com/assets/2704279/4381573/338300de-4378-11e4-843f-89226d6af046.PNG">

You'll be able to choose which repositories you're comparing, and then which branches. Because most sites will be located in the _gh-pages_ branch, you'll want to choose that branch in both the base fork (on 18mr's organizational account) and the head fork (the one you created in your personal GitHub account). It'll look like this: 

<img src="https://cloud.githubusercontent.com/assets/2704279/4381750/f14fbd6c-437a-11e4-993e-fbfd6670e481.PNG">

Now you're ready to add a little detail to explain your pull request, and click _Create Pull Request_. You're done! Cayden and/or the tech team will review your code and decide if they want to merge it with the production branch.
