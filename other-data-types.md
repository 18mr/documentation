There are some other data types that have yet to be fully fleshed out on 18millionrising.org. Here is a brief introduction.

## Authors

In the _authors directory, you'll find a collection of objects about individuals who write articles. Although this is not currently implemented, it would be incredibly helpful if you created author files for authors you edit.

![example author item](https://github.com/18mr/documentation/blob/master/images/author.PNG)

Author items include, in Front Matter:

1. Name.
2. Photo, if available.
3. One-line bio, written as if it is preceded by _name_.
4. URL of author's website, social media, etc. Only one please.

### Author Photos

Store author photos in the directory _/static/images/authors/_. Images can be any size, but the filename should be the author's first initial and last name.

## Staff

In the _staff directory, you'll find a collection of objects about staff members, including Content Crew members. This is currently nominally implemented as the image grid on the "About" page.

![example staff item](https://github.com/18mr/documentation/blob/master/images/staff.PNG)

Staff items include, in Front Matter:

1. Name
2. Photo.
3. Title.
4. Weight, a numeric value which allows us to float paid staff at the top.

Complete biographical information can be included in the body, but currently does not appear on the website.

### Staff Photos 

Staff photos can be found in the directory _/static/images/staff_. Images are 300px square and file names are first initial and last name.
