#

                   _   _                 _
                  | \ | |               (_)
                  |  \| | ___  _____   ___ _ __ ___
                  | . ` |/ _ \/ _ \ \ / / | '_ ` _ \ 
                  | |\  |  __/ (_) \ V /| | | | | | |
                  |_| \_|\___|\___/ \_/ |_|_| |_| |_|


                      The Historian's Best Friend



                            Ramon Voges

                            Sep 23, 2017


# Outline





1. My Journey to (Neo)Vim
2. Vim as a DSL
3. Plug-ins
4. Conclusion


# My Journey to (Neo)Vim                                        (1/5)














Word

# My Journey to (Neo)Vim                                        (2/5)













          -> Emacs
Word


# My Journey to (Neo)Vim                                        (3/5)












                      -> Textmate
          -> Emacs
Word


# My Journey to (Neo)Vim                                        (4/5)











                                      -> Atom
                      -> Textmate
          -> Emacs
Word


# My Journey to (Neo)Vim                                        (5/5)










                                                 -> Vim
                                      -> Atom
                      -> Textmate
          -> Emacs
Word



# Vim as DSL                                                    (1/3)


# Vim as DSL                                                    (2/3)





* `(` or `)`: to quickly navigate from sentence to sentence
* `{` or `}`: to quickly jump from paragraph to paragraph
* `ciw`: to quickly change a word in a sentence
* `daw`: one of the sequences I use most often
* `das`: to delete a whole sentence
* `ci(`: to change the words within the brackets
* `.`: 'the dot formula', to repeat the last change


# Vim as DSL: Spell Checking                                    (3/3)





* `]s`: goto next misspelled word
* `[s`: goto previous misspelled word
* `zg`: mark word as good
* `zw`: mark word as wrong
* `z=`: suggests correct words


# Plug-ins


1. Vimtex (https://github.com/lervag/vimtex)

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


# Plug-ins


2. Pandoc (https://pandoc.org/)





`:Pandoc <output format> [options]`



# Plug-ins


3. Vimwiki (https://vimwiki.github.io/)





```
Mai
  * [[2017-05-30|Vortrag RVL von Torsten Hiltmann (Münster): Digitale Heraldik]]
  * [[2017-05-29|Lektüre von Lars Behrisch: Berechnung der Glückseligkeit]]
  * [[2017-05-26|Zu erledigen]]
  * [[2017-05-25|Forschungskolloquium]]
  * [[2017-05-23|2017-05-23 Arbeitsplan]]
  * [[2017-05-22|2017-05-22 Arbeitsplan]]
```


# Plug-ins


3. Vimwiki (https://vimwiki.github.io/)





``` vimscript
let g:vimwiki_list = [{'path': '~/Documents/VimWiki/personal.wiki', 'syntax': 'markdown', 'ext': '.md', 'diary_header': 'Journal'}, {'path': '~/Documents/VimWiki/work.wiki', 'syntax': 'markdown', 'ext': '.md', 'diary_header': 'Arbeitsjournal'}]
let g:vimwiki_diary_months = {
      \ 1: 'Januar', 2: 'Februar', 3: 'März',
      \ 4: 'April', 5: 'Mai', 6: 'Juni',
      \ 7: 'Juli', 8: 'August', 9: 'September',
      \ 10: 'Oktober', 11: 'November', 12: 'Dezember'
      \ }
```



# Plug-ins


4. Ditto (https://github.com/dbmrq/vim-ditto)


It is called Ditto and highlights words often used in a paragraph. It's name is Ditto and it highlights often used words. The Ditto plug-in highlights words you use to often in a paragraph.

```vimscript
au FileType markdown,text,tex DittoOn  " Turn on Ditto's autocmds
nmap <leader>dt <Plug>ToggleDitto      " Turn it on and off
nmap <leader>dn <Plug>DittoNext        " Jump to the next word
nmap <leader>dp <Plug>DittoPrev        " Jump to the previous word
nmap <leader>dg <Plug>DittoGood        " Ignore the word under the cursor
nmap <leader>db <Plug>DittoBad         " Stop ignoring the word under the cursor
nmap ]d <Plug>DittoMore                " Show the next matches
nmap [d <Plug>DittoLess                " Show the previous matches
```



# Plug-ins


5. Goyo (https://github.com/junegunn/goyo.vim)





`:Goyo`





# Plug-ins


6. Targets (https://github.com/wellle/targets.vim)





* `cin)`: changes the contents of the next brackets
* `dal"`: deletes around the last (i.e. previous) quote
* `vi,`: marks the contents of the comma delimited clause


# Conclusion                                                  (1/4)







* Scholars of the (Digital) Humanities have an affinity for languages


# Conclusion                                                  (2/4)







* Scholars of the (Digital) Humanities have an affinity for languages

* (Neo)Vim offers a Domain Specific Language for dealing with text


# Conclusion                                                  (3/4)







* Scholars of the (Digital) Humanities have an affinity for languages

* (Neo)Vim offers a Domain Specific Language for dealing with text

=> (Neo)Vim is great for humanists to work with!

# Conclusion                                                  (4/4)







 _______ _                 _
|__   __| |               | |
   | |  | |__   __ _ _ __ | | __  _   _  ___  _   _
   | |  | '_ \ / _` | '_ \| |/ / | | | |/ _ \| | | |
   | |  | | | | (_| | | | |   <  | |_| | (_) | |_| |
   |_|  |_| |_|\__,_|_| |_|_|\_\  \__, |\___/ \__,_|
                                   __/ |
                                  |___/


# How to Contact Me







* On the net: https://www.ramonvoges.de
* eMail: kontakt@ramonvoges.de
* Twitter: @ramon_voges
* Github: https://github.com/ramonvoges


