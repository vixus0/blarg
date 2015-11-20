Initial Commit
@tags: python
@date: 28-10-2015 13.00

Well every programmer and their gran has a blog now so I guess it is about high time I got on the bandwagon. I'm sure people will want to know exactly what I think about the latest developments in getting assembly in your JavaScript in your thing.

I looked into using other static site generators before rolling my own, as every good dev does. They're all great, really great. But you know sometimes you get that odd feeling when you're in an entirely strange place where you don't speak the language and you're not quite sure how anything works? Not like you're in danger or anything, just that you want to have a little bit of familiarity so you go and buy pizza or a beer or something because pizza and beer tends to be similar in most places. Anyway so I wrote [my own thing][blarg]. It is _not_ beautiful code but it does the trick (hey, that's Python!)

## README

In the interests of filling space, and in case I ever get amnesia I'm going to explain how it works. Put blarg next to 4 folders:

    posts/ pages/ static/ templates/

Posts and pages contain your content. Static is where you put any other stuff. CSS and SCSS files in this directory will be compiled and merged. Templates are in Jinja format.

Posts or pages can be .md if you like Markdown. Everything is spewed into a directory, accidentally creating an archive and tags page on the way. It's all boring, static HTML. All the way down.

Usage? Sure:

    :::bash
    blarg [--out OUT] [--editor EDITOR] {new, render, push}

OUT is where the compiled files will end up. EDITOR is the editor to launch for new posts.

Actions: new - write a new post, render - compile everything, push - commit and push the output directory (I'm assuming it will be a repo.)

[blarg]: https://github.com/vixus0/blarg "blarg on github"
