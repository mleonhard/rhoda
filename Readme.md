# Rhoda File Format
Rhoda is a file format for bundling a Markdown file and its embedded media files.

## Motivation
We need a way to save files for reading on computers and mobile devices.

Existing options have problems:
- Save a link to a webpage:
  - The webpage will likely disappear within 5 years.
  - Viewing the page requires a network connection.
  - Many web pages consume a lot of resources when viewing: data transfer, CPU, memory, and battery power.
  - Most web pages embed trackers to record your interest in the page.
  - Many web pages play unwanted audio, video, or animations.
- Save the webpage HTML file:
  - The same problems of a link to a webpage.
  - The file will probably display incorrectly or not at all due to being unable to load external resources due to security policies.
  - The file will stop working when external resources change.
  - Scripts in the HTML file could steal data from the user's computer.
- Save the webpage HTML file and all its dependencies:
  - The directory will contain many files and consume a lot of disk space.
  - Scripts in the HTML file could steal data from the user's computer.
  - The HTML file still probably depends on external servers and will break in some way.
  - Scripts in the HTML file could steal data from the user's computer.
  - Many web pages consume a lot of resources when viewing: data transfer, CPU, memory, and battery power.
  - Most web pages embed trackers to record your interest in the page.
  - Many web pages play unwanted audio, video, or animations.
  - Some resources will not get saved and will require a network connection to display.
- Save a PDF:
  - Unreadable on a phone because the text is too small.
  - Page formatting is usually screwed up.  For example, there will be unnecessary line breaks and white space.
  - Videos and audio are lost.
  - The resulting file contains images from ads and lists of "related articles".  These images make the PDF file large.
  - The file may contain unnecessary page breaks.
  - Sometimes content overflows the edge of the page and is lost.
  - Many of these problems are solved by using the browser's Reader Mode before saving the PDF.
    Unfortunately, many news websites are designed to be unusable in Reader Mode.
- Copy the webpage into a Google Doc, Microsoft Word Online doc, Zoho Writer doc:
    - Page formatting is usually screwed up, making the page unreadable on a phone.
    - Viewing the page requires a network connection
    - Viewing the page requires maintaining an account with the software maker.
    - The software maker records your interest in the page.
    - Videos and audio are lost.
    - The resulting file contains images from ads and lists of "related articles".  These images consume storage.
- Copy the webpage into a Microsoft Word file, Rich Text file, OpenOffice file, Apple Pages file:
    - Page formatting is usually screwed up, making the page unreadable on a phone.
    - Viewing the page requires special software on the phone.
    - Videos and audio are lost.
    - The resulting file contains images from ads and lists of "related articles".  These images make the file large.

How did we get here?
- Publishers don't want users saving their content.  They want users to come back and look at more ads.
- Publishers sell user tracking data, so they make sure their pages only work when tracking works.
- Leading tech companies want to users to use online software which they pay for with money or ad views.
- Browser makers Google & Microsoft make web tech more and more complicated because it stifles competition.
- Google has massive influence over web standards and has ignored the offline viewing use-case because it reduces
  their ad revenue.

How can we get back control?
- Save content into a new file format that works just as well on phones & computers, offline,
  and doesn't support trackers.
- Make a web browser or browser plugin for converting web pages into Rhoda files.
- Work together to build and maintain de-formatters for converting pages on popular websites into Rhoda files.

## Rhoda File Format
- Markdown file first.  Maybe compressed with DEFLATE or brotli.
- Media files appearing afterward, in same order as in markdown file.  With filenames.  Uncompressed.


## Deformatters
