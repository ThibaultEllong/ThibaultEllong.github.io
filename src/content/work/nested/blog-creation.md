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

First create a project on GitHub.

**The name of your project MUST be in the form <USERNAME>.github.io !

Then, clone your repository:

'''terminal
> cd /your_local_project_folder
> git clone https://www.github.com/<USERNAME>/<USERNAME>.github.io.git
'''
This links your local folder to the remote repository.

When done, we must upload our files.

'''terminal
> git add * 
> git commit -m "Initial Website Commit"
> git push
'''





