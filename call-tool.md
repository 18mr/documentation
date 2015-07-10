The current version of our call tool lives [here](https://github.com/18mr/call-congress).

Deploying this version of the call tool is a multistep process. Being precise with your updates to app files will ensure that nothing shady happens when the updated version is deployed. Take care, and you'll do great!

## Table of Contents

1. [Set Up Your Petition](https://github.com/18mr/documentation/blob/master/call-tool.md#set-up-your-petition)
2. [Set Up Your Thank You Page](https://github.com/18mr/documentation/blob/master/call-tool.md#set-up-your-thank-you-page)
3. [Record Your Audio Files](https://github.com/18mr/documentation/blob/master/call-tool.md#record-your-audio-files)
4. [Set Up Twilio Numbers](https://github.com/18mr/documentation/blob/master/call-tool.md#set-up-twilio-numbers)
5. [Update campaigns.yaml in call-congress](https://github.com/18mr/documentation/blob/master/call-tool.md#update-campaignsyaml-in-call-congress)

## Set Up Your Petition

Set up a petition in Action Network. [Here's the walkthrough](https://github.com/18mr/documentation/blob/master/action-network.md) if you need it.

You will also need to add an extra line of Front Matter to your Jekyll page. It should say: ``call-js: true``.

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
    layout: petition-page
    title: "You're calling Rep. Judy Chu"
    permalink: /chu-call-script/
    facebooktext: 'Your Facebook share text.'
    twittertext: 'Your Twitter share text. %2318MR'
    ---

The Front Matter for ``facebooktext`` and ``twittertext`` will be the default share text for automatically generated share buttons. You'll notice that the hashtag is a random series of characters--that's to help Jekyll generate a functional link for the Twitter share link.

_Pro Tip: use [this cheat sheet](http://www.w3schools.com/tags/ref_urlencode.asp) to properly encode special characters in Twitter text._

Once you've done that, compose your thank you page's body. This should include a word of thanks, number(s) to call if you aren't connected since sometimes ``call-congress`` throws errors that I don't understand (_probably skip this if you're setting up a call tool to call multiple members of Congress_), talking points or a call script, and sharing links for after the user has completed the call.

Check out the way previous [call script pages](https://github.com/18mr/action/blob/gh-pages/chu-callscript/index.md) have been formatted before. Note that the actual call script is enclosed by a ``<div class=featurebox>`` which gives it highlighted styling.

### Update your thank you page in Action Network

In the "Response Options" tab, insert the permanent URL of the thank you page you just made. 

_Pro Tip: that this will throw a 404 error until the live Amazon Web Services version has been updated. Use a [local server emulator](https://github.com/18mr/documentation/blob/master/local-site.md) to test your share links._

## Record Your Audio Files

You can just record audio files on your phone, and email them to yourself. You may wish to listen to example files by calling through an existing campaign in order to get an idea of what each snippet does.

Please name your files uniformly. Filenames should be based on the parameter they are assigned to, which keeps things neat and easy. From the [call-congress README](https://github.com/18mr/call-congress/blob/master/README.md):

* msg_intro: This is the first audio a new caller hears. Introduce yourself and the tool.
* msg_ask_zip: Ask for the user's ZIP code if you are looking it up.
* msg_invalid_zip: An error message about their ZIP code.
* msg_call_block_intro: In this block, introduce the campaign. Read through the script, and then tell the caller that when they're one with their call, they can press * to proceed to the next call (if applicable).
* msg_rep_intro: Notify the caller they're being connected to the next office.
* msg_special_call_intro: Optional: if an extra first call number is specified in the remote Google Spreadsheet, this text can be used to introduce the extra call. It's optional, and if not specified, we'll fall back to _msg_rep_intro_.
* msg_between_thanks: Offer some words of encouragement!
* msg_final_thanks: Thank the caller for their time. Remind them about social media, microsites, or upcoming events.

For example, if you want to record a new introduction, name that file ``msg_intro.mp3``.

Place your files in a new folder in your local clone of action.18mr.org. The filepath should be similar to previous campaigns, such as: ``static/audio/chu-nn``.

Once you've created the campaign page, landing page, and audio files, commit your changes and send a pull request to get all that good stuff into the main branch and out to AWS.

## Set Up Twilio Numbers

For now, get in touch with me to set up Twilio numbers. Make sure you tell me the campaign slug from ``/data/campaigns.yaml`` that you will set up below.

## Update campaigns.yaml in [call-congress](https://github.com/18mr/call-congress)

If you haven't already, create a fork of [call-congress](https://github.com/18mr/call-congress). Once you've cloned it locally, open up the ``/data/campaigns.yaml`` file in your favorite text editor. You'll see that a "default" campaign exists, as well as other live call-in campaigns that are currently running.

You need to create a new item in the yaml file. You may wish just to copy the existing yaml from a previous campaign.

_Pro Tip: yaml is notoriously fickle. Make sure you use spaces instead of tabs and everything is the right number of spaces, otherwise the yaml won't process and your campaign won't work!_

Here are the basic fields in the yaml file:

* **id**: the unique identifying slug for the campaign.
* **number** the phone number(s) you get from Twilio.
* **target_house** (boolean) include members of the House of Representatives
* **target_senate** (boolean) include Senators
* **target_house_first** allows the campaign to target house members before senate members (default: target senate first)
* **only_call_1_sen** (optional, default false) only call one senator
* **only_call_1_rep** (optional, default false) only call one representative
* **repIds** (optional) list of rep. IDs to target
* **randomize_order** (optional, default false) randomize the order of the phone calls
* **skip_star_confirm** (optional, default false) Whether to skip the "press star to confirm" step for campaigns which don't gather zipcode
* **call_human_check** (optional, default false) Whether to check the recipient is not an answering machine. Note, will add a 3 second delay before your call begins.
* **extra_first_calls** (optional) specify non-Congressional targets action-takers will call before any Congressional targets. Name, phone number, and title should be included as a yaml list.
* **extra_last_calls** (optional) specify non-Congressional targets action-takers will call after any Congressional targets. Name, phone number, and title should be included as a yaml list.

You'll also see these field options for audio files. Included are the default values, if you don't add new text for the robot or a custom audio filepath:

* **msg_intro**: Hi. Welcome to call congress.
* **msg_ask_zip**: Please enter your zip code so we can lookup your Congress person.
* **msg_invalid_zip**: "Sorry, that zip code didn't work. Please try again."
* **msg_call_block_intro**: "We'll now connect you to {{n_reps}} representatives. Press # for next rep."
* **msg_rep_intro**: "We're now connecting you to {{name}}"
* **msg_special_call_intro**: Optional: if an extra first call number is specified in the remote Google Spreadsheet, this text can be used to introduce the extra call. It's optional, and if not specified, we'll fall back to _msg_rep_intro_.
* **msg_between_thanks**: You're doing great - here's the next call.
* **msg_final_thanks**: Thank you!

_Pro Tip: custom filepaths should always start with ``http://action.18mr.org/static/audio/your-campaign/``_

### Getting fancy

__Case 1: Targeting Particular Senators__

Let's say you want to target a couple particular Senators to get to vote a particular way on a bill. You can [find their bioguide ID here](http://bioguide.congress.gov/biosearch/biosearch.asp). In ``repIds``, list each ID in a yaml list surrounded by ``[]`` and separated by commas.

When you search the bioguide, you'll have to find the ID in the URL, highlighted below:

![chu](https://cloud.githubusercontent.com/assets/2704279/8621822/908469ce-26dc-11e5-8175-e42bd401f539.PNG)

__Case 2: Targeting Without Members of Congress__

Let's say you're setting up the call tool to call ICE about a deportation or detainer case. You don't need to call any members of Congress right now, but you want the tool to connect users directly to several ICE officials.

A great example of this use case is the Stand With Nan-Hui campaign. You'll notice that ``target_house`` and ``target_senate`` are set to false. ``repIds`` also contains an empty list.

![swnh](https://cloud.githubusercontent.com/assets/2704279/8622533/da46e722-26e0-11e5-8039-44e1b17887c3.PNG)

### Going live

Once you've saved your new campaigns.yaml file, commit the changes to your fork of call-congress and send a pull request.

_Before your campaign is live and testable_, keep in mind that tech has to approve the pull request and deploy the changes to the Heroku server. Sending a pull request is all you need to do; tech will notify you your tool is live and can be tested.
