---
title: "create website using hugo"
date: 2023-07-16T00:04:18+05:30
draft: true
---

### Hugo is a fast and modern static site generator written in Go, and designed to make website creation fun again.
Hugo is a general-purpose website framework. Technically speaking, Hugo is a static site generator. Unlike systems that dynamically build a page with each visitor request, Hugo builds pages when you create or update your content. Since websites are viewed far more often than they are edited, Hugo is designed to provide an optimal viewing experience for your website’s end users and an ideal writing experience for website authors.
Websites built with Hugo are extremely fast and secure. Hugo sites can be hosted anywhere, including Netlify, Heroku, GoDaddy, DreamHost, GitHub Pages, GitLab Pages, Surge, Firebase, Google Cloud Storage, Amazon S3, Rackspace, Azure, and CloudFront and work well with CDNs. Hugo sites run without the need for a database or dependencies on expensive runtimes like Ruby, Python, or PHP.
General 
Extremely fast build times (< 1 ms per page)
Completely cross platform, with easy installation on macOS, Linux, Windows, and more
Renders changes on the fly with LiveReload as you develop
Powerful theming
Host your site anywhere
Organization 
Straightforward organization for your projects, including website sections
Customizable URLs
Support for configurable taxonomies, including categories and tags
Sort content as you desire through powerful template functions
Automatic table of contents generation
Dynamic menu creation
Pretty URLs support
Permalink pattern support
Redirects via aliases
Content 
Native Markdown and Emacs Org-Mode support, as well as other languages via external helpers (see supported formats)
TOML, YAML, and JSON metadata support in front matter
Customizable homepage
Multiple content types
Automatic and user defined content summaries
Shortcodes to enable rich content inside of Markdown
“Minutes to Read” functionality
“WordCount” functionality
Additional features 
Integrated Disqus comment support
Integrated Google Analytics support
Automatic RSS creation
Support for Go HTML templates
Syntax highlighting powered by Chroma
Quick start
Learn to create a Hugo site in minutes.
In this tutorial you will:

Create a site
Add content
Configure the site
Publish the site
Prerequisites 
Before you begin this tutorial you must:

Install Hugo (extended edition, v0.112.0 or later)
Install Git
You must also be comfortable working from the command line.

Create a site 
Commands 
If you are a Windows user:

Do not use the Command Prompt
Do not use Windows PowerShell
Run these commands from PowerShell or a Linux terminal such as WSL or Git Bash
PowerShell and Windows PowerShell are different applications.

Run these commands to create a Hugo site with the Ananke theme. The next section provides an explanation of each command.

hugo new site quickstart
cd quickstart
git init
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
echo "theme = 'ananke'" >> hugo.toml
hugo server
View your site at the URL displayed in your terminal. Press Ctrl + C to stop Hugo’s development server.

Explanation of commands 
Create the directory structure for your project in the quickstart directory.

hugo new site quickstart
Change the current directory to the root of your project.

cd quickstart
Initialize an empty Git repository in the current directory.

git init
Clone the Ananke theme into the themes directory, adding it to your project as a Git submodule.

git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
Append a line to the site configuration file, indicating the current theme.

echo "theme = 'ananke'" >> hugo.toml
Start Hugo’s development server to view the site.

hugo server
Press Ctrl + C to stop Hugo’s development server.

Add content 
Add a new page to your site.

hugo new posts/my-first-post.md
Hugo created the file in the content/posts directory. Open the file with your editor.

---
title: "My First Post"
date: 2022-11-20T09:03:20-08:00
draft: true
---
Notice the draft value in the front matter is true. By default, Hugo does not publish draft content when you build the site. Learn more about draft, future, and expired content.

Add some markdown to the body of the post, but do not change the draft value.

---
title: "My First Post"
date: 2022-11-20T09:03:20-08:00
draft: true
---
## Introduction

This is **bold** text, and this is *emphasized* text.

Visit the [Hugo](https://gohugo.io) website!
Save the file, then start Hugo’s development server to view the site. You can run either of the following commands to include draft content.

hugo server --buildDrafts
hugo server -D
View your site at the URL displayed in your terminal. Keep the development server running as you continue to add and change content.

Hugo’s rendering engine conforms to the CommonMark specification for markdown. The CommonMark organization provides a useful live testing tool powered by the reference implementation.

Configure the site 
With your editor, open the site configuration file (hugo.toml) in the root of your project.

