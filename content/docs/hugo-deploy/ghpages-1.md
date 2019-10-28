---
title: "ghpages (1): user site and project site"
date: 2019-10-23T20:53:55+09:00
categories:
    - generic
tags:
    - generic
keywords:
inspired: https://help.github.com/en/github/working-with-github-pages/about-github-pages#publishing-sources-for-github-pages-sites
motivation: ""
draft: true
---

### About GitHub Pages

GitHub Pages is a static site hosting service that takes HTML, CSS, and JavaScript files straight from a repository on GitHub.
See [ GitHub Pages examples collection](https://github.com/collections/github-pages-examples).

### Types of GitHub Pages sites

There are three types of GitHub Pages sites: project, user, and organization.

- User sites are always published from a repository named `<user>.github.io`.
Unless you're using a custom domain, user and organization sites are available at `http(s)://<username>.github.io`.

- The source files for a project site are stored in the same repository as their project. Unless you're using a custom domain, project sites are available at `http(s)://<user>.github.io/<repository>`.

You can only create one user or organization site for each GitHub account. Project sites, whether owned by an organization or a user account, are unlimited.

### Publishing sources for GitHub Pages sites

The publishing source for your GitHub Pages site is the branch or folder where the source files for your site are stored. All sites have a default publishing source, and* project sites have additional publishing sources available*.[^gh1-1]

[^gh1-1]: ?

- The default publishing source for user and organization sites is the `master` branch. If the repository for your user or organization site has a `master` branch, your site will publish automatically from that branch. You cannot choose a different publishing source for user or organization sites.

- The default publishing source for a project site is the `gh-pages` branch. If the repository for your project site has a `gh-pages` branch, your site will publish automatically from that branch.

- Project sites can also be published from the `master` branch or a `/docs` folder on the `master` branch. To publish your site from one of these sources, you must configure a different publishing source. For more information, see [Configuring a publishing source for your GitHub Pages site](https://help.github.com/en/github/working-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#choosing-a-publishing-source).


### Static site generators

GitHub Pages will use `Jekyll` to build your site by default. If you want to use a static site generator other than `Jekyll`,

1. *disable the `Jekyll` build process by creating an empty file called `.nojekyll` in the root of your publishing source*,
2. then follow your static site generator's instructions to build your site locally.

GitHub Pages does not support server-side languages such as PHP, Ruby, or Python.

### Guidelines for using GitHub Pages

- GitHub Pages sites created after June 15, 2016 and using `github.io` domains are served over HTTPS.
- GitHub Pages sites shouldn't be used for sensitive transactions like sending passwords or credit card numbers.
- Your use of GitHub Pages is subject to the [GitHub Terms of Service](https://help.github.com/en/github/site-policy/github-terms-of-service), including the prohibition on reselling.

#### Usage limits

GitHub Pages sites are subject to the following usage limits:

- Source repositories have a recommended limit of 1 GB. For more information, see [What is my disk quota?](https://help.github.com/en/github/managing-large-files/what-is-my-disk-quota#file-and-repository-size-limitations).
- Published GitHub Pages sites may be no larger than 1 GB.
- Bandwidth limit of 100 GB per month.
- Limit of 10 builds per hour.

If your site exceeds these usage quotas, we may not be able to serve your site, or you may receive a polite email from GitHub Support or GitHub Premium Support suggesting strategies for reducing your site's impact on our servers, including putting ...

#### Prohibited uses

...

### MIME types on GitHub Pages

...

