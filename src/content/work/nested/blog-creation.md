---
title: Creation of this portfolio
publishDate: 2023-09-20 17:00:00
img: /blog1/miniature.png
img_alt: Logos of Github and Astro.build
description: |
  Short summary of this portfolio's development
tags:
  - Development
  - Portfolio
  - Blog
---

### Motivations

As a last year engineering student, it became more and more necessary for me to have an online portfolio. A website portfolio is a practical and interactive way to showcase your work to recruiters and fellow students.

In this first ever blog post, I will go over the creation process of this website that can be followed as a tutorial.

### Technologies

To create our portfolio, we will be using GitHub pages to host our page and Astro.build as a template provider.

GitHub pages allows you to host any project for free. 
The page will be linked to your personnal or company account. If you already have a DNS address to your name (which you can buy online to DNS providers), you can set it as a custom URL. 
However, you can only host one project at a time with the standard account subscription (free subscription).

Astro.build provides many templates for diverse uses: portfolio, blog, marketing page,ect.

To not be redundant and concise, I will provide a link to each services relevant tutorials when necessary.

---

## Starting our project

Start by creating a working folder on your local device.
This folder will contain all your code and assets.

### Selecting a template and initiating your project

Head over to [Astro's website](https://www.astro.build) and select a design you enjoy and that seems relevant to your industry (make sure to select a different template than mine, I have no reason for that request).

Once you've found the template of your dreams, follow this [tutorial](https://docs.astro.build/en/getting-started/).

Make sure to load your project in the folder you previously created.

Before moving on to the next part, make sure that the folder you previously created contains the Astro template files.

### Initializing your Git repository

A GitHub repository is an online folder containing the files of a particular project. 
Those online files are the ones that will be used to display your website.
Everytime you want to update your website (post a new blog post, update your carreer history), those are the files you will have to modify.

First create a project on GitHub following [this tutorial](https://pages.github.com/).

**The name of your project MUST be in the form <USERNAME>.github.io !**

Then, clone your repository:

```bash
> cd /your_local_project_folder
> git clone https://www.github.com/<USERNAME>/<USERNAME>.github.io.git
```
This links your local folder to the remote repository.

When done, we must upload our files.

```bash
> git add * 
> git commit -m "Initial Website Commit"
> git push
```

### Setting your Astro template as a GitHub page

We can deploy our Astro website using GitHub Actions.

1. Copy/Paste and modify this block of code to your astro.config.mjs file.

```msj
import { defineConfig } from 'astro/config'

export default defineConfig({
  site: 'https://astronaut.github.io',
})
```

This file should be located at the root of your project (in the original folder).

Customize it to fit your website's URL. 


2. Create a new file in your project at .github/workflows/deploy.yml and paste in the YAML below.

Create the folders and the file. Then paste this code:

```yml
name: Deploy to GitHub Pages

on:
  # Trigger the workflow every time you push to the `main` branch
  # Using a different branch name? Replace `main` with your branch’s name
  push:
    branches: [ main ]
  # Allows you to run this workflow manually from the Actions tab on GitHub.
  workflow_dispatch:

# Allow this job to clone the repo and create a page deployment
permissions:
  contents: read
  pages: write
  id-token: write

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout your repository using git
        uses: actions/checkout@v3
      - name: Install, build, and upload your site
        uses: withastro/action@v0
        # with:
            # path: . # The root location of your Astro project inside the repository. (optional)
            # node-version: 16 # The specific version of Node that should be used to build your site. Defaults to 16. (optional)
            # package-manager: yarn # The Node package manager that should be used to install dependencies and build your site. Automatically detected based on your lockfile. (optional)

  deploy:
    needs: build
    runs-on: ubuntu-latest
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v1
```
3.On GitHub, go to your repository’s Settings tab and find the Pages section of the settings.

4.Choose GitHub Actions as the Source of your site.

5.Commit the new workflow file and push it to GitHub.

Everything should now be online ! 
(This was a shameless copy of [Astro's tutorial](https://docs.astro.build/en/guides/deploy/github/))

### Done !

Now, it's your turn to customize your portfolio ! Add pictures, blog posts about your past projects, introduce yourself.

All pages are customizable using basic HTML5 and CSS3.

If you're not too familiar with those technologies, they are really easy to learn and understand, so give it a shot !







