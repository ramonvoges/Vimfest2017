---
title: "Neovim – The Historians Best Friend"
date: 2017-09-23
---

First of all, I would like to thank Matthias for accepting my proposal and giving me the possibility to talk to you all!

I am not a developer or computer scientist, but an historian by profession, teaching at Paderborn University Early Modern History. And this is the first time I take part in a hackathon. With my talk I hope I can show that, although it is, as far as a I know, quite unusual for scholars of the humanities to attend a hackathon, this does not need to be the case.

In order to explain why an historian of the Early Modern Times considers himself a great fan of Vim and Neovim, I will start with a short survey of how I ended up with that awesome piece of software.
In a next step, I will describe some of Neovim's features I find most useful.
After that I will give a concise overview of plugins I rely on during my day to day work.
Finally, I will end with a short conclusion why advocates of the humanities should use Vim and Neovim as well.


# My Journey to Vim

The vast majority of students of the humanities start writing their essays with word processors. In university, the lecturers are thrilled when their students master the basic functions and workflows of Microsoft Word or LibreOffice. So I was quite satisfied, too, when I managed to let Word create a Table of Contents for my essays.

This changed dramatically the moment I began to do some research on Early Modern pictures and tried to integrate them into my papers. After many hours of wasting time and nerve-racking, I resolved to look for something better. I found the solution to all the annoyances in LaTeX. But what I missed was a good editor to write my LaTeX files.

As the author of a guide on how to use LaTeX recommend Emacs as the most versatile LaTeX editor – and, of course, I wanted the most powerful editor, I began not only to learn LaTeX but also how to use Emacs. I must admit, everything was fine for a while. True, Emacs was not easy to configure and it took some time until the editor was up and running. However, it was ok for me.

But then, one day, without warning, my config broke! I hadn't changed a thing, but out of nowhere Emacs refused to start and just showed me cryptic error messages. Since I had, by that time, to write my PhD thesis, I looked for quick and dirty alternative. I was quite happy finding that Textmate had just became open source, so I switched to that editor. And again, I was quite contended.

After some time, a good friend pointed me to Sublime and I suddenly realised how Textmate had fallen behind. As I didn't wanted to use a commercial product I switched to Atom. In comparison with Textmate it was slow and an awful mess with all its different plugins and inconsistent settings. After one of Atom's crushes had devoured a day's work of writing, I, again, looked for something better.

In of the blog posts I read, the author recommended to use Atom, but with a plugin that emulates Vim. So I began to wonder what everybody was so exciting about when they wrote about Vim's different modes and how this revolutionized how they edited text.


# Vim as a DSL

It took quite a while before I dared to install MacVim. And I must confess, the first impression was not inspiring a lot of confidence, since it was obvious that I needed to configure quite a lot before I could use Vim the way I wanted to. From my experience with Emacs I was well acquainted with that.

What really stroke me and induced me to invest again time and nerves was the way how Vim differentiates between the modes of dealing with text. For me, this was, of course, absolutely not intuitively. But I realized how effective one could be once mastered. But, instead of carrying owls to Athens, I will give you a short survey of Vim specific mappings I fell in love with:

* `.`: 'the dot formula', to repeat the last change
* `ciw`: to quickly change a word in a sequences
* `daw`: one of the sequences I use most often
* `das`: to delete a whole sentence
* `(` or `)`: to quickly navigate from sentence to sentence
* `{` or `}`: to quickly jump from paragraph to paragraph
* `ci(`: to change inner brackets

In short, I was amazed that Vim actually offers a *Domain Specific Language* for dealing with text.

# Plugins

# Conclusion
