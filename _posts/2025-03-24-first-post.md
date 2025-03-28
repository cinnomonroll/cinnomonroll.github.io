---
layout: post
title:  "My First Post"
# description:
date: 2025-03-24 12:00:00 -0400
categories: [blog]
tags: [jekyll, learning]
published: true
---

## Why I Started This Blog
I’ve always believed that the best way to truly understand something is to explain it. Recently, I’ve been attending courses, working through DataCamp, and learning a lot of new things—some of which I don’t want to forget. That’s why I started this blog: to document what I’m learning and solidify my understanding by sharing it.

At the same time, I see this blog as a fun side project to experiment with new technologies. Building it gave me a chance to explore different tools!

Along the way, I’ll also be sharing some of my projects. Hopefully, this blog will not only help me track my progress but also be useful for others who are on a similar learning journey.

## Tech Stack & Tools I Used to Built This Blog
When I decided to create this blog, I wanted something simple, lightweight, and easy to maintain. After some research, I chose GitHub Pages for hosting—it's completely free! (Though it only supports static sites.)

To generate and manage the blog, I went with Jekyll, a powerful static site generator that converts Markdown files into a fully functional website. This makes it an excellent choice for a minimal, no-database blog setup.

Here’s how I set everything up, step by step:

### Step 1: Setting Up GitHub Pages
GitHub Pages allows you to host a website directly from a GitHub repository. To set it up:

- Go to GitHub and click New Repository.
- Name it yourusername.github.io (replace yourusername with your actual GitHub username).
- Set it to Public and check the box to initialize with a README.

### Step 2: Installing Jekyll Locally
Instead of starting from scratch, I forked an existing Jekyll template to save time and get a well-designed setup right away. I found a great collection of Jekyll themes on **[Jamstack Themes](https://jamstackthemes.dev/ssg/jekyll/)** and chose **"Chirpy"** because of its clean design and useful features.

#### 1. Forking the Chirpy Repository
I went to the **[Chirpy GitHub Repository](https://github.com/cotes2020/jekyll-theme-chirpy)** and clicked the Fork button. The other way is to follow the guidance from the author[Getting Startted](https://tranglc.github.io/posts/getting-started/)
This created a copy of the project in my own GitHub account, which I could customize as needed.

#### 2. Cloning the Repository Locally
Once I forked the repo, I cloned it to my local machine using:
```sh
git clone git@github.com:cinnomonroll/cinnomonroll.github.io.git
cd cinnomonroll.github.io
```
#### 3. Installing Dependencies
Since Chirpy is built with Jekyll, I first needed to install Ruby and necessary Jekyll’s dependencies:

For macOS (using Homebrew):
```sh
brew install ruby
gem install bundler jekyll
```
Then, inside the project folder, I installed the necessary gems:
```
bundle install
```

The `bundle` command automatically installs all dependencies specified by `Gemfile`.

Additionally, to generate extra files like categories, tags, and last modified timestamps, Chirpy uses some tool scripts that may rely on GNU coreutils. These utilities include enhanced versions of standard Unix commands such as `date`, `readlink`, and `stat`, which behave differently on macOS by default.

Since macOS uses BSD coreutils, it's recommended to install the GNU version for better compatibility:

macOS
```
brew install coreutils
```
This ensures that the scripts run smoothly, especially if they use GNU-specific flags or behavior.

#### 4. Running the Blog Locally
To preview the blog before deploying, I started the local Jekyll server:
```
bundle exec jekyll serve
```
Now, I could see the blog running at `http://localhost:4000/` in my browser.

#### 5: Writing and Customizing the Blog
Once the blog was running, I started customizing it to make it my own. Here are some key customizations I made:

✔ **Updating Blog Info in `_config.yml`**

The **`_config.yml`** file contains the blog’s main settings. I updated it with my own information by following the provided guidelines. For any settings I didn’t need, I simply left them blank.

> Note: After making changes to **`_config.yml`** you need to restart the local server for it to take effect:
> ```
> bundle exec jekyll serve
> ```

✔ **Uploading an Avatar**

I found a cute avatar from **[Avatar Generator](https://www.peppercarrot.com/extras/html/2020_mobilizon-generator/)**. and decided to use it for my profile. Since this was an online source, I didn’t create it myself—I just referred to it as my avatar.

Once I had the image, I stored it in the **`assets/`** folder, where all images for the blog are kept.

✔ **Modifying the Sidebar (`_tabs/`Directory**)

The sidebar includes sections such as **`about.md`**, **`archives.md`**, **`tags.md`** and **`categories.md`**. You can customize their order by modifying their files.

For my setup, I only updated **`about.md`** and left the other sections as default.

✔ **Creating a New Blog Post**

All blog posts are stored in the **`_posts/`** directory.
Each post file name follows this format: `YYYY-MM-DD-ArticleName.md`
> Note: The date in the filename cannot be in the future.

Each post follows this format:
```markdown
---
layout: post
title: "Your Post Name"
date: YYYY-MM-DD
categories: [blog]
tags: [jekyll, customization]
---

This is my first blog post! 🚀
```
Once the post is added, Jekyll will automatically display it on the blog.





For more setting details **[Chirpy Doc](https://chirpy.cotes.page)**

