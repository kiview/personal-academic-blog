---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Java  for Education (and Beyond)"
subtitle: ""
summary: ""
authors: ["admin"]
tags: ["java", "education"]
categories: ["kevin-blog"]
date: 2020-08-03T08:39:31+02:00
lastmod: 2020-08-03T08:39:31+02:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

The nucleus for this post was an email to Ken Fogel (the famous [@omniprof](https://twitter.com/omniprof) on Twitter) I wrote after a discussion we had on Twitter about the educational and pedagogical qualities of programming languages.
We [quite](https://twitter.com/Kiview/status/1282335981031612416) [often](https://twitter.com/Kiview/status/1248751688657371136) [disagree](https://twitter.com/Kiview/status/1282781682979012609) on certain topics, but I assume his opinions have aged like a fine wine by many years of experience as a computer science professor. 
While I would say that often we don’t leave a discussion on common ground, I nevertheless leave with a more reflected understanding afterward (and there are even the rare occasions, where we agree on [something](https://twitter.com/Kiview/status/1289603680497356801)). 
In addition, I am very happy to see the creation of the [Java in Education Working Group](https://community.oracle.com/community/groundbreakers/java/jcp/executive-committee/java-in-education-working-group) and I appreciate everyone involved for their contributions to the community.

What follows are some more or less unstructured ramblings about using Java for education, which I had in my mind for quite some time. Maybe some of those things are useful to spur further discussion and I'm quite interested in which direction the education working group might lead Java.

## The Soaring Heights of Higher Education

> Universities are truly storehouses for knowledge: students arrive from school confident they know nearly everything, and they leave five years later certain that they know practically nothing. Where did the knowledge go in the meantime? In the university, of course, where it is dried and stored. ― Terry Pratchett

So, first of all, I want to add, that Java was the main language at my [university](https://www.en.w-hs.de/) back then (I was studying computer science) and therefore it was extensively used in all kind of different courses. 
I think this approach to a coordinated curriculum generally works well and I was not unhappy with it back then. 
That said, I now also discovered with some of the students starting out in [my research group](https://bl.internet-sicherheit.de/), that they see themselves as Java programmers, not as programmers or software developers in general. 
I think this a very bad way to think about your skills and they need to be aware, that their skills have to be transferable (and they generally are, they are just afraid and not yet aware of it). 
Therefore being confronted with different languages during your studies might help you in developing a bigger picture.
In general, I feel the current form of Java works reasonably well for teaching Java as the first programming language for computer science students. 
So I don't see big problems in this regard, especially if learned in conjunction with a language closer to the metal (we had one course in C) and another focusing on FP (we had Haskell, which I absolutely loved).
However, we have a completely different situation when looking at Java as the first programming language for school students and for people jumping into programming from outside the IT industry (here I am thinking about scientists, data science, analysts, etc.). 
In this case, Java does a non-ideal job and generally loses to Python on multiple levels. 
What follows are some reasons which I assume play a role to a certain extent

## Setting up a Working Environment

Not easy to get started. You have to normally install an IDE and JDK to use Java in a useful way and an IDE is really a big beast for a beginner. 
Yes, we have [Java in Visual Studio Code](https://code.visualstudio.com/docs/languages/java) and it works reasonably well, but in my opinion, Java just soars when used in a powerful IDE and every other approach feels subpar. 
With Python, you have really good only editors and, most importantly, [Jupyter Notebooks](https://jupyter.org/), which are the real game-changer. 
Also with [Anaconda](https://www.anaconda.com/) as a single distribution, it is super easy to get a working slightly professional Python environment for data science installed, directly including local Jupyter server and other widely used software packages. 
And while I think Anaconda is not a great distribution from a software developer standpoint (and [pipenv](https://github.com/pypa/pipenv) works much better for dependency management), but for newcomers, it mostly just works, fits the ecosystem of existing learning materials and handles native dependencies reasonably well, even on Windows. 
I think [repl.it](https://repl.it/) with Java support is a somewhat nicer starting point, but it is pretty slow for Java, so not super fun.

## Learning to Code

With Python, you have zero ceremonies to get started. 
Just write a script, print “Hello World”, that's it. 

```python
print("Hello World")
```

In Java you need to have a class with a main method, printing has a complicated signature involving the System package, etc..
I know it feels stupid to compare languages based on their "Hello World" abilities, but this is a high conceptual hurdle. 
When we started with Java at university, our professor just told us to ignore this ceremony in the beginning and start writing things in the body of the main method. 
This solves it for students, but it is a less than ideal approach for general beginners, curious in learning programming. [JEP 330](https://openjdk.java.net/jeps/330) for launching single-file source-code programs seems like a step in the right direction though. 
However, [Apache Groovy](https://groovy-lang.org/) can actually help with this problem even better and ticks most of the boxes in this regard. 

## Generating  Value

How quickly can you get real usable results, that help you with the task you are trying to achieve? 
Python has such strong (industry standard) data science libraries, with regards to analyzing as well as plotting data (such as [NumPy](https://numpy.org/), [pandas](https://pandas.pydata.org/) and [matplotlib](https://matplotlib.org/)), it is very hard to catch up here. 
And people can use some code from a blog post and quickly adapt it to their use case, without having a full understanding of programming and Python, and they get real results they can use at work. 
This is how my [wife](/home-nesli/) got into Python by the way and it is an excellent way to start programming as a scientist. 
Also, those libraries behave kind of similar (similarly strange I'd like to add) to R and MATLAB in certain ways and most scientists already have some familiarity with those. 
Again, this is something where Groovy can potentially help and where we might be able to carve out a great niche for Groovy (and I am very excited what [Paul King](https://twitter.com/paulk_asert) and the other maintainers might be cooking up in the future).

## Consequences?

So where does this leave us?
I am not the one to dish out recommendations for the folks involved with developing the Java language.
This is a hard topic and I my opinion, there is a certain area of conflict involved in making a language accessible to beginners and powerful for experts, 
especially when considering the evolvement of the language with backward compatibility in mind.
The Java community simply should be careful to not develop tunnel vision and stay aware of surrounding developments and dynamics. 
Additionally, if we take mentoring and teaching seriously, we also need to admit that forcing Java down the throat of every potential student (meaning student as a abstract concept in the widest way possible) and bolting it on every use case is no way to behave.
What I have personally learned in the last month I got more involved with Python is a very obvious concept: 

It's better to embrace another language and its ecosystem for its qualities instead of complaining about what it is not.
This is not only more effective in the long run, but also much more fun and I'd like to think it makes us become better persons as well 😇.