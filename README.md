# workexperience

DevOps Work Experience Repository for AGS

## What Are We Going to Do, Then?

We're going to configure a web server to display a web page that will display some information about the server.
We're also going to do a 5 minute presentation and demo at the end of the week, so be sure to take notes.

We will make changes to the server with code that automates the configuration.
Why do we store the configuration in code? Why do we automate? Ask!

## Prerequisites

1. Make sure you've joined the slack channel, and sent a message to say hello.
2. Create your free Github account, and post your Github username in Slack

## Getting Started

The first thing to do is to connect to your instance - that's the server you'll be configuring. To make things simpler, you'll be accessing it via the Amazon Web Services(AWS) Console.

1. Log into AWS using your username and password. Ask for the URL in Slack
2. Click "Services" at the top right, type "Systems Manager" in the search box, then click the result that reads "Systems Manager"
3. On the left menu, click "Session Manager"
4. Click on the "Start Session" button
5. Ask in Slack for your instance ID

** Remember **

To switch to the ec2-user account:

`sudo su ec2-user`

To go to your home directory:

`cd `

To go up a directory:

`cd ..`

To create a directory:

`mkdir directory_name`



Once you are connected to your instance, we'll do the following:

## Install Git

We need a program that will let us manage our code. We're going to use Git. For an overview of what Git is/does, watch these two videos:

https://git-scm.com/video/what-is-version-control

https://git-scm.com/video/what-is-git

Don't forget you can ask questions at any point!

Now we can install git with the command:

`sudo yum install git`

Ask what this command does before running it - never run a command without knowing what it does, and never copy/paste a command directly off the Internet - better safe than sorry ;)

## Configure Git

Now we need to set up some basic user information so Git knows who we are.



## Install Ansible

Ansible is a tool that lets us automate the configuration of servers and infrastructure. We'll be using it only for servers in this case. 

For an overview of what Ansible is/does, watch:
https://www.ansible.com/resources/videos/quick-start-video

Now we can install ansible with the command:

`sudo pip install ansible`

** Remember **

You need to set your $PATH environment variable correctly to run ansible. You can do this temporarily with:

`export PATH=$PATH:/usr/local/bin`

A better way is to do this permanently by editing your bash profile file:

`vi ~/.bash_profile`

and adding this line to the bottom of the file:

`export PATH=$PATH:/usr/local/bin`

if you edit your bash profile, you then need to run the following command to update your environment variables:

`source ~/.bash_profile`



## Clone this Repository

First, make sure the public and private key you saved is on the server. You should have `id_rsa` and `id_rsa.pub` in `/home/ec2-user/.ssh`

You can check this by using `ls` to list the directory contents, e.g.:

`ls /home/ec2-user/.ssh`

or

`ls ~/.ssh`

or

`cd /home/ec2-user/.ssh`

`ls`

You also configured the git user and email with:

`git config --global user.name "YOUR_NAME"`

`git config --global user.email "YOUR_EMAIL"`


To clone this repository, you did the following:

`cd` (To change to your home directory)

`mkdir src` (To make a new directory)

`cd src` (To change to the new directory)

`git clone git@github.com:DanRoeSparks/workexperience.git`

You then changed to the root of the project code with:

`cd workexperience`

## Create a Branch

You've already created a branch, and here's how you did it:

`git checkout -b YOUR_BRANCH_NAME`

If you clone a project that already has your branch (e.g. you're on a new server and want to put your code on it) you can clone the project as normal and then check out that branch - you don't need to create it with the `-b` option:

`git checkout YOUR_EXISTING_BRANCH_NAME`

## Git Tips

Check the status of your code often:

`git status`

This will tell you what code has changed, what branch you are on, and whether you have added, commited, or pushed.

To add your changes:

`git add .` (Run this from the root of the project - in the workexperience directory - to add all your changes)

`git add path/to/a/specific/file.txt` (to only add a specific file)

To commit your changes:

`git commit -m "Your commit message"`

To push your code to the remote repository (e.g. Github in this case):

`git push`


## Run Ansible to Configure the Server

To run the ansible playbook, you used the following command from the root of the project:

`ansible-playbook server.yml`

To get more verbose output, you can add the `-v` option:

`ansible-playbook server.yml -v`

More `v`'s gives you more information, e.g.:

`ansible-playbook server.yml -vvv`

Experiment with the different levels of output different numbers of `v`'s gives you.


## Make Some Changes

Yesterday you used the ansible template module to copy a template (`index.html.j2`) to the correct location for the index page of your webserver.

Today, try to add more pages.

You can get some basic info on HTML from http://www.simplehtmlguide.com/

Start with these pages for some ideas:

http://www.simplehtmlguide.com/essential.php

http://www.simplehtmlguide.com/basics.php

For example, you could make an `about.html` page. You could link to it from the index page with something like:

`<a href="about.html">about</a>`

Here's some things to maybe try:

* Can you set up your site so it has the same links at the top of each page, like a navigation menu?
* Can you think of a way you might do that without having to enter the same list of links on every template?  
* Can you create a set of pages that don't have links to the current page, only the other pages? e.g. the index.html page only links to the about.html and news.html pages, the about.html page only links to the index.html and news.html pages, and the news.html page only links to the index.html and about.html page?

Here's some things to think about for the next work:

* What other things could you add to the site?
* What things might change about the server over time that you might be able to display?
* What things might stay the same about the server that you might be able to display? 
* Do you think you know what you need to do to set up a new server if this one stopped working?
* What else could we automate to make it even easier?

Have a look at the different modules in ansible: https://docs.ansible.com/ansible/latest/modules/modules_by_category.html
Especially look at these:
* Files modules: https://docs.ansible.com/ansible/latest/modules/list_of_files_modules.html
* Commands modules: https://docs.ansible.com/ansible/latest/modules/list_of_commands_modules.html
An example: You might get the system time and date by running the command `date` and then adding that to one of your pages.

Have a look at the built-in ansible plugins: https://docs.ansible.com/ansible/latest/plugins/plugins.html
Would any of these be useful/fun?
Some examples:
* https://docs.ansible.com/ansible/latest/plugins/lookup/url.html - this gets the content from a URL - e.g. you could get the content from https://thesimpsonsquoteapi.glitch.me/quotes and then display that somehow.
* https://docs.ansible.com/ansible/latest/plugins/lookup/env.html - this reads environment variables - like the $PATH var we set to run ansible. 




