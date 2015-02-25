So you're an administrator. Congrats. (Mostly this document is for Cayden's reference.)

The actual http://action.18mr.org is now hosted on Amazon Web Services. Here are step-by-step deployment instructions.

## Sync Local Site and Rebuild in Ruby

Check to make sure there are no errors. Worth double-checking by typing

    bundle exec jekyll serve

and checking out http://localhost:4000 before pushing to AWS.

## Push to AWS

Now that you've built the most recent version of the site, type

    s3_website push

Hopefully everything is as it should be. s3_website should recognize where the built site is and update it accordingly.

## Known Issues with s3_website

_On a Windows Machine_

There are problems with Ruby and SSL certs on Windows. If the .jar file is not found, go [to the releases page](https://github.com/laurilehmijoki/s3_website/releases/) and download the relevant .jar file for the release you are using.

[s3_website](https://github.com/laurilehmijoki/s3_website) relies on Java. If Java is out-of-date, sometimes s3_website has a hard time finding it. It's been my experience that the following works:

1. Uninstall the s3_website gem.
2. Update Java.
3. Reinstall the s3_website gem.
4. Make sure the .jar file is right.
