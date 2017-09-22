---
title: "Neovim – The Historian's Best Friend"
date: 2017-09-23
author: Ramon Voges
---

First of all, I would like to thank Matthias for accepting my proposal and giving me the possibility to talk to all of you today!

My name is Ramon Voges. I am not a developer or computer scientist, but a historian by profession, teaching Early Modern History at Paderborn University. And this is the first time I take part in a hackathon. With my talk I hope I can show that, although it is, as far as a I know, quite unusual for scholars of the humanities to attend a hackathon, this does not need to be so.

In order to explain why a historian of the Early Modern Times considers himself a great fan of Vim and Neovim, I will start with a short survey of how I ended up with that awesome piece of software.
In a next step, I will describe some of Neovim's features I find most useful.
After that I will give a concise overview of plug-ins I rely on during my day to day work.
Finally, I will end with a short conclusion why advocates of the humanities should use Vim and Neovim as well.


# My Journey to Vim

The vast majority of students of the humanities start writing their essays with word processors. In university, the lecturers are thrilled when their students master the basic features and workflows of Microsoft Word or LibreOffice. So I was quite satisfied, too, when I managed to let Word create a Table of Contents for my essays.

This changed dramatically the moment I began to do some research on Early Modern visual prints and tried to integrate them into my papers. After many nerve-racking hours of wasting time, I resolved to look for something better. I found the solution to all the annoyances of Word and its clones in LaTeX. But what I missed was a good editor to write my LaTeX files.

First I began with – horribile dictu – Emacs. I must admit, everything was fine for a while. True, Emacs was not easy to configure and it took some time until the editor was up and running. However, it worked for me.

But then, one day, without warning, my configuration broke! I hadn't changed a thing, but out of nowhere Emacs refused to start and just showed me cryptic error messages. Since I had, by that time, to write my PhD thesis, I looked for a quick and dirty alternative. I was quite happy finding that Textmate had just become open source, so I switched to that editor. And again, I was quite contended.

After some time, a good friend pointed me to Sublime and I suddenly realised how Textmate had fallen behind. As I didn't want to use a commercial product I switched to Atom. In comparison with Textmate it was slow and an awful mess with all its different plug-ins and inconsistent settings. So after Atom had crushed and devoured a day's work of writing, I, again, looked for something better.

In one of the many blog posts I read, one author recommended to enhance Atom with a plug-in that emulates Vim. So I began to wonder what everybody was so excited about when they wrote about Vim's different modes and how this revolutionized how they edited text.


# Vim as a DSL

It took quite a while before I dared to install MacVim. And I must confess, the first impression was not inspiring a lot of confidence, since it was obvious that I needed to configure quite a lot before I could use Vim the way I wanted to. From my experience with Emacs I was well acquainted with that.

However, what really struck me and made me invest again time and nerves was the way how Vim differentiates between the modes of dealing with text. For me, this was, of course, absolutely not intuitive. But I realized how effective one could be once fully understood and mastered. Instead of carrying owls to Athens, I will give you a short survey of Vim specific mappings I fell in love with:

* `(` or `)`: to quickly navigate from sentence to sentence
* `{` or `}`: to quickly jump from paragraph to paragraph
* `ciw`: to quickly change a word in a sentence
* `daw`: one of the sequences I use most often
* `das`: to delete a whole sentence
* `ci(`: to change the words within the brackets
* `.`: 'the dot formula', to repeat the last change

Besides these movements and commands and their combinations I use, during my writing, also some of the mappings concerned with spelling:

* `]s`: to go to the next misspelled word
* `[s`: to go to the previous misspelled word
* `zg`: to mark a word as correct (or good)
* `zw`: to mark a word as wrong
* `z=`: to suggest correct words

In short, I was amazed that Vim actually offers a *Domain Specific Language* for dealing with text.

But, again, this is nothing new to you. So I will continue by talking over some of the plug-ins I find most useful in everyday work.

# Plugins

## LaTeX

I would like to start my short survey with LaTeX, since this software originally introduced me to real editors.

Since I switched to Neovim I use `vimtex`, a lightwight and comprehensive plug-in for most of the things you would like to do with your LaTeX files. I like especially the way it can open a Table of Contents and compile your file in the background. These are my settings:

``` vimscript
let g:tex_flavor = 'latex'
map <leader>lt :VimtexTocOpen<CR>
map <leader>lc :VimtexCompile<CR>
map <leader>lv :VimtexView<CR>
map <leader>ls :VimtexStop<CR>
let g:vimtex_compiler_latexmk = {
\ 'backend' : 'nvim',
\ 'background' : 1,
\ 'build_dir' : '',
\ 'callback' : 1,
\ 'continuous' : 1,
\ 'executable' : 'latexmk',
\ 'options' : [
\   '-pdf',
\   '-verbose',
\   '-file-line-error',
\   '-synctex=1',
\   '-interaction=nonstopmode',
\ ],
\}
```

