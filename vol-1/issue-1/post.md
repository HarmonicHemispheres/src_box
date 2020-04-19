
![banner](i1-banner.png)

<h1 align="center">
Blogging with Github
</h1>
<h5 align="center">
Author: <i>Robby Boney</i>  |
Vol: 1 |
Iss: 1
</h5>
<br>


`Git Based Blogging` is an idea thats been brewing in the back of my mind for awhile now. In this post I want to discuss what is beneficial about this approach and how this repository is configured to execute this paradigm of blogging.


<br>

## Benefits of using Git

[Git](https://git-scm.com/) along with [Github](https://github.com/) provide some really intriguing features that appeal to scientific and technical blogging. It's version control focus is ideal for _Continuous Content_ and _Repeatable Behavior_ which are the two primary benefits of using this blogging format. 

<br>

__Continuous Content__ can be defined as:

> __Continuous Content__: _written content that is continuously updated rather than archived and replaced once it is stale_

This type of content is inspired from concepts in DevOp's of Continuous Integration and Continuous Deployment. This is a very useful attribute for written technical content because most fields evolve so fast. Simply read through the [Nature Journal](https://www.nature.com/) or the [Rust Lang's Changelog](https://github.com/rust-lang/rust/blob/master/RELEASES.md) and you will find miles of programmers inventing better algorithms and brilliant researchers discovering more efficient technologies. In this day and age staying updated is hard because the cutting edge moves so fast and reading an article hoping it will be updated "enough" is a inefficiency. The fact that `git` is a version control software with a rich feature set, means old content can be updated and older versions are still accessible. This blog seeks to take advantage of that by keeping content "updated". New or additional content, wont be thrown into a new post, but will be tagged onto an existing post if applicable, creating a new version.

<br>

__Repeatable Behavior__ can be defined as:

> __Repeatable Behavior__: a behavior achieved by a 'describer' which can be repeated by a 'describee' using the 'describer's methods

Often times when reading articles online with example code or other procedures the reader will attempt to copy/paste the example into their own environment in the hopes of achieving the same result described in the blog post or article. This commonly results in errors and bugs related to system, environment, or code copied out of order. Projects like [Docker](https://www.docker.com/) and [Jupyter Notebooks](https://jupyter.org/) help solve this issue in different ways, but an a great benefit of using Github for blogging is that all the code used in the post (for example a jupyter notebook blog post) is already assembled in the repo to be run. And additionally Github displays Jupyter Notebooks by default making them good for reading on the site as well as running locally when a reader clones the repo.

Git Blogging is probably suited better for scientific, technical and philosophical blogs but also benefits from being easy to configure, since [github](https://github.com/) (and other git clients) support features like issues, wiki's, subscription to repositories and/or issues, and native rendering support for markdown and jupyter notebooks. Features like this are very handy because they could require setup in other blogging formats.



<br>
<br>

## Configuration
This repo attempts to repurpose some of Github's features to appeal to a blogging format and hopefully provide an interesting case study on experimental uses for `git` and `Github`.

<br>

### __Volumes, Issues & the Issue board__
Each blog post represents a new topic or idea for the blog. These posts are contained into `volumes` which are numbered by year and called `issues`; similar to scientific journals. The reasoning for `volume` and `issue` is to draw familiarity for expected readers of this blog's technical topics.

Each Issue corresponds with an issue on Github's issue board to provide a place for readers to comment as well as subscribe in case any changes to that issue occur. Issues uses the `BlogPost` label (mentioned below) and the `Topic::<___>` labels to describe itself on the issue board.

<br>

### __Structure__
The blog is layed with each `volume` contained in its own folder with all its `issues`. All example code and post specific content is located in that issue's folder. Using this structure and Github's markdown format, the repo is setup to let readers navigate from the readme to any blog post without having to navigate the files and folders.

```
readme.md
vol-1/
    overview.md            - describes the volume and gives links to issues
    issue-1/
        post.md            -+---- the post.? is the primary post file
    issue-2/                |
        post.ipynb         -+
        pyexample.py       - an example script
```

<br>

### __Labels__
Github labels are used to help categorize issues as well as provide methods for readers to filter the issue board better.

* `BlogChannel` - is used exclusively on issues designed to be "topic feeds" which will continuously be updated when new posts are added to it. Comments are disabled on these issues and provide readers a way to subscribe to only certain types of content in the blog.
* `BlogPost` - used for issues that represent a blog post
*  `bug, improvement, question` - these are reader labels, meant to signify a type of forum discussion related to the blog
* `topic::[____]` - these are for posts and channels to give readers more filtering power from the issue board filter search

<br>

### __Branches__
Branches are a great tool for keeping "official code" separate from "in progress" code. For this blog, `master` branch is dedicated to the official blog content (standard git process) and any new post ideas in the works are developed on separate branches following the naming convention below (adapted from [Git flow process](https://datasift.github.io/gitflow/IntroducingGitFlow.html)). This first blog post is the only exception to this rule. Using branches this way allows eager readers to see content in the works as well provides a clean `git log` for official posts on `master`

<br>

_New blog post ideas that have not been published use the __branch__ naming:_
```
format:     idea-[topic or name]
example:    idea-odd_python_funcs
```

_Published issues are __tagged__ with the naming:_
```
format:     v[volume number]i[issue number].[issue version]
example:    v3i23.1
```

### __Releases__
Releases represent a snapshot of a project at a `Good Stopping Point`. Where issues in this repo will most likely stay open to allow for `Continuous Content`, releases will be a subscribable feed of new posts & post versions.

<br>
<br>

# Conclusion
Hopefully this post has outlined an interesting new take on blogging and providing some adaptions to the Github feature-set that can help achieve _Continuous Content_ and _Repeatable Behavior_ from content in this blog.

As described above, this is living content, so feel free to make suggestions!
See you again soon.

~ Robby