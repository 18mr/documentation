The current version of our call tool lives [here](https://github.com/18mr/call-congress).

Deploying this version of the call tool is a multistep process. Being precise with your updates to app files will ensure that nothing shady happens when the updated version is deployed. Take care, and you'll do great!

## Set Up Your Petition

Set up a petition in Action Network. [Here's the walkthrough](https://github.com/18mr/documentation/blob/master/action-network.md) if you need it.

In addition to embedding the petition widget from Action Network, you will need to add some bits of code to override the default Action Network text (so the submit button says "Call Now!" instead of "Add Your Name" and the like).

    <script>
	      $(document).ready(function() {
		    $('#can-petition-area-call-congress-be-a-champion-for-adoptee-citizenship').on('can_embed_loaded', function() {
		        document.getElementsByName("commit")[0].value = "Call Now";
		  	    $(".action_sidebar h4").text("Take Action");
		  	    var str = document.getElementsByClassName("action_status_running_total")[0].innerHTML;
		  	    var txt = str.replace("Signatures Collected", "Calls Completed");
			      document.getElementsByClassName("action_status_running_total")[0].innerHTML = txt;
		      });
	      });
    </script>

The ``#can-petition-area-call-congress-be-a-champion-for-adoptee-citizenship`` is the ID of the div created by Action Network; you can find the right one for your new petition in the last line of the code you embed when you create an Action Network petition.

## Set Up Your Thank You Page

Unlike a standard petition, where we use the default Action Network share tools, when we run call-in campaigns, we create static pages on http://action.18mr.org to host the call script and share buttons. Before you start, make sure your local version of action.18mr.org is up-to-date.

### Create a new folder

On your local machine, reate a new folder. Name it what you want the slug to be in the URL, like ``chu-callscript``. Create a new file in that folder called ``index.md``.

### Add your content

Your thank you page's [front matter](https://github.com/18mr/documentation/blob/master/action-network.md#create-front-matter) is more simple than a petition page's:

    ---
    layout: petition-page
    title: "You're calling Rep. Judy Chu"
    permalink: /chu-call-script/
    facebooktext: 'Your Facebook share text.'
    twittertext: 'Your Twitter share text. %2318MR'
    ---

The front matter for facebooktext and twittertext will be the default share text for automatically generated share buttons. You'll notice that the hashtag is a random series of characters--that's to help Jekyll generate a functional link for the Twitter share link.

_Pro Tip: use [this cheat sheet](http://www.w3schools.com/tags/ref_urlencode.asp) to properly encode special characters in Twitter text._

Once you've done that, compose your thank you page's body. This should include a word of thanks, number(s) to call if you aren't connected (_probably skip this if you're setting up a call tool to call multiple members of Congress_), talking points or a call script, and sharing links for after the user has completed the call.

Check out the way previous [call script pages](https://github.com/18mr/action/blob/gh-pages/chu-callscript/index.md) have been formatted before. Note that the actual call script is enclosed by a ``<div class=featurebox>`` which gives it highlighted styling.

### Update your thank you page in Action Network

In the "Response Options" tab, insert the permanent url of the thank you page you just made. 

_Remember that this will throw a 404 error until the live Amazon Web Services version has been updated by Cayden._

## Record Your Audio Files

You can just record audio files on your phone, and email them to yourself. You will want to

Place your files in a new folder in your local clone of action.18mr.org. The filepath should be similar to previous campaigns, such as: ``static/audio/chu-nn``.

Once you've created the campaign page, landing page, and audio files, commit your changes and se

## Set Up Twilio Numbers

For now, get in touch with Cayden to set up Twilio numbers. Make sure you tell them the campaign slug from ``/data/campaigns.yaml`` that you will set up below.

## Update campaigns.yaml in [call-congress](https://github.com/18mr/call-congress)

If you haven't already, create a fork of [call-congress](https://github.com/18mr/call-congress). Once you've cloned it locally, open up the ``/data/campaigns.yaml`` file in your favorite text editor. You'll see that a "default" campaign exists, as well as other live call-in campaigns that are currently running.

