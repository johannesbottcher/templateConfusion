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
completely wrong input that leads to warnings or errors from the
very beginning. Most of the templates have something in common:
they want somebody else to save some time, time that they
invested in the past while googling for problems they had
themselves. Bad code and bad practices are distributed that way,
from one generation to the next.

As we can't get in touch with every maintainer of a web-page
providing template-like stuff, does that mean the helpers should
team up and start provide templates themselves? Team-maintained
and up to date? Sean Allred started a [github repository called
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
document classes there.

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
fonts, chapter/section headings. The layout is fixed and hidden
to keep the end-user from changing anything.


`classicthesis` sets very specific design ideas. The author
explains those ideas, what they are based on and asks the user
not to change the margins. In my experience, changing the margins
is quite the first thing a `classicthesis`-user is changing. So
...  no fixed output at all.  `classicthesis` (the package) is licensed (good thing)
and every change to the original code has to be done by
redefining or patching, which i think is quite scary and
outputting for a new user. I think my point here is: Actually
using a template might be easy, customizing it for own needs can
be harder comparing to not using a template.

One more thing to consider are package incompatibilities. If some
package like `subfigure` or `hyperref` are loaded early in a
class file, trouble is to be expected. 

Those fixed templates usually come with own documentation on how
to use it. Additionally introducing new commands if necessary.

One of those fixed templates is the [Thesis Template by Sunil
Patel](http://www.sunilpatel.co.uk/thesis-template/) which i
think we all are familiar with to some extend. From the FAQ
section of the web site 

> Why do I need to use this LaTeX Thesis Template?

>It is not compulsory to use the LaTeX Thesis Template or any
other LaTeX template, but here is one, ready, tested and
documented for you to use. It is a template and structured
framework and written to keep you organized and let you start
writing your thesis straight away without spending time worrying
about the formatting and layout.

>Of course, you can do all of this yourself manually, but why
re-invent the wheel?


That very template made it to [LaTeX
Templates](http://www.latextemplates.com/template/masters-doctoral-thesis)
as well and is the most used of the three thesis templates
available. Later, some modifications were made to [our famous
thesis template](ourFamousThesisTemplate). Somehow, it isn't that
fixed anymore.




Non-fixed Output
--------------

No layout decisions are hidden in a class or package file, maybe
put in a file called `config.tex` or `structure.tex`. The user
sees the whole bunch of stuff, comments behind. There might be
packages loaded to suit almost all users. Three for table stuff,
`tikz` for TikZ, `pgfplots` for diagrams, additional loading of
package `color`, 4 different packages that set the font of the
document, and finally package `xcolor` with some option. To top
it off, several independent blocks of redefining internal
commands using the `\makeatletter`/`\makeatother` combo
Actually, that was made up, but that doesn't mean there is no
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
----------------


LaTeX moves on every day. Does code have a *best before end* life
span? What happens to unmaintained code? How can a community
assure that code is up to date?

Who supports a template? Who mountains it?
-------------------------------------------

Overleaf and ShareLaTeX have a little comments section, where
some support is done. Many users drop in to
[TeX.Stackexchange](http://tex.stackexchange.com/). The support
for LaTeX-templates is done in collaboration with
[LaTeX-community](http://latex-community.org/forum/), though not
everybody finds the right button and many users seek help at
TeX.SX. Some *templates* do development and support on gitHub,
some may know
[cleanthesis](https://github.com/derric/cleanthesis/). A few
thoughts about maintainership and support (as long with license
issues) can be found in [the Deedy Das CV template
example](exampleDeedyResume.md).


-----

As part of one of the best communities of the world `;-)` i think
we can work together to establish some common standards of *best
practice* (What does that even mean?) to improve the initial
state of future templates and improve the current situation. 

What do you think? It this  worth the effort and something can
be done? Can the questions above be answered? Are there more
questions concerning templates? What is a template? Can a
template have a license, should a template have a license? What
effect does a license have to the user? 

The good news is, we have the guys from
[ShareLaTeX](https://www.sharelatex.com/),
[Overleaf](https://www.overleaf.com/) and [LaTeX
Templates](http://www.latextemplates.com/) on board willing to
make at least some improvements. Those improvements will
(hopefully) improve the overall image, accessibility and user
experience of LaTeX.  Thousands of people are using the online
compilers and LaTeX Templates gets about 5000 visitors each day
as well. Looking at those digits there really is a quite high
interest from the user side to use LaTeX for their typesetting
and publication needs.
