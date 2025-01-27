---
layout: default
title: Preface
---

Preface
=======

This book explores several themes with the following goals in mind:

* To have knowledge of the structure of `ruby`
* To gain knowledge about language processing systems in general
* To acquire skills in reading source code

Ruby is an object-oriented language developed by Yukihiro Matsumoto. The
official implementation of the Ruby language is called `ruby`. It is actively
developed and maintained by the open source community. Our first goal is to
understand the inner-workings of the `ruby` implementation.  This book is going
to investigate `ruby` as a whole.

Secondly, by knowing about the implementation of Ruby, we will be able to know
about other language processing systems. I tried to cover all topics necessary
for implementing a language, such as hash table, scanner and parser, evaluation
procedure, and many others. Because this book is not intended as a text book,
going through entire areas and ideas without any lack was not reasonable.
However the parts relating to the essential structures of a language
implementation are adequately explained.
And a brief summary of Ruby language itself is also included
so that readers who don't know about Ruby can read this book.

The main themes of this book are the first and the second point above. Though,
what I want to emphasize the most is the third one: To acquire skill in reading
source code. I dare to say it's a "hidden" theme. I will explain why I thought
it is necessary.

It is often said "To be a skilled programmer, you should read source code
written by others." This is certainly true. But I haven't found a book that
explains how you can actually do it. There are many books that explain OS
kernels and the interior of language processing systems by showing the concrete
structure or "the answer," but they don't explain the way to reach that answer.
It's clearly one-sided.

Can you, perhaps, naturally read code just because you know how to write a
program? Is it true that reading codes is so easy that all people in this world
can read code written by others with no sweat? I don't think so.
Reading programs is certainly as difficult as writing programs.

Therefore, this book does not simply explain `ruby` as something already known,
rather demonstrate the analyzing process as graphic as possible.
Though I think I'm a reasonably seasoned Ruby programmer,
I did not fully understand the inner structure of `ruby` at the time when I
started to write this book.
In other words, regarding the content of `ruby`,
I started from the position as close as possible to readers.
This book is the summary of both the analyzing process started from that point
and its result.

I asked Yukihiro Matsumoto, the author of `ruby`, for supervision. But I
thought the spirit of this book would be lost if each analysis was monitored by
the author of the language himself. Therefore I limited his review to the final
stage of writing. In this way,
without loosing the sense of actually reading the source codes,
I think I could also assure the correctness of the contents.

To be honest, this book is not easy. In the very least, it is limited in its
simplicity by the inherent complexity of its aim. However, this complexity may
be what makes the book interesting to you. Do you find it interesting to be
chattering around a piece of cake?  Do you take to your desk to solve a puzzle
that you know the answer to in a heartbeat? How about a suspense novel whose
criminal you can guess halfway through? If you really want to come to new
knowledge, you need to solve a problem engaging all your capacities. This is
the book that lets you practice such idealism exhaustively.
"It's interesting because it's difficult." I'm glad if the number of people
who think so will increase because of this book.

Target audience
---------------

Firstly, knowledge about the Ruby language isn't required. However, since the
knowledge of the Ruby language is absolutely necessary to understand certain
explanations of its structure, supplementary explanations of the language are
inserted here and there.

Knowledge about the C language is required, to some extent. I assume you can
allocate some structs with `malloc()` at runtime to create a list or a stack
and you have experience of using function pointers at least a few times.

Also, since the basics of object-oriented programming will not be explained so
seriously, without having any experience of using at least one of
object-oriented languages, you will probably have a difficult time.
In this book, I tried to use many examples in Java and C++.

Structure of this book
----------------------

This book has four main parts:

* Part 1: Objects
* Part 2: Syntactic analysis
* Part 3: Evaluation
* Part 4: Peripheral around the evaluator

Supplementary chapters are included at the beginning of each part when
necessary. These provide a basic introduction for those who are not familiar
with Ruby and the general mechanism of a language processing system.

Now, we are going through the overview of the four main parts. The symbol in
parentheses after the explanation indicates the difficulty gauge. They are ==(C)==,
(B), (A) in order of easy to hard, (S) being the highest.

#### Part 1: Object

* Chapter1 — Focuses the basics of Ruby to get ready to accomplish Part 1. ==(C)==
* Chapter2 — Gives concrete inner structure of Ruby objects. ==(C)==
* Chapter3 — States about hash table. ==(C)==
* Chapter4 — Writes about Ruby class system. You may read through this chapter quickly at first, because it tells plenty of abstract stories. (A)
* Chapter5 — Shows the garbage collector which is responsible for generating and releasing objects. The first story in low-level series. (B)
* Chapter6 — Describes the implementation of global variables, class variables, and constants. ==(C)==
* Chapter7 — Outline of the security features of Ruby. ==(C)==

#### Part 2: Syntactic analysis

* Chapter8 — Talks about almost complete specification of the Ruby language, in order to prepare for Part 2 and Part 3. ==(C)==
* Chapter9 — Introduction to `yacc` required to read the syntax file at least. (B)
* Chapter10 — Look through the rules and physical structure of the parser. (A)
* Chapter11 — Explore around the peripherals of `lex_state`, which is the most difficult part of the parser. The most difficult part of this book. (S)
* Chapter12 — Finalization of Part 2 and connection to Part 3. ==(C)==

#### Part 3: Evaluator

* Chapter13 — Describe the basic mechanism of the evaluator. ==(C)==
* Chapter14 — Reads the evaluation stack that creates the main context of Ruby. (A)
* Chapter15 — Talks about search and initialization of methods. (B)
* Chapter16 — Defies the implementation of the iterator, the most characteristic feature of Ruby. (A)
* Chapter17 — Describe the implementation of the eval methods. (B)

