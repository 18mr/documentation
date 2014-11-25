This file assumes that you have [set up Jekyll locally](https://github.com/18mr/documentation/blob/master/local-site.md).

The reason that this workflow exists is that once changes are pushed to the GitHub server, they're live on the web. We want to avoid publishing mistakes and breaking the website at all costs, and this also helps the tech team monitor who's making which edits, and help you out whenever necessary.

## Step One: Sync It!

You should have a fork living on your local machine by now. If not, there are [complete instructions here](https://github.com/18mr/documentation/blob/master/local-site.md).

Open up the GitHub application and [make sure you update your fork from the trunk before proceeding](https://github.com/18mr/documentation/blob/master/sync-your-fork.md). This ensures that you aren't adding to an outdated version of the site that might look different when you submit a pull request. There should be a little notification next to the "sync" button in the upper righthand corner of GitHub that indicates there's something fresh to update from the server.

## Step Two: Edit It!

Fire up your text editor. I use Notepad++, but it's Windows-only. Take a look around at text editors and find one that works for you.

In general, you'll be editing files that are in the _posts folder. Much of the other content is required to build and style the site, so that can be left alone. The only exception are pages, which may be standalone .html files, or can be found in their own folders. This documentation will focus on editing posts.

If you're making a new file in the _posts folder, say, to host a new petition, you'll want to make sure your file has the right filename. Every file in the _posts folder has this format filename: 

    2014-MO-DA-unique-slug.md

![petitions](https://cloud.githubusercontent.com/assets/2704279/5173174/30455d98-73db-11e4-9a4d-d9310188313f.PNG)

This tells Jekyll how to process the file, and is crucial when you create a new file.

Keep in mind that every time you save your file, Jekyll will regenerate the webpage at _http://localhost:4000_. This is useful so as you work, you can make sure your pages look up to snuff.

### Metadata

In a new file, you'll need to add one more crucial element to make sure Jekyll can process your file. At the top of every _pages file, you'll notice some information that falls between two sets of dashes. That stuff is the "YAML Front Matter," and it tells Jekyll how to process the file to create a beautiful, styled webpage. You need, at minimum, to place two sets of three dashes at the top of your document so Jekyll will process it.

![frontmatter](https://cloud.githubusercontent.com/assets/2704279/5173219/a9d3b542-73db-11e4-9cbb-1adb8012f4e0.PNG)

At minimum, for a new petition page, your Front Matter & post body should look like this.

For more information about creating the right Front Matter, [check out this guide](http://jekyllrb.com/docs/frontmatter/). Before creating Front Matter of your own, it might be a good idea to check out other posts that exist in a similar category to the one you'd like to create.

### Markdown

You'll also notice that our website uses this funny markup and plain text. This markup is called Markdown, and you can [dive into the more complex Markdown documentation here](http://daringfireball.net/projects/markdown/basics). The idea is pretty simple--offering a plaintext way of generating styled pages, with an emphasis on writing instead of coding.

### Images

If you want to add images to your post that aren't included in the petition body, you'll first want to add the image to the site directory. _On your local machine_, put your image in a directory in the website's directory on your hard drive. In general, images should be stored in a folder unique to the post, such as _static/images/unique-slug/_.

To then include that image in your post, you can use either HTML or the Markdown syntax to call it.

    ![alternate text]({{ baseurl }}/static/images/unique-slug/image-filename.jpg)

OR

    <img src="{{ baseurl }}/static/images/unique-slug/image-filename.jpg" />

Notice that in both formats, there is the tag _baseurl_ in double curly brackets. This tells Jekyll to start the file path with whatever is specified as your site's base url, so when you upload everything to GitHub the filepath won't break.

### Action Network

If you're just making a petition page, Action Network already provides all the goodies you need to roll out a new petition.

Check out the Action Network document for more information on how to generate the code you need and make your petition look fabulous.

## Step Three: Upload It!

When you're done making your edits, save your changes in your text editor and create your commit. Saving in GitHub is called making a "commit." You'll be asked to describe your change--this is standard procedure for making commits, so other team members can quickly ascertain what you did, and every file that is changed in that commit will be labeled accordingly.

You can easily make your commit using the GitHub application. Describe the commit, then confirm the commit.

![commit](https://cloud.githubusercontent.com/assets/2704279/5173281/2e638918-73dc-11e4-8a37-8d3cd29a4c30.PNG)

As you can see, we're making a commit to the gh-pages branch. This is where it should be if you want it to be part of the site!

You'll also notice that a little flag pops up next to "Sync" in the upper righthand corner. Sync your work to the server.

## Step Four: Create a Pull Request

Once you've made your commit, it's time to add it to the production site. Back in your repository on GitHub.com, you'll see that there's a little green button in the upper lefthand corner.

<img src="https://cloud.githubusercontent.com/assets/2704279/4381570/3059548a-4378-11e4-905e-902b44173fa4.PNG">

Click the little green button. You'll be on the page to create a pull request, which means you're asking for your code to be checked out and committed to the production site's branch. If nothing appears, or if you can't create a pull request because there's nothing to compare, click the "edit" button to pick a new set of branches.

<img src="https://cloud.githubusercontent.com/assets/2704279/4381573/338300de-4378-11e4-843f-89226d6af046.PNG">

You'll be able to choose which repositories you're comparing, and then which branches. Because most sites will be located in the _gh-pages_ branch, you'll want to choose that branch in both the base fork (on 18mr's organizational account) and the head fork (the one you created in your personal GitHub account). It'll look like this: 

<img src="https://cloud.githubusercontent.com/assets/2704279/4381750/f14fbd6c-437a-11e4-993e-fbfd6670e481.PNG">

Now you're ready to add a little detail to explain your pull request, and click _Create Pull Request_. You're done! Cayden and/or the tech team will review your code and decide if they want to merge it with the production branch.
