# LolasView.com

**Personal Blog** created with [Jekyll][jekyll] and the gorgeous gem-based
theme [Minimal Mistakes][mmistakes].

## Setup

Open up **Tilix terminal** and set up the project in your code directory:

```
$ sudo apt install git ruby
$ mkdir code
$ cd code
$ git clone git@github.com:netzfisch/lolasview.com.git
$ cd lolasview.com
$ bundle install
```

> This only needs to be done once!

## Write

To write a **new posts**, simply add a file in the `_posts/` directory that
follows the naming convention `YYYY-MM-DD-name-of-post.md`, edit the post with
**gedit text editor** and include necessary front matter (title, excerpt, header
image/teaser, categories, tags, etc.).

Use the **file manager** to look at the source of **existing blog posts** and
check [markdwon syntax][kramdown] to get an idea how to format text and add
hyperlinks! To see it in the context of the theme look parallel at the [formated
post][markup-post] vs. the [raw version][markup-raw].

**Images** need to be placed in the folder `assets/imgages/` with following name
convention about name and dimension

* `..._header.jpg` with a 3:1 ratio: 1200x400 pixel (banner)
* `..._large.jpg` with a 1:1 ratio: 800x800 pixel (square)
* `..._large.jpg` with a 4:3 ratio: 800x600 pixel (postcard)
* `..._small.jpg` with a 2:3 ratio: 300x450 pixel (portrait)
* `..._small.jpg` with a 3:2 ratio: 300x200 pixel (postcard)
* `..._teaser.jpg` with a 3:2 ratio: 300x200 pixel (teaser)


Use the application **gThumb** to

1. **crop** image to ratio, eg 3:1,1:1, 3:2, etc. and **accept**, than
2. **resize** to image width 1200, 800, 300, etc. and **accept** and
3. finally **save as** with appropiate **name extenstion** like  header, large,
small, teaser.

Than link the images `![Simon]({{"/assets/images/cat_simon_small.jpg"}})` in the
post with markdown syntax followed by image alignment instructions

* `{: .full}`
* `{: .align-left}`
* `{: .align-right}`

which results in
`![Simon]({{"/assets/images/cat_simon_small.jpg"}}){: .align-right}`

## Preview

To locally preview and check the changes start the **terminal Tilix**, do

    $ bundle exec jekyll serve

and than view in the browser at http://localhost:4000

## Deployment

For a general understanding of git and GitHub read [Hello World Guide][github].

First **sync the fork**

    $ git fetch upstream
    $ git checkout master
    $ git merge upstream/master

To **commit** start a second terminal tab and do

    $ git log            # see the last commits
    $ git status         # see the staging area
    $ git add .          # mark files to be commited
    $ git commit -m "create a blog post about live"

If you forgot something, or want to **change stuff in the last commit**, do

    $ git add .          # mark changed files to becommited
    $ git commit --amend # append changes to last commit

than **push to GitHub**, which also will **deploy** changes **to the server**:

    $ git push

A successful `git push` will trigger a GitHub webhook and deploy the static
site to [Netlify][netlify]. Than "it is live" and before promoting via email to
friends and family check the results at https://www.lolasview.com

# Help

For further help and advanced customisations read about

* [text format][kramdown]
* [alignment options][mmistakes-align]
* [image helpers][mmistakes-image]
* [layout variations][mmistakes-layout]

Check out the [Jekyll docs][jekyll-docs] for general info on how to use Jekyll.

# License

The following directories and their contents are copyright of
[L0laB](https://github.com/L0laB). You may not reuse anything therein without my
explicit permission:

* \_posts/
* assets/

Everything else is free software, and may be redistributed under the terms
specified in the [LICENSE](LICENSE) file.

[jekyll]:           https://jekyllrb.com
[jekyll-docs]:      https://jekyllrb.com/docs/home
[kramdown]:         https://kramdown.gettalong.org/quickref.html
[markup-post]:      https://mmistakes.github.io/minimal-mistakes/markup/markup-html-tags-and-formatting/
[markup-raw]:       https://raw.githubusercontent.com/mmistakes/minimal-mistakes/master/docs/_posts/2013-01-11-markup-html-tags-and-formatting.md
[mmistakes]:        https://mmistakes.github.io/minimal-mistakes/
[mmistakes-align]:  https://mmistakes.github.io/minimal-mistakes/docs/utility-classes/
[mmistakes-image]:  https://mmistakes.github.io/minimal-mistakes/docs/helpers/
[mmistakes-layout]: https://mmistakes.github.io/minimal-mistakes/docs/layout/
[netlify]:          https://www.netlify.com
[github]:           https://guides.github.com/activities/hello-world/
