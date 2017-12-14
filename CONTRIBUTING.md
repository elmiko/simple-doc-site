# Contributing to Simple Doc Site

In general, all contributions should be made by forking this repository,
making your changes on a feature branch, and proposing that feature branch
as a pull request in GitHub.

This site is generated using the [Jekyll framework](https://jekyllrb.com),
with several customizations to create the look and feel. Please reference
their documentation for questions about the usage of jekyll features in your
documents.

## Adding documents to Simple Doc Site

To add new documents to the site, create new AsciiDoc based files in the
`_docs` directory. After adding your new files follow the instructions for
testing the site to see your content rendered. Documents will appear in the
main listing at the index (`/`) for your site.

## Testing out your changes locally

To test this site locally, you will need to have Ruby installed as well as the
[Bundler](https://bundler.io) gem. This will make installing and
running the site much simpler. Provided that you have Ruby and the `gem`
command installed, a quickstart to running the site will be:

```
$ gem install bundler
$ cd simple-doc-site
$ bundle exec jekyll serve
```

At this point the site will be running and served locally at
`http://localhost:4000`, with the server running any file changes will be
automatically picked up and the site re-generated.

**A note on Mac OSX development**
A common source of problems for Mac users when installing Jekyll's
dependencies is the [Nokogiri library](http://www.nokogiri.org). Should your
`bundle install` run into trouble installing Nokogiri, please see the
[suggestions offered in the Nokogiri docs](http://www.nokogiri.org/tutorials/installing_nokogiri.html#mac_os_x)
or consult [Stack Overflow](https://stackoverflow.com) for other possible
fixes.

### Docker based testing

If you would prefer to use a self-contained environment for testing your
changes, a Dockerfile is provided in the root of the project which will
allow you to leverage the convenience of docker. To test your changes using
this methodology run the following:

```
docker run --rm -v "$PWD:/srv/jekyll:Z" -p 4000:4000 -it\
 jekyll/jekyll:3.5 jekyll serve
```

The site will now be served locally at `http://localhost:4000`

Files that will be processed by jekyll contain a bit at the beginning referred
to as . This is a small
section of YAML that contains variables which will be available to the
processing engine. When creating your application documentation there are
several front matter variables which will help with the proper display of
your information. Please be careful to follow the instructions in the template
about their usage.

### A note on AsciiDoc AttributeEntry blocks

AsciiDoc documents may contain
[AttributeEntry blocks](http://asciidoc.org/asciidoc.css-embedded.html#X18)
in their headers. These variables are used in a similar manner as the Jekyll
[front matter](https://jekyllrb.com/docs/frontmatter/) variables. Although
these attribute entries and front matter can co-exist within the current
deployment framework, the preference should be to always use AsciiDoc
attribute entries when possible.
