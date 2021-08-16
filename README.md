# catch-muri
This is a Jekyll-based website for a research group.

## Software for working on the website

The website is hosted on GitHub and served by [GitHub Pages](https://pages.github.com/) which [supports Jekyll](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll) as a first-class citizen. It is easy to develop Jekyll-based websites with open-source support for all major operating systems - it is recommended to [locally setup](https://jekyllrb.com/docs/installation/) Jekyll (based on Ruby), as you can then easily run a local server to preview changes prior to uploading them to the website. However, GitHub automatically runs continuous integration for Pages to do all the heavy lifting - small changes can be made by editing [Markdown (.md)](https://www.markdownguide.org/basic-syntax/) files and uploading with git. This readme summaries common maintenance tasks.

## Adding a news post
Simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.markdown` and includes the necessary front matter (layout: post, title, date, categories).
~~~~
---
layout: post
title:  "Welcome to the web site!"
date:   2018-10-01 23:55:23 +1000
categories: jekyll update
---
~~~~

## Updating team members
Add an image with small file size (ideally 10kB or thereabouts) and ideally 200 x 200 dimensions, to the `assets/people` directory -- if you have a larger source file, you may place it in `assets/people-raw` for safekeeping. Add a markdown file in the `_investigators`, `_postdocs`, or `_phds` directory as appropriate with the necessary front matter:
~~~~
---
layout: person
name: "Dr Postdoc McPostdoc"
title: "Dr Postdoc McPostdoc"
role: "Postdoc"
affiliation: "A University"
email: something@somewhere
homepage: https://somewhere.edu
categories: jekyll update
image: assets/people/filename.jpg
order: 100
---
~~~~
Following this front matter add a biography. The root-level `peope.md` page will automatically add the new team member, and open up/close categories of people when they're available based on where you place the Markdown file.

Team members leaving the group can be moved to the `_alums` directory.

## Creating a new page
Add the markdown file in the `root` directory with the necessary front matter (layout: page, title, categories).

Categories may include `navi` or `browse`.
* `navi` is for adding the page to the navigation bar
* `browse` is for adding the page to the browsing topics on the home page

~~~~
---
layout: page
title: News
categories: [navi]
---
~~~~

~~~~
---
layout: page
title: About
categories: [navi, browse]
browse-description: Learn more about our organisation.
---
~~~~

## Posting job opportunities
To post job opportunities:

* Add an item to `careers.md` page. Suggest a short title, location, closing date, with link to external job application site.
* Ensure the `careers.md` front matter includes `categories: [browse]` to include an alert linking to opportunities on the website's landing page. Typically we keep the navigation bar stable, so prefer not to temporarily show opportunities there but this is a possibility.

Remember to turn off the `categories: [browse]` front matter when there are no available opportunities in the group. (We might investigate streamlining this in the future, if it becomes a hassle, using closing dates.)

## Adding a new research area
Add the markdown file in the `_research-areas` directory and include the necessary front matter (layout: page, title).
~~~~
---
layout: page
title:  "Research Area 2"
---
~~~~

## Acknowledgements

We thank the [ARC Training Centre in Cognitive Computing for Medical Technologies](https://github.com/eltimster/arc-medtechai) for serving as a template for this website's source.

<!-- ## Creating a nested section
1. Create a new folder in the `root` directory with the appropriate name of the section. Place the markdown files in the folder, and any further nesting in subfolders. **This template allows nesting with depth of at most 2.**

2. In the `_data` folder, add a `.yml` file with the same name as the section folder created previously. Describe the table of contents for navigation that will appear for the section as follows:

~~~~
toc:
- page: Nested
  url: /nested/
- page: Section 1
  url: /nested/section1.html
- page: Section 2
  url: /nested/section2/
  subpages:
    - page: Subsection
      url: /nested/section2/subsection.html
    - page: Subsection 2
      url: /nested/section2/subsection2.html
~~~~

(See sample `nested` directory file.)-->
