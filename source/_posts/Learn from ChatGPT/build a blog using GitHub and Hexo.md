---
title: build a blog using GitHub and Hexo
date: 2023-04-21
tags: [tag1,tag2]
---

# Key Points

-  what is node.js
-  what is hexo
-  in the blog, what roles do different tools play?
-  where can i change the content of my blog?
-  how can i make it more fancy?

note: there are two repos in the building of project. one(name.github.io) is for the deployment, the other is for the storeration of code.


# To build a blog using GitHub and Hexo, follow these steps:

1. **Install Node.js and Git:**

Hexo is built on Node.js, so you will need to install it on your local machine. Visit the Node.js website (https://nodejs.org/) to download and install the latest version of Node.js. Also, ensure you have Git installed on your machine (https://git-scm.com/downloads).

2. **Install Hexo:**

Open a terminal (or command prompt) and install Hexo using the following command:

```
npm install -g hexo-cli
```

3. **Create a new Hexo project:**

In the terminal, navigate to the directory where you want to create your blog and run the following command:

```
hexo init my-blog
```

Replace `my-blog` with the desired name for your blog directory. This command will create a new Hexo project in the specified directory.

4. **Install dependencies:**

Navigate to the new project directory and install the necessary dependencies:

```
cd my-blog
npm install
```

5. **Run the Hexo server:**

Start the Hexo server to preview your blog:

```
hexo server
```

By default, your blog will be accessible at `http://localhost:4000`.

6. **Customize your blog:**

Edit the `_config.yml` file in the project directory to customize your blog's settings, such as title, description, and theme. You can also create new posts and pages using the following commands:

```
hexo new post "Your Post Title"
hexo new page "Your Page Title"
```

7. **Deploy your blog to GitHub Pages:**

First, install the Hexo GitHub Pages deployment plugin:

```
npm install hexo-deployer-git --save
```

Next, configure the deployment settings in the `_config.yml` file by adding the following lines:

```
deploy:
  type: git
  repo: https://github.com/yourusername/yourusername.github.io
  branch: main
```

Replace `yourusername` with your GitHub username.

Commit your changes and push your project to a new repository on GitHub:

```
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/yourusername/my-blog.git
git push -u origin main
```

Replace `yourusername` with your GitHub username and `my-blog` with the desired repository name.

Finally, deploy your blog to GitHub Pages:

```
hexo generate
hexo deploy
```

Your blog should now be available at `https://yourusername.github.io`.

For more information on Hexo and its features, visit the official Hexo documentation: https://hexo.io/docs/