---
layout: post
title:  "Website Workflow"
---

Here is how I have my website setup for me to update it any time I want. I will be going over the process I started off with and what I am currently using to push updates. 



#### Jekyll & Markdown

I discovered Jekyll as a way to generate a static website. I could type all the posts in markdown (or HTML), which made writing pages a breeze. Jekyll handled the heavy-lifting of page generation, while I could write all my pages in Markdown. 


I decided to choose Jekyll since I prefer static websites. I believe that static websites are the way the web was designed to be - no JavaScript, no bloat - just simple static pages that load instantly. HTML and CSS are more than sufficient to create good-looking websites that load up instantly. 


I started hosting the website on a Jekyll Docker (in reality it was Podman) container on my homeserver, which would serve all the files directly on a specified port. With this setup, I would simply put the server behind Caddy, my webserver. While this would work in my local network, it was still not exposed to the rest of the internet. 

To make the website "public", I leveraged my existing VPS on DigitalOcean. I already have a VPS to expose certain services I am running on my homeserver. I use Wireguard as a VPN to link my homserver and my VPS together. With this, I simply reverse-proxied my desired domain to point to the Jekyll server. This works since the container binds to all network interfaces, and I could access it via the Wireguard subnet too. 


While this worked, and all changes I made were instantly reflected, the solution was not satisfactory. I could break something and the whole website would come down. And I could only access the site through sshing into my homeserver and editing files directly from there. To address these shortcomings, Ileveraged the other services I was running on my homeserver - Gitea and Drone CI. 


#### Gitea with Drone CI

Gitea and Drone CI were pretty useful together. There is no need for another individual container. Since the website generates static files, there is no need for a Jekyll container to run and eat up resources. 


Instead, I put all the required files for Jekyll to build the website on a repository on my Gitea instance. This means I can easily make changes to the website with a simple push. However, the repo itself wasn't enough for generating and serving files. 


This is where Drone CI comes in. Drone is a simple CI service that works nicely with Gitea. I setup Drone to build my repo with the Jekyll build commands using a ruby image as the base. This generated and built the website, but how would I get the actual built files from the container in which this build was executed? This is where the Drone plugin for `scp` comes in. With this plugin, I can specify which files to copy from the docker container to the host machine (which is my homeserver). Using this plugin, I copied the static files to my homeserver and used Caddy to serve them. The rest of it is the same as the first part. 

I also set the Gitea repo to mirror the GitHub repo containing the same code, so that other people could view it. Anyone can view the Gitea code too, but GitHub tends to be more accessible. 


#### Gitea Actions

With Gitea Actions being introduced in v19.0, Drone CI can be ditched for Gitea's own runners and CI build system. Gitea actions is great since it uses the same configuration syntax as Github, which a lot of people are familiar with. Currently, Gitea Actions takes care of deploying this website by building and `scp`-ing the files on a push to the main branch.
