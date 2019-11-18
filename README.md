# stormy-stories.surf
a travel, windsurf and livestyle blog

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

### Select your images
If you need some pictures for your blog-post, please go through your pictures select the ones which you you want for your post and copy them into a temporary folder. Go through all of these pictures and review them for the following points:
 - Are there any faces of people that you don't want to publish
 - Are there any plates of cars that you don't want to publish
 - Are there any dirt dots in the picture because of a dirty lense
 - Is there a slate / non horizontal horizon
 - Is the picture to bright or to dark
 - Are there color errors because of a too high light sensitivity / ISO value

 If one or more of these points are matching with one of your pictures you should consider to not use it or to rework it, before using it.

### Add your pictures to the media-base repository
At stormy-stories.surf we have one repository which is storing all original pictures without any compression or watermark but which are already in a reworked publication worthy status. Now as you have selected and reworked your pictures you have to add this pictures to this repository.


### License and watermark
If you want to write a blog post you most likely will need both pictures and text. At stormy-stories.surf we publish all everything with a CC BY-NC-SA license. This means every one is free to copy and redistribute the material in any medium or format and also
adapt — remix, transform, and build upon the material. But this usage is only allowed for non-commercial purpose, if we as the initial authors are mentioned and if the newly created material is also published with the same license.

To ensure that our pictures refer back to us, even if they are used without mentioning us as the creator, we add watermarks to all published pictures.

To not make this an annoying task we developed a command-line tool which can automatically run through all pictures and add a watermark to them. The usage of this tool is explained in a later part of this README.

## Compression and scaling of images
As most of the modern cameras create pictures with sizes > 5MB and also often > 20MB it is important to reduce the file sizes of all images.
