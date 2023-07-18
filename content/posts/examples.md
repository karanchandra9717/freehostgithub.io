---
title : "hugo example"
date : 2023-07-16T00:04:18+05:30
draft : true
---

Example Hugo website using GitLab Pages.
Learn more about GitLab Pages at the official documentation.

GitLab CI/CD
This project's static Pages are built by GitLab CI/CD,
following the steps defined in .gitlab-ci.yml.

Building locally
To work locally with this project, you'll have to follow the steps below:


Fork, clone or download this project.


Install git and go.


Install Hugo.


Install the theme as a Hugo module:

hugo mod get -u github.com/theNewDynamic/gohugo-theme-ananke




Preview your project:

hugo server




Add content.


Optional. Generate the website:

hugo




Read more at Hugo's documentation.

Use a custom theme
Hugo supports a variety of themes.
Visit https://themes.gohugo.io/ and pick the theme you want to use. In the
Pages example, we use https://themes.gohugo.io/themes/gohugo-theme-ananke/.

Use a custom theme using a Hugo module
The example .gitlab-ci.yml uses Hugo modules to import the theme.
To use your own theme, the following steps will help you recreate the hugo modules
that include the information of your theme. You must perform them locally:


Edit config.toml and comment out the already existing theme:

#theme = ["github.com/theNewDynamic/gohugo-theme-ananke"]




Remove go.mod and go.sum:

rm -f go.mod go.sum




Recreate the theme module:

hugo mod init gitlab.com/pages/hugo




Recreate the checksum:

hugo mod get -u github.com/theNewDynamic/gohugo-theme-ananke




Edit config.toml and add the theme back:

theme = ["github.com/theNewDynamic/gohugo-theme-ananke"]




Finally, edit .gitlab-ci.yml, and replace the THEME_URL variable with the URL of your theme:

THEME_URL: "github.com/theNewDynamic/gohugo-theme-ananke"




Commit all the changes and push them to your repository.



hugo vs hugo_extended

The Container Registry
contains two kinds of Hugo Docker images, hugo and
hugo_extended. Their main difference is that hugo_extended comes with
Sass/SCSS support. If you don't know if your theme supports it, it's safe to
use hugo_extended since it's a superset of hugo.
The Container Registry contains three repositories:

registry.gitlab.com/pages/hugo
registry.gitlab.com/pages/hugo/hugo
registry.gitlab.com/pages/hugo/hugo_extended

pages/hugo:<version> and pages/hugo/hugo:<version> are effectively the same.
hugo_extended was created afterwards, so we had to create the pages/hugo/ namespace.
See how the images are built and deployed.

