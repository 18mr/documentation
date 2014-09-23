This file is a quick and easy guide for campaigners who want to start editing content themselves in the new stack. It assumes you're already up and running with all of the basic tools that power 18MR's new stack: GitHub, prose.io, and ActionNetwork.

The reason that this workflow exists is that once changes are pushed to the GitHub server, they're live on the web. We want to avoid publishing mistakes and breaking the website at all costs, and this also helps the tech team monitor who's making which edits, and help you out whenever necessary.

## Step One: BYOB (Bring Your Own Branch)

First, you need to create your own branch of the repository you want to work with. Navigate to the branch that you want to make a copy of. _If you're working with an 18MR site that's hosted on GitHub Pages, please choose the gh-pages branch._

<img src="https://cloud.githubusercontent.com/assets/2704279/4381217/b986275c-4372-11e4-8e0d-d5fda92fd6c0.PNG">

Then, go ahead and create a new branch using the "branches" dropdown. Name it something evocative that lets other team members know what it is. Like your name, for instance.

<img src="https://cloud.githubusercontent.com/assets/2704279/4381214/b66cfc3a-4372-11e4-8b05-94dd678574c3.PNG">

Now you can edit your branch without negatively affecting the production site!

## Step Two: Edit Your Content in Prose

Go to [prose.io](http://prose.io) and authorize it to access your GitHub account. Prose is amazing because it not only helps you learn Markdown, the markup format that we use to write pages for the website, but it also lets you preview the things you write so you know what you're getting yourself into.

Make sure you navigate to your personal editing branch before you begin!

<img src="https://cloud.githubusercontent.com/assets/2704279/4381492/02c19c0e-4377-11e4-9325-2f049a24864b.PNG">

### Markdown

You'll notice that Prose uses this funny markup and plain text. This markup is called Markdown, and Prose's help (the ? in the top menu) will explain some basics. You can also (dive into the more complex Markdown documentation here](http://daringfireball.net/projects/markdown/basics).

_N.B.: image insertion seems to be broken in Prose. If you're going to add images to the site, [let Cayden know](mailto:cayden@18millionrising.org), or you may set up Git on your desktop computer (tutorial coming soon)._

When you're done making your edits, save your changes using the disk icon. Saving in GitHub is called making a "commit." You'll be asked to describe your change--this is standard procedure for making commits, so other team members can quickly ascertain what you did, and every file that is changed in that commit will be labeled accordingly.

## Step Three: Create a Pull Request

Once you've made your commit, navigate back to the site project page in GitHub. You'll notice a little box up top that is just casually remarking that you changed something in a branch, like this: 

<img src="https://cloud.githubusercontent.com/assets/2704279/4381570/3059548a-4378-11e4-905e-902b44173fa4.PNG">

Click that green button. You'll be placed on the page to create a pull request, which means you're asking for your code to be checked out and committed to the production site's branch. If nothing appears, or if you can't create a pull request because there's nothing to compare, click the "edit" button to pick a new set of branches.

<img src="https://cloud.githubusercontent.com/assets/2704279/4381573/338300de-4378-11e4-843f-89226d6af046.PNG">

The first branch you choose should be the branch you _want_ your changes to appear in. In most cases this'll be _gh-pages_. The second branch should be your personal editing branch, in this case, _cayden_.

<img src="https://cloud.githubusercontent.com/assets/2704279/4381575/35545d0e-4378-11e4-9641-7412b8f77f7d.PNG">

Now you're ready to add a little detail to explain your pull request, and click _Create Pull Request_. You're done! Cayden and/or the tech team will review your code and decide if they want to merge it with the production branch.

### Don't Forget to Update Your Editing Branch!

If you're coming back to an editing branch after a little time away, please make sure your branch is up to date. You can create a pull request to sync your editing branch with the production branch by inverting Step Three above.