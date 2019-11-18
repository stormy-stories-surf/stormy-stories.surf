# **STORMY-STORIES.SURF**
a travel, windsurf and livestyle blog

![link broken](mediaLibrary/general/Logo.png)

## How to write a blog post

### Create a new ticket / issue at Github
The first thing you should do, before writing a new blogpost is creating a new ticket on github. This ticket is needed to track all changes which are made during the creation of this blogpost.
To create a ticket go to :
```
https://github.com/stormy-stories-surf/stormy-stories.surf/issues/new
```
Here you can add :
 - A **title**, which could be for example "Add blogpost : <NAME_OF_YOUR_BLOG_POST>"
 - An **assignee**, which is the person who is working on this ticket, which is most probably you.
 - A **label**, here you have to select **new blogpost**
 - A **project**, which should be **Write .md files for STORMY-STORIES.SURF**
 - And finally a **milestone**, which should be the milestone of the version in which this blogpost shall be released.

After the ticket is complete you can click on **Submit new issue**.
Your new ticket is created and opened. Besides this your new ticket has a number that is displayed after the title of the ticket with a **#** in front of it. Please remember this number. You will need it in the next steps.

### Select your photos
If you need some photos for your blog-post, please go through your photos select the ones which you you want for your post and copy them into a temporary folder. Go through all of these photos and review them for the following points:
 - Are there any faces of people that you don't want to publish
 - Are there any plates of cars that you don't want to publish
 - Are there any dirt dots in the picture because of a dirty lense
 - Is there a slate / non horizontal horizon
 - Is the picture to bright or to dark
 - Are there color errors because of a too high light sensitivity / ISO value

 If one or more of these points are matching with one of your photos you should consider to not use it or to rework it, before using it.

### Add your photos to the media-base repository
At stormy-stories.surf we have one repository which is storing all original photos without any compression or watermark, but which are already in a reworked publication worthy status. Now as you have selected and reworked your photos you have to add this photos to this repository. For this follow the next steps:

1. Clone the stormy-stories-media-base repository by opening the terminal and typing

  ``` bash
  git clone gitlab@dev.sum7.eu:mezorian/stormy-stories-media-base.git
  ```
  or
  ``` bash
  git clone https://dev.sum7.eu/mezorian/stormy-stories-media-base.git
  ```
2. Go into the new directory
  ``` bash
  cd stormy-stories-media-base
  ```
3. Create a new branch which is based on the development branch. Use the number of your github ticket / issue as the new branch name. For example if your ticket / issue number was #54 name the new branch #54.
  ``` bash
  git checkout development
  git checkout -b <TICKET_NUMBER>
  ```
4. Create a new directory for your blog post. For this please keep up with the already existing directory structure which is as follows:
  ```
  .
  ├── pages
  │   └── ......
  │  
  ├── posts
  │   ├── year
  │   │   ├── countryInEnglish-countryInGerman
  │   │   │   ├── Month-Day-NameOfPostInEnglishAndGerman
  │   │   │   │   ├── XX.JPG
  │   │   │   │   ├── YY.JPG
  │   │   │   │   ├── ZZ.JPG
  │   │   │   ├── Month-Day-NameOfPostInEnglishAndGerman
  │   │   │   │   ├── XX.JPG
  │   │   │   │   ├── YY.JPG
  │   │   │   │   ├── ZZ.JPG
  │   │   │   ├── Month-Day-NameOfPostInEnglishAndGerman
  │   │   │   │   ├── XX.JPG
  │   │   │   │   ├── YY.JPG
  │   │   │   │   ├── ZZ.JPG
  │   ├── year
  │   │   ├── countryInEnglish-countryInGerman
  │   │   │   ├── Month-Day-NameOfPostInEnglishAndGerman
  │   │   │   │   ├── XX.JPG
  │   │   │   │   ├── YY.JPG
  │   │   │   │   ├── ZZ.JPG
  │   │   │   ├── Month-Day-NameOfPostInEnglishAndGerman
  │   │   │   │   ├── XX.JPG
  │   │   │   │   ├── YY.JPG
  │   │   │   │   ├── ZZ.JPG
  │   │   │   ├── Month-Day-NameOfPostInEnglishAndGerman
  │   │   │   │   ├── XX.JPG
  │   │   │   │   ├── YY.JPG
  │   │   │   │   ├── ZZ.JPG

  ```
  For example if your post is about the Brandon Bay Stradbally in Ireland at the 06. November 2017 your directory structure has to look like :
  ```
  .
  ├── posts
  │   ├── 2017
  │   │   ├── ireland-irland
  │   │   │   ├── 11-06-brandon-bay-stradbally
  │   │   │   │   ├── DSC09040.JPG
  │   │   │   │   ├── DSC09042.JPG
  │   │   │   │   ├── DSC09050.JPG

  ```
5. Copy all photos into the directory.
6. Add the new photos to the version control system by opening the terminal in the new directory and typing the following commands. For this please replace #<TICKET_NUMBER> by your github ticket / issue number (for example #54 ) and replace <POST_TITLE> by name of your blog-post.
``` bash
git status
git add -A
git commit -m "#<TICKET_NUMBER> : Added photos for <POST_TITLE>"
git push -u origin #<TICKET_NUMBER>
```
### Merge your ticket branch into the development branch
Now as you added and pushed your new photos to the stormy-stories-media-base repository you can merge your changes from the ticket-branch into the development branch.
For this open
```
https://dev.sum7.eu/mezorian/stormy-stories-media-base/merge_requests/new?merge_request
```
and select your recently created new ticket-branch as source and **"development"** as target branch, after this click **"Compare branches and continue"**.
On the next page scroll to the back and click to **"Submit merge request"**.
On the next page click on **"Merge"**.

