---
title: "Host React/Vue with Continuous Deployment, for Free!"
published: true
description: "Build and host your React and Vue projects from GitHub for free, with GitHub Actions for continuous deployment included."
tags: "react, vue, github"
canonical_url:
cover_image: https://dev-to-uploads.s3.amazonaws.com/i/bpsmg1uccir9azio11sd.png
series:
---

### Introduction

Have you ever built web applications that you’d love to show off online, but don’t want to spend hours configuring and deploying it? 

Do you have a blog, splash page or series of portfolio showcase projects, but don’t want to pay money to host them for display?

This guide will show you fully-featured web projects, for free!

![Example React/Vue Project for Portfolio](https://dev-to-uploads.s3.amazonaws.com/i/au93h70az8wqr2c3t1u7.png)

**Here’s the solution.**

I’ve created a collection of template repositories on GitHub that makes hosting and continuously deploying React and Vue projects *free*, *automatic* and *incredibly simple*. 

Additionally, it’s super easy to plug in a custom domain, and I've included installation instructions including all of the required A and CNAME host records for your domain provider.

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

Pages is a feature of GitHub that can serve static web files for a repository, typically for docs or a wiki. *We’ll* be using it to serve a compiled React/Vue project. 

Read more: https://docs.github.com/en/github/working-with-github-pages

I should note here that this won’t host an app that relies on Node. You’ll need a proper web server for that.

### Getting started

It can be set up in minutes, and has a few nice features out-of-the-box:

- The repository contains a GitHub Actions workflow to automatically build and deploy any pushed changes. No messing around with external pipelines (i.e. Travis CI), and a private repo can still get ~2000 deployments per month. 

![GitHub Actions for Deployment to GitHub Pages](https://dev-to-uploads.s3.amazonaws.com/i/grgc0b8a1aynlhwrlxcy.png)

- The repository contains a CNAME file, along with easy instructions for pointing your domain to the site using your provider’s DNS host records.

![Namecheap DNS CNAME and A Host Records](https://dev-to-uploads.s3.amazonaws.com/i/x4x75n365cecaan2cgic.png)

- The README also contains instructions for launching *unlimited* static sites, each to its own subdomain. You can now publish a blog, or separate out your portfolio’s projects into repos under the same domain, all for free. 

![CNAME Subdomain for Separate GitHub Pages Repo](https://dev-to-uploads.s3.amazonaws.com/i/qrqekkjetz3x9rbfle7n.png)

All instructions are in the repository’s README, but let’s get started below!

### Usage

Get started in minutes with these instructions:

1. Create a repository from this template (include all branches).
2. Rename your repository to `<username>.github.io`.
3. Make sure that GitHub Pages uses the build branch.

The branch can be selected at `Settings -> Options -> GitHub Pages -> Source`.

### Architecture

This is real simple:

- The master branch contains a React/Vue project.
- The build branch will contain the compiled React/Vue application.
- When you push to master, a GitHub Action compiles the updated project into build.

![Example Build and Deploy after Push to Master](https://dev-to-uploads.s3.amazonaws.com/i/2leb512bdca5378jq8to.png)

### Development

Any commits pushed or merged into master will trigger the build action.

These changes will be reflected on your GitHub Pages site after around 60 seconds.

### Domain Names

**Apex Domain**

First, set your domain name within the GitHub repository.

- In the CNAME file, replace example.com with your domain.
- This can also be done in `Settings -> Options -> GitHub Pages -> Source`.

![CNAME Subdomain for Separate GitHub Pages Repo](https://dev-to-uploads.s3.amazonaws.com/i/qrqekkjetz3x9rbfle7n.png)

Second, configure your DNS host records with your domain provider.

- Create an A record for host "@" pointing to 185.199.108.153.
- Create an A record for host "@" pointing to 185.199.109.153.
- Create an A record for host "@" pointing to 185.199.110.153.
- Create an A record for host "@" pointing to 185.199.111.153.

**Subdomains**

You can configure a subdomain, such as `www.[example.com]`, in your DNS host records.

- Create a CNAME record for host "www" pointing to `<username>.github.io`.

### Infinite Hosting

The awesome power of this is that you can have a repository for each and every subdomain.

1. Create a repository from this template with any name (include all branches).
2. Enable GitHub Pages for it (`Settings -> Options -> GitHub Pages -> Source`).
3. In the CNAME file, replace `example.com` with your apex and subdomain (i.e. `blog.[example.com]`).
4. With your domain provider, create a CNAME record for host "[blog]" pointing to `<username>.github.io`.

This is how I achieved each of these, for free:

- Vue: https://vue.lloyd.cx/
- Nuxt: https://nuxt.lloyd.cx/
- React: https://react.lloyd.cx/

What's not to love? 😉

---

Hey, guys! Thank you for reading. I hope that you enjoyed this.

Keep up to date with me:

- DEV: https://dev.to/tao/
- Twitter: https://twitter.com/LloydTao
- GitHub: https://github.com/LloydTao
- LinkedIn: https://www.linkedin.com/in/LloydTao/

Catch you around!
