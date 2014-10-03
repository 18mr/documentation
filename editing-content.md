This file is a quick and easy guide for campaigners who want to start editing content themselves in the new stack.

The reason that this workflow exists is that once changes are pushed to the GitHub server, they're live on the web. We want to avoid publishing mistakes and breaking the website at all costs, and this also helps the tech team monitor who's making which edits, and help you out whenever necessary.

## Step One: Fork It!

First, you need to create your own fork of the repository you want to work with. Navigate to the repository that you want to make a copy of.

<img src="https://cloud.githubusercontent.com/assets/2704279/4381217/b986275c-4372-11e4-8e0d-d5fda92fd6c0.PNG">

Then, go ahead and fork it by clicking "fork" in the upper righthand corner. Land the fork in your personal GitHub account.

Now you can edit your fork without affecting the production site! You know, to prevent any untoward mistakes.

## Step Two: Edit Your Content

You can both edit existing content or create new pages right in GitHub. Navigate to your _personal_ repository and either open up an existing file to edit it, or create a new one by clicking on the + after the filepath links up top:

![create a new post](https://cloud.githubusercontent.com/assets/2704279/4512637/aad00b06-4b42-11e4-8e24-dda7bc9d98c4.PNG)

If you create a new post, you'll see a plain text editor box. Be sure to create a filename that is consistent with [Jekyll's naming conventions](http://jekyllrb.com/docs/posts/). That means, your filename will be something like: YEAR-MONTH-DAY-BLOGTITLE.md.

![edit your new post](https://cloud.githubusercontent.com/assets/2704279/4512638/aad050e8-4b42-11e4-8101-537ded83493f.PNG)

On the other hand, if you're editing an existing post, you'll first see the "preview" pane when you open the file. It'll look like this:

![open an existing file](https://cloud.githubusercontent.com/assets/2704279/4512635/aacd53de-4b42-11e4-8e2f-3be0d5256c5c.PNG)

When you click the pencil icon in the upper righthand corner of the preview box, you'll get to a text box.

### Metadata

You probably notice that there is this weird little table of information in the last screenshot. That stuff is the "YAML Front Matter," and it tells Jekyll how to process the file to create a beautiful, styled webpage. You need, at minimum, to place two sets of three dashes at the top of your document so Jekyll will process it.

For more information about creating the right Front Matter, [check out this guide](http://jekyllrb.com/docs/frontmatter/). Before creating Front Matter of your own, it might be a good idea to check out other posts that exist in a similar category to the one you'd like to create.

### Markdown

You'll also notice that our website uses this funny markup and plain text. This markup is called Markdown, and you can [dive into the more complex Markdown documentation here](http://daringfireball.net/projects/markdown/basics). The idea is pretty simple--offering a plaintext way of generating styled pages, with an emphasis on writing instead of coding.

_N.B.: you can't insert images automatically into a GitHub page. Check out [this documentation](https://github.com/18mr/documentation/blob/master/uploading-images.md) for a guide on how to upload your images and make them accessible._

When you're done making your edits, save your changes by scrolling down and creating your commit. Saving in GitHub is called making a "commit." You'll be asked to describe your change--this is standard procedure for making commits, so other team members can quickly ascertain what you did, and every file that is changed in that commit will be labeled accordingly.

![create a commit](https://cloud.githubusercontent.com/assets/2704279/4512638/aad050e8-4b42-11e4-8101-537ded83493f.PNG)

## Step Three: Create a Pull Request

Once you've made your commit, it's time to add it to the production site. Back in your fork's main directory, you'll see that there's a little green button in the upper lefthand corner.

<img src="https://cloud.githubusercontent.com/assets/2704279/4381570/3059548a-4378-11e4-905e-902b44173fa4.PNG">

Click the little green button. You'll be on the page to create a pull request, which means you're asking for your code to be checked out and committed to the production site's branch. If nothing appears, or if you can't create a pull request because there's nothing to compare, click the "edit" button to pick a new set of branches.

<img src="https://cloud.githubusercontent.com/assets/2704279/4381573/338300de-4378-11e4-843f-89226d6af046.PNG">

You'll be able to choose which repositories you're comparing, and then which branches. Because most sites will be located in the _gh-pages_ branch, you'll want to choose that branch in both the base fork (on 18mr's organizational account) and the head fork (the one you created in your personal GitHub account). It'll look like this: 

<img src="https://cloud.githubusercontent.com/assets/2704279/4381750/f14fbd6c-437a-11e4-993e-fbfd6670e481.PNG">

Now you're ready to add a little detail to explain your pull request, and click _Create Pull Request_. You're done! Cayden and/or the tech team will review your code and decide if they want to merge it with the production branch.