### License and watermark
If you want to write a blog post you most likely will need both photos and text. At stormy-stories.surf we publish everything with a CC BY-NC-SA license. This means every one is free to copy and redistribute the material in any medium or format and also
adapt — remix, transform, and build upon the material. But this usage is only allowed for non-commercial purpose, if we as the initial authors are mentioned and if the newly created material is also published with the same license.

To ensure that our photos refer back to us, even if they are used without mentioning us as the creator, we add watermarks to all published photos.

To not make this an annoying task we developed a command-line tool which can automatically run through all photos and add a watermark to them. The usage of this tool is explained in a later part of this README.

### Compression and scaling of photos
As most of the modern cameras create photos with sizes > 5MB and also often > 20MB it is important to reduce the file sizes of all photos. The compression and scaling of the photos can also be done with the command-line tool which is used for watermarking.

### Prepare your photos (watermarking & scaling / compressing)
Before you can use your photos for your new blogpost you have to reduze the file size and add a watermark to them.
For this you can use the command-line tool PhotoPrep as follows:

1. Download it, by opening the terminal and typing

  ``` bash
  git clone git@github.com:stormy-stories-surf/PhotoPrep.git
  ```
  or
  ``` bash
  git clone https://github.com/stormy-stories-surf/PhotoPrep.git
  ```
2. Go into the new directory
  ``` bash
  cd PhotoPrep
  ```
3. Copy all your pictures ......

**TODO anon42**

### Add your prepared photos to the stormy-stories.surf repo
At stormy-stories.surf we have one main repository which stores all blog posts and all photos which are used in the post. The repository consists mainly of two directories:
- markdown
- mediaLibrary

The blog post itself is written in markdown and is stored in the **markdown** directory.
The photos are stored in the **mediaLibrary** directory.

To create a new blogpost. You have to :

1. Download the repository by opening the terminal and typing:
``` bash
git clone git@github.com:stormy-stories-surf/stormy-stories.surf.git
```
or
``` bash
git clone https://github.com/stormy-stories-surf/stormy-stories.surf.git
```
2. Go into the new directory
``` bash
cd stormy-stories-media-base
```
3. Create a new branch which is based on the development branch. Use the number of your github ticket / issue as the new branch name. For example if your ticket / issue number was #54 name the new branch #54.
  ``` bash
  git checkout development
  git checkout -b <TICKET_NUMBER>
  ```
4. Create a new directory for the photos of your post. For this please keep up with the already existing directory structure which is as follows:
  ```
  mediaLibrary
  ├── pages
  │   └── ......
  │  
  ├── posts
  │   ├── year
  │   │   ├── countryInEnglish-countryInGerman
  │   │   │   ├── Month-Day-NameOfPostInEnglishAndGerman
  │   │   │   │   ├── XX.JPG
  │   │   │   │   ├── YY.JPG
  │   │   │   │   ├── ZZ.JPG
  │   │   │   ├── Month-Day-NameOfPostInEnglishAndGerman
  │   │   │   │   ├── XX.JPG
  │   │   │   │   ├── YY.JPG
  │   │   │   │   ├── ZZ.JPG
  │   │   │   ├── Month-Day-NameOfPostInEnglishAndGerman
  │   │   │   │   ├── XX.JPG
  │   │   │   │   ├── YY.JPG
  │   │   │   │   ├── ZZ.JPG
  │   ├── year
  │   │   ├── countryInEnglish-countryInGerman
  │   │   │   ├── Month-Day-NameOfPostInEnglishAndGerman
  │   │   │   │   ├── XX.JPG
  │   │   │   │   ├── YY.JPG
  │   │   │   │   ├── ZZ.JPG
  │   │   │   ├── Month-Day-NameOfPostInEnglishAndGerman
  │   │   │   │   ├── XX.JPG
  │   │   │   │   ├── YY.JPG
  │   │   │   │   ├── ZZ.JPG
  │   │   │   ├── Month-Day-NameOfPostInEnglishAndGerman
  │   │   │   │   ├── XX.JPG
  │   │   │   │   ├── YY.JPG
  │   │   │   │   ├── ZZ.JPG

  ```
  For example if your post is about the Brandon Bay Stradbally in Ireland at the 06. November 2017 your directory structure has to look like :
  ```
  mediaLibrary
  ├── posts
  │   ├── 2017
  │   │   ├── ireland-irland
  │   │   │   ├── 11-06-brandon-bay-stradbally
  │   │   │   │   ├── DSC09040.JPG
  │   │   │   │   ├── DSC09042.JPG
  │   │   │   │   ├── DSC09050.JPG

  ```
5. Copy all prepared photos into the new directory.
6. Add the new photos to the version control system by opening the terminal in the new directory and typing the following commands. For this please replace #<TICKET_NUMBER> by your github ticket / issue number (for example #54 ) and replace <POST_TITLE> by name of your blog-post.
``` bash
git status
git add -A
git commit -m "#<TICKET_NUMBER> : Added photos for <POST_TITLE>"
git push -u origin #<TICKET_NUMBER>
```
