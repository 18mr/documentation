Exciting! We just upgraded the old call-congress to the shiny, new [CallPower](http://callpower.org). The current version of our call tool lives [here](https://github.com/18mr/call-congress).

Deploying a call campaign is a multistep process. Being precise with your updates to app files will ensure that nothing shady happens when the updated version is deployed. Take care, and you'll do great!

## Table of Contents

4. [Set Up Twilio Numbers](https://github.com/18mr/documentation/blob/master/call-tool.md#set-up-twilio-numbers)
5. [Create a CallPower Campaign](https://github.com/18mr/documentation/blob/master/call-tool.md#create-a-callpower-campaign)
1. [Set Up Your Petition](https://github.com/18mr/documentation/blob/master/call-tool.md#set-up-your-petition)
2. [Set Up Your Thank You Page](https://github.com/18mr/documentation/blob/master/call-tool.md#set-up-your-thank-you-page)

## Set Up Twilio Numbers

For now, get in touch with tech to set up Twilio numbers. Wait until you get confirmation, then you can move on to the next step.

## Create a CallPower Campaign

In case you need it, the complete campaigner documentation for CallPower is [here](https://github.com/18mr/documentation/blob/master/CallPower%20User%20Guide.pdf). This guide explains all the audio cues and options you can set up for any given campaign.

__You can access [the campaigner interface for CallPower here](http://calls.18mr.org).__

### Create Campaign

Create a new campaign and pick your targeting method, or add a custom target.

_Note that if you have state level targets, you may need to target by lat/lon. This feature has not been added yet; please hang tight._

Select the Twilio number or numbers that tech has set up for you.

Check _allow call-in_. This will help users complete calls even if the server fails to respond.

### Record Audio

You can record audio directly into CallPower. Ideally, record using a headset to try and isolate the sound of your voice as best as possible, and record in a quiet room.

Be sure to record _Location Prompt_ asking for callers' ZIP codes, as ZIP codes are not currently being passed to the app. You can also use existing audio to fill in location audio files if you wish.

### Save Your Campaign and Get Data to Embed

Be sure to test your call audio! Call all the way through and ensure all audio is loading correctly and you're being patched through to the correct office.

The current website template will more or less set everything up for you. In order to proceed, make a note of the campaign number and one of the Twilio numbers in order to list the call-in number.

## Set Up Your Petition

Set up a petition in Action Network. [Here's the walkthrough](https://github.com/18mr/documentation/blob/master/action-network.md) if you need it.

You will also need to add two extra lines of [Front Matter](https://github.com/18mr/documentation/blob/master/action-network.md#create-front-matter) to your Jekyll page. They should say: 

    callcampaign: true
    campaignId: SOME_NUMBER

``campaingId`` is the ID number of your CallPower campaign that you just created.

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

The only thing you have to change in the code above is ``#can-petition-area-call-congress-be-a-champion-for-adoptee-citizenship``. It's the ID of the div created by Action Network; you can find the right one for your new petition in the last line of the [code you embed](https://github.com/18mr/documentation/blob/master/action-network.md#step-three-embed-it) when you create an Action Network petition.

## Set Up Your Thank You Page

Unlike a standard petition, where we use the default Action Network share tools, when we run call-in campaigns, we create static pages on http://action.18mr.org to host the call script and share buttons. Before you start, make sure your local version of action.18mr.org is up-to-date.

### Create a new folder

On your local machine, create a new folder in the main directory, ``action``. Name it something descriptive, preferably what you want the slug to be in the URL, like ``chu-callscript``. Create a new file in that folder called ``index.md``. This tells Jekyll to generate a static page (i.e., not a "blog entry").

### Add your content

Your thank you page's [Front Matter](https://github.com/18mr/documentation/blob/master/action-network.md#create-front-matter) is more simple than a petition page's:

    ---
    layout: callscript
    title: "You're calling Rep. Judy Chu"
    permalink: /chu-call-script/
    twittertext: 'Your Twitter share text. %2318MR'
    sharelink: /chu-nn/
    ---

Make sure you change the ``layout`` to ``callscript`` so you get pretty share buttons. The ``sharelink`` is the slug for the petition you're attaching the script page to.

The Front Matter for ``twittertext`` will be the default share text for automatically generated share buttons. You'll notice that the hashtag is a random series of characters--that's to help Jekyll generate a functional link for the Twitter share link.

_Pro Tip: use [this cheat sheet](http://www.w3schools.com/tags/ref_urlencode.asp) to properly encode special characters in Twitter text._

Once you've done that, compose your thank you page's body. This should include a word of thanks, and the number to call if you don't get a call, talking points or a call script, and sharing links for after the user has completed the call.

Check out the way previous [call script pages](https://github.com/18mr/action/blob/gh-pages/chu-callscript/index.md) have been formatted before. Note that the actual call script is enclosed by a ``<div class=featurebox>`` which gives it highlighted styling.

### Update your thank you page in Action Network

In the "Response Options" tab, insert the permanent URL of the thank you page you just made. 

_Pro Tip: that this will throw a 404 error until the live Amazon Web Services version has been updated. Use a [local server emulator](https://github.com/18mr/documentation/blob/master/local-site.md) to test your share links._

You're all set! Submit those pull requests and your campaign will be live shortly.
