The main shortcoming of editing directly in GitHub is that you can't update images directly in the browser. Since we don't need to track changes in images the way we do in text files, this solution will suffice (and keep all our images in one place).

## Basic Method: Open an Issue on GitHub

Go to the repository you're creating or editing a file in, and pick the "Issues" item from the menu on the right.

<img src="https://cloud.githubusercontent.com/assets/2704279/4413674/b7314f6c-4508-11e4-8046-bdc298aac51b.PNG">

<img src="https://cloud.githubusercontent.com/assets/2704279/4413675/b8f55de8-4508-11e4-8f39-3c538cec9a98.PNG">

Here's the "Issues" view, which shows you bugs, suggestions, questions, and other stuff from the team and the community. As you may notice, there is a tag in bright purple in the Documentation repository's issues labeled _images_. These aren't real issues; they're threads to store static content used in these documentation files.

To add new images, click "New Issue." Name your issue something descriptive that will help you identify the issue later. Be sure to tag it as _images_ and then you can just drag-and-drop or use a file selector to find the image you want to upload.

<img src="https://cloud.githubusercontent.com/assets/2704279/4413679/cbb8d96e-4508-11e4-9c59-e770d94e182b.PNG">

Cool! Now you can retrieve the image URL by copying its location on GitHub's user content server.

## Adding Images to an Existing Issue

You can also add images by responding to an existing thread. Use this feature to help keep images organized. Open up an existing issue and drag and drop your images into the text field.

<img src="https://cloud.githubusercontent.com/assets/2704279/4413684/de97d6de-4508-11e4-90e7-b27275cbaa23.PNG">

## Put Your Images in a File

In [Markdown](daringfireball.net/projects/markdown/basics), you can use HTML snippets as long as those snippets are preceded by and followed immediately by a line break. So, drop your images in wherever using img tags: 

<img src="https://cloud.githubusercontent.com/assets/2704279/4413818/8426ed90-450b-11e4-9fda-17af063960aa.PNG">
