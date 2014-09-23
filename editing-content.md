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

Make sure you navigate to your personal editing branch!

<img src="https://cloud.githubusercontent.com/assets/2704279/4381492/02c19c0e-4377-11e4-9325-2f049a24864b.PNG">

You'll notice that Prose uses this funny markup and plain text. This markup is called Markdown, and Prose's help (the ? in the top menu) will explain some basics. You can also (dive into the more complex Markdown documentation here](http://daringfireball.net/projects/markdown/basics).

## Step Three: Create a Pull Request