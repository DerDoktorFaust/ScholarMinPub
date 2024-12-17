# ScholarMinPub

ScholarMinPub is a minimalist computing platform for scholars and students to digitally publish to the world their research. It has no monetary costs as it is entirely based on the free platform GitHub. The computing requirements are very low: an internet-connected device (almost any computer of any age will work, along with most tablets and smartphones). The digital literacy requirements are also very low and the author needs only the information contained down below to get set up and running. ScholarMinPub supports the needs of online digital humanities projects through providing an easy-to-use platform with no-coding (just MarkDown!) to publish text, images, and videos with an eye to aesthetic design and the proliferation of knowledge globally.

## Origins of ScholarMinPub

ScholarMinPub is developed by Christopher Thomas Goodwin, a historian of Germany and a digital historian, at the University of Florida. ScholarMinPub is a fork of the documentary publishing platform MinDoc, which was created by Christopher Thomas Goodwin, Caroline Kness at the University of Illinois at Urbana-Champaign, John Randolph at the University of Illinois at Urbana-Champaign, and Liza Senatrova.

# User Guide

## Establish a Repository with Your Copy of ScholarMinPub In It

The first thing you’ll need to do—to build your website—is to create a copy of our ScholarMinPub template that you can alter to suit your needs and put into something GitHub calls ‘a repository.’ A repository is just a collection of files within a larger project (in this case ScholarMinPub). So in this step you will create a clone copy of the ScholarMinPub files, within a repository you will name as your own.  To create the site, you’ll then be revising these files to reflect your content (adding all the elements of your edition: digital sources, your commentary, footnotes, etc.) You will revise these files to make your website.  To create your Repository, with your new copy of the ScholarMinPub template in it:

- ***Sign in to GitHub*** - If you don’t already have an account, create one. Go to [GitHub](https://github.com) and select “sign up” at the top right corner.
- ***Go to the ScholarMinPub Repository*** - This is where you will find all the ScholarMinPub files: [ScholarMinPub GitHub Repository](https://github.com/DerDoktorFaust/ScholarMinPub).
- ***Create Your Own Repository*** - Click on the big green button on the top right of the screen ("Use this Template") It will provide you with two options. Choose ”Create a New Repository.”
- ***Choose a Name for your Brand New ScholarMinPub Project*** - Remember this name
- ***Set the Preferences*** - The default setting is public repository. Do not change this, as you can only deploy a website if the repository is public.
- ***Click Create Repository***

## Initial Testing of Your Site

So your new copy of ScholarMinPub already can be converted into a website, using GitHub’s tools. It’s just a blank website (for now), since you haven’t added any content. Still, it makes sense to make sure you can deploy your site before you put more work into it. Here’s how.

- ***Go to the Settings Tab and Choose ‘Pages’*** - It’s in the top left bar.
- ***Set the Site to Deploy from Main Branch*** - Click on the Save button. The "branch” refers to your unique version of the ScholarMinPub repository. The main branch is considered the most simple, stable, and deployable branch. By selecting the main branch, all your edits will be merged and displayed on your website.
- ***Reload the Page*** - The link to your website will appear at the top of the same page.  This may take several minutes, so don’t worry if your link isn’t immediately generated.
- ***Copy and Store Your New URL So You Have It Handy*** - Copy the link, then click on the ‘Code’ page (top left).  Find the ‘About’ section (on the right). Click on the Settings button, which is just to the right of “About” and looks like a gear. Then paste the URL (the website’s address) in the “Website” line to always have it at hand.  
- ***Set Your Site baseurl***
    - Set your Config.yml File - You can find the “config.yml” folder under the “Code” button at the top left hand of the screen. The “config.yml” folder is near the bottom of the page.
    - Replace the content of the line "baseurl" in the config.yml folder with the name of your repository, which is the name you selected when you initially created your own repository.  Be sure to copy the name exactly (e.g., 'baseurl: "/ScholarMinPub"' --> 'baseurl: "TheNameYouChoseAbove"'). _Note: these single and double quotation marks are required._
    - Change the title of your project
    - Add your authors' names
- ***Click on the Link You Created in the Step Above*** - Your website should now load.

> [!WARNING] 
> If you do not have experience working with GitHub, Jekyll, and web design, do not move files around in your directory structure. Do not alter ANY existing files except the _one_ time you change _config.yml and the numbered files where you put your content (i.e. files beginning with 001... 007).

## Adding Content

### Adding Text

To add text content:
- Click on one of the text files (001... 007)
- Click on the little pencil symbol in the top left
- On the page that opens, add your text
- Press the green button at the top that says "Commit Changes..."

Leave base titles alone that have the ```# Title``` headings. To add second-level titles, use ```## Second-Level Title```.

Also, do not change any text at the top of each file, everything that is between the ``` --- ``` symbols.

### Adding Links

To add a link, use the following code: ``` [text to describe the link or the website's name](url to the site) ```

### Adding Images

#### Uploading an Image to Your Site

To add an image you found on the internet, you first need to download the image to your computer. Then you need to add the image to your site:
- Navigate to the following directory: /media_files/images
- Click "Add File" at the top of the page
- Click "Upload Files"
- Drag and drop your downloaded file
- Press the green button "Commit Changes"

#### Create the Image Description File

- Navigate to the directory ```/media_files/_media_metadata```
- Press the Add File button at the top left
- Select "Create New File"
- Name your file a descriptive name that makes sense based on the image and ensure you end this name with ```.md```. For the example below, this would be: ```emperornapoleonimage.md```.

Copy and paste the following:


```
--- 
name: EmperorNapoleon
media_type: image

_title: Napoleon ler en costume du Sacre
description: Napoleon as the Emperor of France
creator: Francois Gerard
_date: 1805
source: Wikipedia

_path: /media_files/images/emperornapoleon.jpg 
layout: media_description
--- 
```


Change the information above to match your new image. Remember the "name" you give it above. 

> [!WARNING] 
> This name should not contain special characters such as a colon or spaces between words. There should not be a colon anywhere in these files except where they already appear (for example, _title:, name:, etc.).


#### Add the Image to One of your Pages

Copy and paste the following to where you want the image to appear in your text file:

```
{% assign media = site.media_metadata | where_exp: "item", "item.name == 'PrussianInfantryHohenfriedberg'" %}
{% include media.html pages=media %}
```

Now, change PrussianInfantryHohenfriedberg to the "name" you gave your image in the step above.

### Adding Video Files

#### Find Your Video and Get its URL

- Find a video on YouTube that you want to add.
- Click the Share button below the video
- Select "Embed"
- Copy the URL that appears in front of "src" but make sure not to include the quotation marks. (do not just press the Copy button that YouTube shows you--highlight the URL and copy it like it was regular text)

Example:

After following the steps above, YouTube gives you the following code:

```
<iframe width="560" height="315" src="https://www.youtube.com/embed/PizUbOsjYm0?si=SukZvyQDpYvHldiR" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```


Copy only the following:

https://www.youtube.com/embed/PizUbOsjYm0?si=SukZvyQDpYvHldiR


#### Create Your Video Description File

- Navigate to the directory /media_files/_media_metadata
- Press the Add File button at the top left
- Select "Create New File"
- Name your file a descriptive name that makes sense based on the image and ensure you end this name with ```.md```. For the example below, this would be: ```riseofprussiavideo.md```.

Copy and paste the following:

```
---

name: RiseOfPrussia
media_type: video

_title: Ten Minute History - Frederick the Great and the Rise of Prussia
description: Short video explaining the rise of Prussia
creator: History Matters
_date: 2019
source: YouTube

_path: https://www.youtube.com/embed/wzYfkezHp3k?si=qcH-0UDQp8mtTa8j
layout: media_description

---
```


Change the information above to match your new video. Remember the "name" you give it above. 

> [!WARNING] 
> This name should not contain special characters such as a colon or spaces between words. There should not be a colon anywhere in these files except where they already appear (for example, _title:, name:, etc.).

#### Add the Video to One of your Pages

Copy and paste the following to where you want the video to appear in your text file:

```
{% assign media = site.media_metadata | where_exp: "item", "item.name == 'RiseOfPrussia'" %}
{% include media.html pages=media %}
```

Now, change RiseOfPrussia to the "name" you gave your video in the step above.

### Adding a TimelineJS Timeline

- Create your timeline using TimelineJS
- In step 4 of the process, copy everything under the Embed heading (starting with <iframe... )
- Paste this where you want it to display on your site.

After  ```<iframe``` add the following: ```class='timeline-iframe'```.

Your final code should look exactly like this (except the "src" URL will be different):

```
<iframe class='timeline-iframe' src='https://cdn.knightlab.com/libs/timeline3/latest/embed/index.html?source=12ZNkEbnN4RnsWLrW2Ekpz2cQV_2QA-3WgJTP4WUKduk&font=Default&lang=en&initial_zoom=2&height=650' width='100%' height='650' webkitallowfullscreen mozallowfullscreen allowfullscreen frameborder='0'></iframe>
```

### Changing the Title Page Background Image

- Find a suitable replacement on the internet
- - Convert the new image to .jpg (jpeg) if it is not already in that format
- Go to ```media_files/images``` and rename mainpageimage.jpg to mainpageimage2.jpg (so that you will not lose the image if anything goes awry)
- Upload your new file to that same directory
- Rename your new file ```mainpageimage.jpg```

_Note: Advanced users can go into the file ```home.html``` and change the background image to a filename of their choice. This is particularly useful if the new background image is not in .jpg format and conversion is not desirable.