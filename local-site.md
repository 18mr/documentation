So, you've [installed Jekyll](http://internet-inspired.com/wrote/install-jekyll-in-osx-mavericks/) and are ready to dive into editing content. Not so fast: there are a couple things you're going to have to do before you can get under the hood and start creating stuff willy-nilly.

The reason that this workflow exists is to keep track of who edits what, when. If you make a mistake, it's easy to identify what went wrong and revert the live version of the site back to where it was before that point. This makes it easy to fix mistakes, or, better yet, identify them before they get pushed to production.

## Step One: Fork It!

First, you need to create your own fork of the repository you want to work with. Navigate to the repository that you want to make a copy of. That's probably [action](https://github.com/18mr/action) or [18mr, the main website](https://github.com/18mr/18mr), but could be a microsite for a special project, too.

Let's say you need to fork action, so you can add a petition. Make sure you are in the right branch--for some sites, the branch will be _gh-pages_, as shown below.

<img src="https://cloud.githubusercontent.com/assets/2704279/4381217/b986275c-4372-11e4-8e0d-d5fda92fd6c0.PNG">

Then, go ahead and fork it by clicking "fork" in the upper righthand corner. Select your personal GitHub account as the destination of the fork.

Now you can edit your fork without affecting the production site! You know, to prevent any untoward mistakes. This is your version of the site to screw around with as you choose.

In the future, once you've already forked, and are returning to your project, [make sure you update your fork from the trunk before proceeding](https://github.com/18mr/documentation/blob/master/sync-your-fork.md). It's going to save you headaches down the road.

## Step Two: Clone It!

Now you're going to take that fork and download it to your machine. This way, you can work on your local machine, preview changes, and not even be connected to the internet! Great for throwing shit together when you're on an airplane or something.

The easiest way to manage syncing your local clone is through the GitHub application (what we call a Graphical User Interface, or GUI), which is way more robust now than it's ever been. [Download it and set it up.](https://mac.github.com/)

Once you've downloaded GitHub, fire it up. Find the repository you want to clone under the "+" button, and pick a directory to clone it into. I recommend having a folder that contains all your GitHub projects so you can find them easily later.

![clone](https://cloud.githubusercontent.com/assets/2704279/5172612/3ed69cbe-73d6-11e4-939a-0fd71884bcbb.PNG)

Now, you should be able to serve this on your local machine. (Assuming all the installation steps [described here](http://internet-inspired.com/wrote/install-jekyll-in-osx-mavericks/) happened correctly.)

## Step Three: Run It!

Open up Terminal and navigate to the folder you cloned your repository into by typing:

    cd your/filepath/here
  
Once you're in the directory, type:

    jekyll serve --watch
  
Jekyll should now build your site. If you navigate to _http://localhost:4000_ in the browser of your choice, you'll see a local (i.e., not hosted on the internet) version of the website so you can look at the changes you make as you go. The "--watch" tag tells Jekyll to rebuild the site every time a change is detected in the repository. _If you're editing any content, you'll want to have the local server emulator running, so you can preview your changes._

You can now use the text editor of your choice to [create and edit content](https://github.com/18mr/documentation/blob/master/editing-content.md).

If the build fails, you may wish to Google the error. Stack Overflow contains a lot of answers to questions. If you can't figure it out, drop Cayden a line.
