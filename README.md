Template Confusion
=========


Many beginners are searching for a good template to help them
start using LaTeX. But the internet is a strange place and a lot
of stuff is going on. 

There are many templates around, many different templates for
different use cases. The word template can't even be pinned to
one special meaning, there are lots of instances that are called
*a template*.  


Everyday, LaTeX helpers all over the world get questions based on
a bad template. Bad in this case means unmaintained, no license
statement, obsolete packages and practices, in parts even
completely wrong input that leads to warnings from the very
beginning. 

As we can't get in touch with every maintainer of a web-page
providing template-like stuff, does that mean the helpers should
team up and start provide templates themselves? Team-maintained
and up to date? Sean Allread started a [github repository called
*texample*](https://github.com/vermiculus/texample) a while back
with the idea of providing templates, or rather examples.

Clemens Niederberger expressed some thoughts on templates in [The
Template
Story](http://www.mychemistry.eu/2015/07/the-template-story/) and
[pinged](https://twitter.com/LaTeX_Chemistry/status/619135236560039937)
services like [Overleaf](http://overleaf.com/) and [LaTeX
Templates](http://www.latextemplates.com/) for opinions. 

[Dmitry from
Papeeria](http://www.mychemistry.eu/2015/07/the-template-story/#comment-870)
said "Many templates are quick and dirty hacks, but very often
they don’t need to be polished, because they are just fine for
their job." If i understand him correctly, he is talking about
documentclasses there.

[Vel from LaTeX templates]() on the other hands states his
motives for setting up the web page: Getting new users started by
providing easy usable commented tex-files where the user can
input his/her own content. Every template is commented, *i.e.* a
short note what a package does and why it is loaded.

The last [comment by
Clemens](http://www.mychemistry.eu/2015/07/the-template-story/#comment-888)
is the following:

>It came to me that this discussion seems to miss one thing:
 there are templates on CTAN like classicthesis, tufte-book or
 even my cnltx-doc. Seems like a natural place: a genuine LaTeX
 template is a document class. In a way every document class is a
 LaTeX template. Maybe what we are talking about are not so much
 templates but examples for LaTeX usage…

It seems, there are two general categories of templates.


Fixed Output
-------

LaTeX classes and packages have a special license, most important
to keep names unique. There are multiple university thesis
packages on CTAN, each setting up a titlepage (hopefully using
variables), setting the page layout in general, i.e.  margins,
fonts, chapter/section headings. The layout is fixed. 


`classicthesis` sets very specific design ideas. The author
explains those ideas, what they are based on and asks the user
not to change the margins. In my experience, changing the margins
is quite the first thing a `classicthesis`-user is changing. So
...  no fixed output.  `classicthesis` (the package) is licensed (good thing)
and every change to the original code has to be done by
redefining or patching, which i think is quite scary and
outputting for a new user. I think my point here is: Actually
using a template might be easy, customizing it for own needs can
be harder comparing to not using a template.

One more thing to consider are package incompatibilities. If some
package like `subfigure` or `hyperref` are loaded early in a
class file, trouble is to be expected. 

Those fixed templates usually come with own documentation and how
to use it. Additionally introducing new commands if necessary.

One of those fixed templates is the [Thesis Template by Sunil
Patel](http://www.sunilpatel.co.uk/thesis-template/) which i
think we all are familiar with to some extend. .From the FAQ
section of the web site 

> Why do I need to use this LaTeX Thesis Template?

>It is not compulsory to use the LaTeX Thesis Template or any
other LaTeX template, but here is one, ready, tested and
documented for you to use. It is a template and structured
framework and written to keep you organised and let you start
writing your thesis straight away without spending time worrying
about the formatting and layout.

>Of course, you can do all of this yourself manually, but why
re-invent the wheel?

Non-fixed Output
--------------

No design decisions are hidden in a class or package file, maybe
put in a file called `config.tex` or `structure.tex`. The user
sees the whole bunch of stuff, comments behind. There might be
packages loaded to suit almost all users. Three for table stuff,
`tikz` for TikZ, `pgfplots` for diagrams, additional loading of
package `color`, 4 different packages that set the font of the
document, and finally package `xcolor` with some option. To top
it off, several independent blocks of redefining internal
commands using the `\makeatletter`/`\makeatother` combo
Actually, that was made up, but that doesn't mean there is a
template out there doing this. 

Merely a small fraction here would be actually useful for a
beginner. And that wall of code is scary once more. 


----

Either fixed or non-fixed layout, a template seems to be a
prepacked bunch of files (at least one), something like a black
box for a starter, you cannot judge what's inside.

*A LaTeX template is like a box of chocolates - you never know
what you're gonna get.*



Does the life of a template end? 
-------------

When does a template stop being a template? Consider the most
minimal template you can think of:

    % report template
    \documentclass{report}
    \begin{document}
    This is a very basic setup for writing a report, for example a
    PhD thesis.
    \end{document}

I can use that basic template and i can make
changes, for example define new commands and i can even do this:

    % report template
    \documentclass{report}
    \begin{document}
    This is a very basic setup for writing a report, for example a
    PhD thesis. Use \texttt{\textbackslash\textbackslash} to get a new paragraph.\\\\%Nonsense
    New paragraph
    \end{document}

Sadly, the internet is full of that non-truth and i could
distribute that by uploading it to a prominent place and give it
to friends. A newcomer looking for a template to get started
sees it and believes that to be true. Every template is correct,
right?  
Is the above a template, or rather a (bad) example. Should i (the
user working based on the initial template) remove the comment
line before starting to work? 



Best before end?
---------------


LaTeX moves on every day. Does code have a *best before end* life
span? What happens to unmaintained code? How can a community
assure that code is up to date?


-----

As part of one of the best communities of the world `;-)` i think
we can work together to establish some common standards of *best
practice* (What does that even mean?) to improve the initial
state of future templates and improve the current situation. 

What do you think? It this  worth the effort and something cane
be done? Can the questions above be answered? Are there more
questions concerning templates? The good news is, we have the
guys from [ShareLaTeX](https://www.sharelatex.com/),
[Overleaf](https://www.overleaf.com/) and [LaTeX
Templates](http://www.latextemplates.com/) on board willing to
make improvements. Those improvements will (hopefully) improve
the overall image, accessibility and user experience.
