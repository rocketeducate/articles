
---
title: "Host your React/Vue Projects with Continuous Deployment, for Free!"
published: false
description: "Build and host your React and Vue projects from GitHub for free, with GitHub Actions for continuous deployment included."
tags: "react, vue, github"
canonical_url:
cover_image:
series:
---

## Host your React/Vue Projects with Continuous Deployment, for Free!

### Introduction

Have you ever built web applications that you’d love to show off online, but didn’t want to pay money to host them? 

Do you have a blog, splash page or series of portfolio showcase projects, but don’t want to spend hours configuring and deploying it? 

Here’s the solution.

I’ve created a collection of template repositories on GitHub that makes hosting and continuously deploying React and Vue projects *free* and *incredibly simple*. 

In addition to the built-in deployment through GitHub Actions, it’s super easy to plug in a custom domain, with installation instructions including all of the required A and CNAME host records for your domain provider.

You can view the repositories here:

- Vue: https://github.com/LloydTao/vue-template.github.io
- Nuxt: https://github.com/LloydTao/nuxt-template.github.io
- React: https://github.com/LloydTao/react-template.github.io

Each of these is hosted separately, for free:

- Vue: https://vue.lloyd.cx/
- Nuxt: https://nuxt.lloyd.cx/
- React: https://react.lloyd.cx/

### How it Works

We’ll be taking advantage of GitHub Pages in order to host our sites.

Pages is a feature of GitHub that can serve static web files for a repository, typically for docs or a wiki. 

**We’ll** be using it to automatically serve a compiled React/Vue project. 

I should note here that this won’t host a dynamic web app that would otherwise rely on a Node server. You’ll need a proper web server for that.

### Getting started

It can be set up in minutes, and has a few nice features out-of-the-box:

- The repository contains a GitHub Actions workflow to automatically build and deploy any pushed changes. No messing around with external pipelines (i.e. Travis CI), and a private repo can still get ~2000 deployments per month. 

- The repository contains a CNAME file, along with easy instructions for pointing your domain to the site using your provider’s DNS host records.

- The README also contains instructions for launching *unlimited* static sites, each to its own subdomain. You can now publish a blog, or separate out your portfolio’s projects into repos under the same domain, all for free. 

All instructions are in the repository’s README, but let’s get started below!

Usage
Get started in minutes with these instructions:
1. Create a repository from this template (include all branches).
2. Rename your repository to <username>.github.io.
3. Make sure that GitHub Pages uses the build branch.
The branch can be selected at Settings -> Options -> GitHub Pages -> Source.
This may take a minute or two to update.

Architecture
This is real simple:
* The master branch contains a React/Vue project.
* The build branch will contain the compiled React/Vue application.
* When you push to master, a GitHub Action compiles the updated project into build.

Development
Any commits pushed or merged into master will trigger the build action.
These changes will be reflected on your GitHub Pages site after around 60 seconds.

Domain Names
Apex Domain
First, set your domain name within the GitHub repository.
* In the CNAME file, replace example.com with your domain.
Second, configure your DNS host records with your domain provider.
* Create an A record for host "@" pointing to 185.199.108.153.
* Create an A record for host "@" pointing to 185.199.109.153.
* Create an A record for host "@" pointing to 185.199.110.153.
* Create an A record for host "@" pointing to 185.199.111.153.
Subdomains
You can configure a subdomain, such as www.[example.com], in your DNS host records.
* Create a CNAME record for host "www" pointing to <username>.github.io.

Infinite Hosting
Want to know what makes this awesome? You can have a repository for each and every subdomain.
1. Create a repository from this template with any name (include all branches).
2. Enable GitHub Pages for it (Settings -> Options -> GitHub Pages -> Source).
3. In the CNAME file, replace example.com with your apex and subdomain (i.e. blog.[example.com]).
4. With your domain provider, create a CNAME record for host "[blog]" pointing to <username>.github.io.