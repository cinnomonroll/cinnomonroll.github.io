---
layout: post
title:  "My First Post"
# description:
date: 2025-03-24
categories: [blog]
tags: [jekyll, learning]
# published: true
---

## Why I Started This Blog
I’ve always believed that the best way to truly understand something is to explain it. Recently, I’ve been attending courses, working through DataCamp, and learning a lot of new things—some of which I don’t want to forget. That’s why I started this blog: to document what I’m learning and solidify my understanding by sharing it.

At the same time, I see this blog as a fun side project to experiment with new technologies. Building it gave me a chance to explore different tools!

Along the way, I’ll also be sharing some of my projects. Hopefully, this blog will not only help me track my progress but also be useful for others who are on a similar learning journey.

## Tech Stack & Tools I Used to Built This Blog
When I decided to create this blog, I wanted something simple, lightweight, and easy to maintain. After some research, I chose GitHub Pages for hosting—it's completely free! (Though it only supports static sites.)

To generate and manage the blog, I went with Jekyll, a powerful static site generator that converts Markdown files into a fully functional website. This makes it an excellent choice for a minimal, no-database blog setup.

Here’s how I set everything up, step by step:

### Step 1: Creating a Repository
I followed the guildance from the **[official docs](https://chirpy.cotes.page/posts/getting-started/)**. 

> Note: Always make sure you are using the latest version of the documentation. I accidentally followed an older version and encountered some issues.

- Navigate to [Chirpy-Starter](https://github.com/cotes2020/chirpy-starter) and click **Use this template** button located in the top-right corner. Then select **Create New Repository**.
- Name the repository `yourusername.github.io` (replace `yourusername` with your actual GitHub username).
- Set the repository visibility to Public and check the box to initialize it with a README.


### Step 2: Setting Up the Environment
Instead of installing Jekyll locally, I followed the recommendation to use Docker. This approach ensures that all dependencies are managed within a container, reducing setup errors. If you prefer exploring other Jekyll themes, consider browsing options at **[Jamstack Themes](https://jamstackthemes.dev/ssg/jekyll/)**

- Install [Docker Desktop](https://www.docker.com/products/docker-desktop/)
  - For MacOS users: Launch Docker and ensure you see the Docker icon in the top-right corner of your screen, which indicates that Docker is active.
- Clone your repository within a container by following the instructions provided in[VS Code's docs](https://code.visualstudio.com/docs/devcontainers/containers#_quick-start-open-a-git-repository-or-github-pr-in-an-isolated-container-volume)

If you encounter difficulties with the container setup, here's an alternative method that worked for me:

1. **Clone the repository** manually and navigate to the project directory.
2. Launch the Command Palette by pressing`Cmd + Shift + P`.
3. **Type and select** `Dev Containers: Reopen in Container`.
4. VS Code will: 
  - Detect your .devcontainer folder
  - Build the container
  - Open the project inside the container
5. After a few minutes, your terminal should display something similar to:
  ```
  `vscode ➜ /workspaces/ourusername.github.io (main)`
  ```

### Step 3:Start the Jekyll Server
To run the site locally, use the following command:
```
bundle exec jekyll s
```
After a few seconds, the local server will be available at `http://127.0.0.1:4000`

### Step 4:Writing and Customizing the Blog
Once the blog was running, I started customizing it to make it my own. Here are some key customizations I made:

✔ **Updating Blog Info in `_config.yml`**

The **`_config.yml`** file contains the blog’s main settings. I updated it with my own information by following the provided guidelines. For any settings I didn’t need, I simply left them blank.

> Note: After making changes to **`_config.yml`** you need to restart the local server for it to take effect:
> ```
> bundle exec jekyll s
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

### Step 5: Deploy Using Github Actions
To configure the GitHub Pages service, follow these steps:
- Go to your repository and select **Settings**
- Click on **Pages** in the left navigation bar 
- In the **Source** section, select **`GitHub Actions`** from the dropdown menu.
- Push any commits to GitHub to trigger the Actions workflow. 

Once the build is complete and successful, the site will be deployed automatically!

#### Troubleshooting Git Remote URL Issues

I encountered an issue where Git automatically rewrote URLs starting with `https://github.com/` to `git@github.com:`. EvenEven forcing HTTPS didn't work. To resolve this:

1. Check the Global "insteadOf" Rule:
```
git config --global --get-regexp "url.*insteadOf"
```
This command outputs a rule indicating that Git is rewriting `https://github.com/` to `git@github.com:`

2. Remove the Rule:
```
git config --global --unset-all url.git@github.com:.insteadof
```
3. Verify the Remote URL:
```
git remote get-url origin
```

You should see:
```
https://github.com/yourusername/yourusername.github.io.git
```

You're all set!


<!-- 



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


