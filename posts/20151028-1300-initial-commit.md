Initial Commit
@tags: python
@date: 28-10-2015 13.00

Well every programmer and their has a blog now o I guess it is about high time I got on the bandwagon. I'm sure people will want to know exactly what I think about the latest developments in getting assembly in your JavaScript in your thing.

After looking into GitHub's Jekyll thing and a bunch of other static site generators, I wrote [my own thing][blarg]. Why did I bother? Because I honestly felt it would be a fun, simple little project. As an efficient programmer it felt wrong not using some pre-existing tool but as a regular programmer it felt wrong _not_ to. It isn't beautiful code but it does the trick. Hey, that's Python!

> ...there is no point writing code more than once since it is just a waste of time and gets pretty boring.

## README

In the interests of filling space, and in case I ever get amnesia I'm going to explain how it works. Put blarg next to 4 folders:

    posts/ pages/ static/ templates/

Posts and pages contain your content. Static is where you put any other stuff. CSS and SCSS files in this directory will be compiled and merged. Templates are in Jinja format.

Posts or pages can be .md if you like Markdown. Everything is spewed into a directory, accidentally creating an archive and tags page on the way. It's all boring, static HTML. All the way down.

Usage? Sure:

    :::bash
    blarg [--out OUT] [--editor EDITOR] {new, render, push}

OUT is where the compiled files will end up. EDITOR is the editor to launch for new posts.

Actions: new - write a new post, render - compile everything, push - commit and push the output directory (I'm assuming it will be a git repo.)

[blarg]: https://github.com/vixus0/blarg "blarg on github"
