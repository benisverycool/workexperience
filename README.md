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

`sudo yum install ansible`

It didn't work! Why not? Let's discuss why, and solve the problem.

## Clone this Repository

## Create a Branch

## Run Ansible to Configure the Server

## Make Some Changes

## Commit the Changes

## Push the Changes to the Repository





