---
layout: page
title: "Instructor's Guide"
permalink: /guide/
---

Make is a popular tool for automating the building of software -
compiling source code into executable programs.

Though Make is nearly 40 years old, and there are many other build
tools available, its fundamental concepts are common across build
tools.

Today, researchers working with legacy codes in C or FORTRAN, which
are very common in high-performance computing, will, very likely
encounter Make.

Researchers are also finding Make of use in implementing reproducible
research workflows, automating data analysis and visualization (using
Python or R) and combining tables and plots with text to produce
reports and papers for publication.

## Overall

The overall lesson can be done in a 2 hour slot.

Solutions for challenges are used in subsequent topics.

A number of example Makefiles, including sample solutions to
challenges, are in `code/samples` and are identified below.

## Setting up Make

Recommend instructors and students use `nano` as the text editor for
this lesson because

* it runs in all three major operating systems,
* it runs inside the shell (switching windows can be confusing to
  students), and
* it has shortcut help at the bottom of the window.

Please point out to students during setup that they can and should use
another text editor if they're already familiar with it.

Instructors and students should use two shell windows: one for running
nano, and one for running Make.

Check that all attendees have Make installed and that it runs
correctly, before beginning the session.

## Code and Data Files

Python scripts to be invoked by Make are in `code/`.

Data files are in `data/books`.

You can either create a simple Git repository for students to clone
which contains:

* `wordcount.py`
* `plotcount.py`
* `zipf_test.py`
* `books/`

Or, ask students to download
[make-lesson.zip][zipfile] from this repository.

To recreate `make-lesson.zip`, run:

~~~
$ make make-lesson.zip
~~~
{: .bash}

## Beware of Spaces!

The single most commonly occurring problem will be students using
spaces instead of TABs when intending actions.

## Makefile Dependency Images

Some of these pages use images of Makefile dependencies, in the `fig` directory.

These are created using [makefile2graph][makefile2graph],
which is assumed to be in the `PATH`.
This tool, in turn, needs the `dot` tool, part of [GraphViz][graphviz].

To install GraphViz on Scientific Linux 6:

~~~
$ sudo yum install graphviz
$ dot -V
~~~
{: .bash}
~~~
dot - graphviz version 2.26.0 (20091210.2329)
~~~
{: .output}

To install GraphViz on Ubuntu 14.04.3 and 15.10:

~~~
$ sudo apt-get install graphviz
$ dot -V
~~~
{: .bash}
~~~
dot - graphviz version 2.38.0 (20140413.2041)
~~~
{: .output}

To download and build makefile2graph on Linux:

~~~
$ cd
$ git clone https://github.com/lindenb/makefile2graph
$ cd makefile2graph/
$ make
$ export PATH=~/makefile2graph/:$PATH
$ cd
$ which makefile2graph
~~~
{: .bash}
~~~
/home/ubuntu/makefile2graph/makefile2graph
~~~
{: .output}

To create the image files for the lesson:

~~~
$ make figures
~~~
{: .bash}

See `commands.mk`'s `diagrams` target.

[graphviz]: http://www.graphviz.org/
[lesson-example]: https://github.com/swcarpentry/lesson-example/
[makefile2graph]: https://github.com/lindenb/makefile2graph
[zipfile]: {{ site.github.url }}/files/make-lesson.zip
