This file is a step-by-step guide to setting up an Action Network petition on the new stack. You'll use some skills from other files in the documentation, but this can also be a stand-alone walkthrough for creating a petition.

## Step One: Load It!

Most of the content displayed on petition pages on http://action.18mr.org is actually drawn directly from [Action Network](http://actionnetwork.org). [Go create an action](https://github.com/18mr/documentation/blob/master/action-network.md).

Once you've set up, you're ready to create a post to house it. Be sure to add relevant tags to the action. This will help us track the kinds of campaigns and issue areas that matter the most to our members in the long-term.

## Step Two: Prep It!

Before you drop your widget into a new post, you need to create a new post. There are a few essential steps you need to take before you get started.

### Prepare Your Local Clone

Check out the [guide for keeping your files up-to-date](https://github.com/18mr/documentation/blob/master/sync-your-fork.md) to learn how. Make sure your _local version_ of the website is up-to-date, not just the repository on your personal GitHub account.

### Place a Featured Image in the Directory

Featured images should __aspect ratio of 4:3__ and they should be added to the directory /static/images/featured.

### Create a New File

Open up your favorite text editor and create a new document. Save it as a .md file in the _posts directory on your hard drive's copy of the website. _posts all have a similar file naming convention: YEAR-MO-DA-unique-slug.md.

### Create Front Matter

YAML Front Matter is how Jekyll knows how to treat the files you add to the website. Every post and page in Jekyll needs Front Matter. Start with triple dashes at the beginning and end of your Front Matter.

    ---
    layout: petition-page
    title: "Edward Blum: We Won't Be Used For Your Racist Agenda"
    permalink: /blockblum/
    category: campaigns
    featured-image: '/static/images/featured/blum.png'
    blurb: "Edward Blum is on a mission to dismantle affirmative action. And he's using AAPIs to do it."
    description: "Despite his best efforts, Asian Americans are refusing to be a part of Blum’s racist, anti-affirmative action agenda. The days of divide and conquer are over!"
    ---
  
A basic description of each piece of metadata follows:

+ 'layout' describes which template we will be using. "petition-page" is the default petition page template.
+ 'title' is the page title that will be displayed in the browser. It should be the same as the petition title you entered in Action Network
+ 'permalink' describes the url for the page. Make it descriptive and unique.
+ 'category' indicates that you are creating a post in the "campaigns" category. This is important for the future, as we make a full transition to Jekyll and multiple categories of posts will be posted to the same site.
+ 'featured-image' should be the relative path to the featured image you added to the /featured/ directory.
+ 'blurb' is the tiny snippet of text that will appear on the index of campaigns at action.18mr.org
+ 'description' is the Facebook Open Graph share text that you would like shared. This should be the same as in the Action Network share settings.

## Step Three: Embed It!

Back in Action Network, you can grab the code to embed the petition as a widget in your new post by clicking "edit" on the petition on the 18MR organizational dashboard. You'll see a sidebar that prompts you to embed the petition, with a mess of code and a button that says "Options+" beneath it. Before you copy and paste that code into your new page, make sure that you have the proper options set up: enter "100%" into the custom width field; "Layout Styles Only"; and "Full Layout," as illustrated below.

![widget-options](https://cloud.githubusercontent.com/assets/2704279/5191533/0595a0b6-74a4-11e4-8821-52f8aa1903e3.PNG)

I'm a big fan of breaking up the code a little so it's easier for humans to read if something goes wrong, usually into four lines like this:

    <link href='https://actionnetwork.org/css/style-embed-whitelabel.css' rel='stylesheet' type='text/css' />
    <script>window.yepnope || document.write('<script src="https://actionnetwork.org/assets/yepnope154-min.js"><\/script>');</script>
    <script src='https://actionnetwork.org/widgets/v2/petition/petition-name?format=js&source=widget&style=full'></script>
    <div id='can-petition-area-petition-name' style='width: 100%'><!-- this div is the target for our HTML insertion --></div>

## Step Four: Commit, Sync, Pull Request

You're all set! [Click here for a reminder on how to commit, sync, and send a pull request](https://github.com/18mr/documentation/blob/master/commit-pullrequest.md).