#### Part 4: Peripheral around the evaluator

* Chapter18 — Run-time loading of libraries in C and Ruby. (B)
* Chapter19 — Describes the implementation of thread at the end of the core part. (A)

Environment
-----------

This book describes on `ruby` 1.7.3 2002-09-12 version. It's attached on the
CD-ROM. Choose any one of `ruby-rhg.tar.gz`, `ruby-rhg.lzh`, or `ruby-rhg.zip`
according to your convenience. Content is the same for all.  Alternatively you
can obtain from the support site (footnote{`http://i.loveruby.net/ja/rhg/`}) of
this book.

For the publication of this book, the following build environment was prepared
for confirmation of compiling and testing the basic operation. The details of
this build test are given in `doc/buildtest.html` in the attached CD-ROM.
However, it doesn't necessarily assume the probability of the execution even
under the same environment listed in the table. The author doesn't guarantee
in any form  the execution of `ruby`.

* BeOS 5 Personal Edition/i386
* Debian GNU/Linux potato/i386
* Debian GNU/Linux woody/i386
* Debian GNU/Linux sid/i386
* FreeBSD 4.4-RELEASE/Alpha (Requires the local patch for this book)
* FreeBSD 4.5-RELEASE/i386
* FreeBSD 4.5-RELEASE/PC98
* FreeBSD 5-CURRENT/i386
* HP-UX 10.20
* HP-UX 11.00 (32bit mode)
* HP-UX 11.11 (32bit mode)
* Mac OS X 10.2
* NetBSD 1.6F/i386
* OpenBSD 3.1
* Plamo Linux 2.0/i386
* Linux for PlayStation2 Release 1.0
* Redhat Linux 7.3/i386
* Solaris 2.6/Sparc
* Solaris 8/Sparc
* UX/4800
* Vine Linux 2.1.5
* Vine Linux 2.5
* VineSeed
* Windows 98SE (Cygwin, MinGW+Cygwin, MinGW+MSYS)
* Windows Me (Borland C++ Compiler 5.5, Cygwin, MinGW+Cygwin, MinGW+MSYS, Visual C++ 6)
* Windows NT 4.0 (Cygwin, MinGW+Cygwin)
* Windows 2000 (Borland C++ Compiler 5.5, Visual C++ 6, Visual C++.NET)
* Windows XP (Visual C++.NET, MinGW+Cygwin)

These numerous tests aren't of a lone effort by the author.  Those test build
couldn't be achieved without magnificent cooperations by the people listed
below.

I'd like to extend warmest thanks from my heart.

* Tietew
* kjana
* nyasu
* sakazuki
* Masahiro Sato
* Kenichi Tamura
* Morikyu
* Yuya Kato
* Takehiro Kubo
* Kentaro Goto
* Tomoyuki Shimomura
* Masaki Sukeda
* Koji Arai
* Kazuhiro Nishiyama
* Shinya Kawaji
* Tetsuya Watanabe
* Naokuni Fujimoto

However, the author owes the responsibility for this test. Please refrain from
attempting to contact these people directly.  If there's any flaw in execution,
please be advised to contact the author by e-mail: `aamine@loveruby.net`.

Web site
--------

The web site for this book is `http://i.loveruby.net/ja/rhg/`.
I will add information about related programs and additional documentation, as
well as errata. In addition, I'm going to publisize the first few chapters of
this book at the same time of the release. I will look for a certain
circumstance to publicize more chapters, and the whole contents of the book
will be at this website at the end.

Acknowledgment
--------------

First of all, I would like to thank Mr. Yukihiro Matsumoto. He is the author of
Ruby, and he made it in public as an open source software.  Not only he
willingly approved me to publish a book about analyzing `ruby`, but also he
agreed to supervise the content of it. In addition, he helped my stay in
Florida with simultaneous translation. There are plenty of things beyond
enumeration I have to say thanks to him. Instead of writing all the things, I
give this book to him.

Next, I would like to thank arton, who proposed me to publish this book. The
words of arton always moves me. One of the things I'm currently struggled due
to his words is that I have no reason I don't get a .NET machine.

Koji Arai, the 'captain' of documentation in the Ruby society, conducted a
scrutiny review as if he became the official editor of this book while I was
not told so. I thank all his review.

Also I'd like to mention those who gave me comments, pointed out mistakes and
submitted proposals about the construction of the book throughout all my work.

Tietew,<br />
Yuya,<br />
Kawaji,<br />
Gotoken,<br />
Tamura,<br />
Funaba,<br />
Morikyu,<br />
Ishizuka,<br />
Shimomura,<br />
Kubo,<br />
Sukeda,<br />
Nishiyama,<br />
Fujimoto,<br />
Yanagawa,<br />
(I'm sorry if there's any people missing),<br />
I thank all those people contributed.

As a final note, I thank Otsuka , Haruta, and Kanemitsu who you for arranging
everything despite my broke deadline as much as four times, and that the
manuscript exceeded 200 pages than originally planned.

I cannot expand the full list here to mention the name of all people
contributed to this book, but I say that I couldn't successfully publish this
book without such assistance. Let me take this place to express my
appreciation. Thank you very much.

p(right). Minero Aoki

If you want to send remarks, suggestions and reports of typographcal errors,
please address to [Minero Aoki &lt;aamine@loveruby.net&gt;](mailto:aamine@loveruby.net).

"Rubyソースコード完全解説" can be reserved/ordered at ImpressDirect.
[(Jump to the introduction page)](http://direct.ips.co.jp/directsys/go_x_TempChoice.cfm?sh_id=EE0040&spm_id=1&GM_ID=1721)

Copyright (c) 2002-2004 Minero Aoki, All rights reserved.