## Pandoc

Apart from dealing with pure LaTeX files, I write a lot in Markdown. I do so because it is easy to write in, you can use `git` for your Markdown files and you can transfer your content to many other formats. For this purpose I turn to Pandoc. And, of course, there is a great Pandoc plug-in for Vim and Neovim. It works for me right out of the box and has a very concise syntax. You just start a transformation by `:Pandoc <output format> [options]`.


## Vimwiki

Closely related to Markdown and Pandoc is, in my opinion, Vimwiki. This plug-in offers a whole ecosystem of useful features. Personally, I use it for two things: on one side as a diary, on the other as a means of taking notes for my research. I, therefore, have two separate wikis. But for both I use the markdown format, since this makes it easy to reuse the text in another context, for example in an essay or in my blog.

I appreciate especially how you can create new entries or navigate to existing ones by hitting `enter` on one or several highlighted terms. Another very useful feature is the possibility to sort your daily entries chronologically.

This, for example, is what my working journal for May looks like:

```
### Mai
  * [[2017-05-30|Vortrag RVL von Torsten Hiltmann (Münster): Digitale Heraldik]]
  * [[2017-05-29|Lektüre von Lars Behrisch: Berechnung der Glückseligkeit]]
  * [[2017-05-26|Zu erledigen]]
  * [[2017-05-25|Forschungskolloquium]]
  * [[2017-05-23|2017-05-23 Arbeitsplan]]
  * [[2017-05-22|2017-05-22 Arbeitsplan]]
```

My configuration looks like this:

``` vimscript
let g:vimwiki_list = [{'path': '~/Documents/VimWiki/personal.wiki', 'syntax': 'markdown', 'ext': '.md', 'diary_header': 'Journal'}, {'path': '~/Documents/VimWiki/work.wiki', 'syntax': 'markdown', 'ext': '.md', 'diary_header': 'Arbeitsjournal'}]
let g:vimwiki_diary_months = {
      \ 1: 'Januar', 2: 'Februar', 3: 'März',
      \ 4: 'April', 5: 'Mai', 6: 'Juni',
      \ 7: 'Juli', 8: 'August', 9: 'September',
      \ 10: 'Oktober', 11: 'November', 12: 'Dezember'
      \ }
```

## Ditto

The plug-ins I presented so far offer different environments in which one can write text. The next plug-in I would like to bring to your attention is useful with regard to your style of writing. It is called Ditto and highlights words often used in a paragraph. So it helps you to avoid repeating the same words over and over again. To put it differently, it increases your style.

```vim
au FileType markdown,text,tex DittoOn  " Turn on Ditto's autocmds
nmap <leader>dt <Plug>ToggleDitto      " Turn it on and off
nmap <leader>dn <Plug>DittoNext        " Jump to the next word
nmap <leader>dp <Plug>DittoPrev        " Jump to the previous word
nmap <leader>dg <Plug>DittoGood        " Ignore the word under the cursor
nmap <leader>db <Plug>DittoBad         " Stop ignoring the word under the cursor
nmap ]d <Plug>DittoMore                " Show the next matches
nmap [d <Plug>DittoLess                " Show the previous matches
```

## Goyo

Sometimes everything is annoying and you need to focus on your text – because a deadline is closing soon or just to sort things out. At other times less is more, so you want to have a pure and simple interface for your writing. In situations like these I like to turn to Goyo. This is a plug-in that strips off all additional information Neovim provides in order to show just your text. In fact, it is running for this presentation. It works out of the box. You toggle it with `:Goyo`. With the same command you disable it again, or you just press `:q`.

## Targets

The last plug-in I would like to point out is Targets. It enhances Vim's and Neovim's ability to move the cursor around in text. This is especially useful for combining commands with movements. For instance:

* `cin)`: changes the contents of the next brackets
* `dal"`: deletes around the last (i.e. previous) quote
* `vi,`: marks the contents of the comma delimited clause

... just to name a few. I find this a really great addition to the already substantial standard movements.


# Conclusion

Historians as well as other scholars of the humanities deal with a lot of text in their day to day work. They have, in other words, an affinity for languages. Vim and Neovim, on the other side, put a *Domain Specific Language* at our disposal for dealing with text. Therefore, it is in my opinion just obvious and consistent for us humanists to turn to Vim and Neovim for our daily grind.

Because of this, I would like to thank you for all your efforts! Because of you Vim and Neovim are an awesome piece of software.

I hope I have given you some clues on how scholars of the humanities can make use of Neovim. If you have any questions, please let me know.
