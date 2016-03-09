Before you add your new featured campaign, make sure you've [synced up](https://github.com/18mr/documentation/blob/master/sync-your-fork.md). It'll make the push-to-live process smooth and chill.

Now that you're synced, you'll need to create two files: an image and a custom file that Jekyll will read and puke out as an action box.

## Copy the Campaign Image

You probably already have a campaign image -- in the repository on your computer for _action_. An easy way to get a copy in is to literally copy and paste it from _action/static/images/featured_ into _18mr/static/images/campaigns_. Boom. Done.

## Create a Campaign

You'll notice that there are several folders of things in the _18mr_ repo. In addition to the basic Jekyll directories, there are directories for categories of posts on the site, as well as directories for authors, campaigns, and staff.

If you open up the campaigns directory, you'll see a collection of Markdown files much like blog posts. The only difference is, there's no body content.

![campaign file screenshot](https://github.com/18mr/documentation/blob/master/images/campaign.PNG)

As you see, the campaign file is all Front Matter. Here is what you need to include in order for a pretty action box to appear:

1. Title: the display name of the campaign.
2. Thumbnail: the location of the image you just placed in _18mr/static/images/campaigns_.
3. Blurb: the _very short_ description of the campaign that will compel readers to take action.
4. Campaign Link: the direct link of the campaign.

Save this file with a filename in the format YEAR-MONTH-DAY-name-of-campaign.md.

Now you can [commit, sync, and create a pull request](https://github.com/18mr/documentation/blob/master/editing-content.md#step-three-upload-it). Your campaign will be live shortly!
