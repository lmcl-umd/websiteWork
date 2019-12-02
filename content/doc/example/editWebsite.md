---
title: LMCL Website Overview
linktitle: Website
toc: true
type: docs
date: "2019-05-05T00:00:00+01:00"
draft: false
menu:
  example:
    parent:
    weight: 1

# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 1
---

### System Design:

The LMCL website is built using a [Hugo](https://gohugo.io/about/what-is-hugo/) website framework and hosted on [Github Pages](https://pages.github.com). We implemented the Hugo [Academic](https://sourcethemes.com/academic/docs/) theme. The Academic theme uses a series of templates called "widgets" that can copied and edited as needed to build the site.

Our website is available at: http://lmcl-umd.github.io. 

### System Requirements:

In order to edit and update the website, you must have the following installed on your machine:

<li>[Homebrew](https://brew.sh)</li>

<li>[Hugo](https://gohugo.io/getting-started/installing/)</li>

<li>[Git](https://help.github.com/en/github/getting-started-with-github/set-up-git)</li>

### Github Repositories:

The code for our website is hosted on Github. The username for our lab's GitHub is <b>lmcl-umd</b>. Contact Dr. Slevc for the password if/when needed for SSH authentication (see "Editing the Website" below). There are two repositories in which the code lives:
<li> websiteWork</li>
<li> lmcl-umd.github.io.</li>

The <b>websiteWork</b> repository is where the working code lives while the <b>lmcl-umd.github.io.</b> repository is where the live code lives. 

<b> Note: You will only ever have to change code in websiteWork and that will automatically update the live code in the lmcl-umd.github.io. repository. </b>

### Editing/Updating the Website:

In order to edit the website, you must clone the websiteWork repository from git onto your local machine. When you clone the websiteWork repository, the "public" folder from the code will also be copied onto your machine. This folder, in layman's terms, manages the updates to the site repository. In order to set this automatic updating up, you must run the following code snippets:

```python
#completely remove the current public directory
rm -rf public

#creates a git submodule: builds your site to public where the created public directory will have a different remote origin (i.e. hosted GitHub repository)
git submodule add -b master git@github.com:lmcl-umd/lmcl-umd.github.io.git public

#runs the first build of public
hugo
```

After the website files are locally on your machine and your public directory is set up, you can make changes that will be visible both locally and on the master site. Before you push them back up to the websiteWork repository, run the following code snippet:

```python
./deploy.sh "Your commit message"
```

This deploy command will push your edits to the lmcl-umd.github.io. repository and after a couple of minutes, your changes will appear on the live website. 

In order to clone and push edits via git, you must first have git set up on your computer and [authenticate our lmcl-umd GitHub](https://help.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account) account via your computer's unique SSH key. 

### Helpful Git Commands:

```python
# clone the repository
git clone https://github.com/lmcl-umd/websiteWork.git

# deploy edits to lmcl-umd.github.io. repository
# your commit message should describe the edits made 
./deploy.sh "your commit message"

# add edits to websiteWork repository
git add *

# commit edits to websiteWork repository
# your commit message should describe the edits made 
git commit -m "your commit message"

# push edits to websiteWork repository
git push 

```

### Multiple Git Users:

If there are multiple users updating the website from multiple devices, the websiteWork repository on your local machine may be out of date from time to time. To ensure that you always have the most up to date version of the website code, you must "pull" it down from the repository <b>before</b> you make any changes yourself. 

```python
git pull
```

Read the output of this code carefully. If the word "error" or "aborting" is present after you try to pull the websiteWork repository, something went wrong. The most likely problem is that there are some untracked files between the two versions of code (the version in the repository and the version on your local machine) and git is unable to merge them. To resolve this issue, run the following two code snippets:

```python
git fetch --all
git reset --hard origin/master
```
Now, you should be able to run the pull command again and successfully get an updated version of the code.

```python
git pull
```

At this point, you can make your own changes to any of the websiteWork files and deploy, git add, git commit, and git push as you normally would. 


### Code Organization:

After you clone the websiteWork repository, you will see a folder called "websiteWork" on your computer. Within that folder are many, many subdirectories. The main folders most relevant for editing, however, are:

<li><b>content:</b> holds all the actual editable content on the site; subdirectories within this folder are named to indicate which sections of the site they house information on</li>
<li><b>config:</b> holds the more administrative, website configuration files</li>
<li><b>static:</b> holds images and other files such as publication odds or profile cv's for reference by other folders</li>
<li><b>layouts:</b> the main back-end of the website that holds all style sheets, and design of the site</li>

<b> Do NOT ever edit the public folder in this repository</b> It handles the automatic deployment to the main website and should not be edited. 

For more information on [managing](https://sourcethemes.com/academic/docs/managing-content/) and [writing](https://sourcethemes.com/academic/docs/writing-markdown-latex/) content see the Hugo Academic [source documentation](https://sourcethemes.com/academic/docs/).


### Make Edits without Deploying

What if you want to just play around and see how something will look before actually deploying to the website?

We also have a version of the website's code (and example code) on DropBox. This code is not live and can be run locally. Enter the <b>lmclSite</b> folder via the terminal and then type the command
```python
hugo server
```
Next open a web-browser and type
```python
localhost:1313
```
The code will render in the browser. 


For access to the DropBox code, contact Dr. Slevc and you will be granted access for editing. 


