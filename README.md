# guac.sh

This repository is the home of guac.sh.

## Building the site

You must have [Hugo](https://gohugo.io/) installed.

To build the site, run `hugo server -D`.
This will run a local webserver (defaults to port 1313) where you can verify your changes.

## Contributing

The repository requires a [Developer Certificate of Origin](https://developercertificate.org/) (use the `-s` flag on `git commit`).
See [contributing.md](contributing.md) for more information about contributing to GUAC.

We do not have a style guide yet.
Perhaps someday.

### Adding a blog post

Blog posts come from files in content/blog.
Use a filename of the format `YYYY-MM-DD-WORDS_GO_HERE.md`.
The date encoded in the file name doesn't matter for publication, but it makes sorting in the repo easier.

The file must begin with a header that contains some pertinent information:

* `title`: The title of the post.
* `date`: The date (in `YYYY-MM-DD` format.
Other formats *might* work, but why take chances?)
This is the date used by Hugo to sort the posts.
*If you use a date in the future, it will not be listed on the blog page.*
* `authors` (optional): An array of names to list as the author.
If you only have one author, it still needs to be quoted and in square brackets.

A complete header looks something like:

```
---
title: This is a great blog post
date: 2023-04-13
authors: ["Ben Cotton", "Jane Doe", "Blogger McBlogface"]
---
```

Below the header, write the content.
For ease of writing, use Markdown by default.
You may use HTML when needed.

## Layout

* config.yml — Site configuration and main page content
* content/blog/* — Blog posts
* content/* — Other pages


