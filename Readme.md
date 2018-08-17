# [C](#)onqure [o](#)f  [C](#)ompletion

| CI (Linux, macOS) | Coverage | Gitter | Doc    |
|-------------------|----------|--------|--------|
| [![Build Status Badge][]][Build Status] | [![Coverage Badge][]][Coverage Report] |  [![Gitter Badge][]][Gitter] | [![Doc Badge][]][Doc Link]

Coc is an intellisense engine for vim8 & neovim.

It's a completion framework, language server client with bundled extensions
from [VSCode](https://github.com/Microsoft/vscode) that just works.

![example.gif](https://user-images.githubusercontent.com/251450/42722527-028898ea-8780-11e8-959f-09db0d39ba05.gif)

_True snippet and additional text edit support_

Checkout [doc/coc.txt](doc/coc.txt) for vim interface.

## Pros.

* Easy to install and many features just work.
* Optimized for speed, no effect on startup time and fastest completion
  experience.
* Built in and custom completion source support.
* Full completion features support of language server protocol.
* Featured language server extensions from VSCode, like tsserver, tslint etc.
* Custom language server configuration support.

## Table of contents

* [Installation](https://github.com/neoclide/coc.nvim/wiki/Install-coc.nvim)

  For [vim-plug](https://github.com/junegunn/vim-plug) user. Add:

  ``` vim
  Plug 'neoclide/coc.nvim', {'do': { -> coc#util#install()}}
  ```

  Or build from source code by install [nodejs](https://nodejs.org/en/download/)
  and [yarn](https://yarnpkg.com/en/docs/install)

  ``` sh
  curl -sL install-node.now.sh/lts | sh
  curl --compressed -o- -L https://yarnpkg.com/install.sh | bash
  ```

  And add:

  ``` vim
  Plug 'neoclide/coc.nvim', {'do': 'yarn install'}
  ```

  to your `.vimrc` or `init.vim`, restart vim and run `:PlugInstall`.

  For other plugin manager, run command `:call coc#util#install()` to download
  binary after coc is installed.

* [Completion with sources](https://github.com/neoclide/coc.nvim/wiki/Completion-with-sources)

  * [Trigger mode of completion](https://github.com/neoclide/coc.nvim/wiki/Completion-with-sources#trigger-mode-of-completion)
  * [Snippet completion](https://github.com/neoclide/coc.nvim/wiki/Completion-with-sources#snippet-completion)
  * [Use `<Tab>` or custom key for trigger completion](https://github.com/neoclide/coc.nvim/wiki/Completion-with-sources#use-tab-or-custom-key-for-trigger-completion)
  * [Improve completion experience](https://github.com/neoclide/coc.nvim/wiki/Completion-with-sources#improve-completion-experience)
  * [Completion sources](https://github.com/neoclide/coc.nvim/wiki/Completion-with-sources#completion-sources)

* [Using configuration file](https://github.com/neoclide/coc.nvim/wiki/Using-configuration-file)

  * [Configuration file resolve](https://github.com/neoclide/coc.nvim/wiki/Using-configuration-file#configuration-file-resolve)
  * [Default COC preferences](https://github.com/neoclide/coc.nvim/wiki/Using-configuration-file#default-coc-preferences)
  * [Configuration for sources](https://github.com/neoclide/coc.nvim/wiki/Using-configuration-file#configuration-for-sources)
  * [Extension configuration](https://github.com/neoclide/coc.nvim/wiki/Using-configuration-file#extension-configuration)

* [Language servers](https://github.com/neoclide/coc.nvim/wiki/Language-servers)

  * [Supported features](https://github.com/neoclide/coc.nvim/wiki/Language-servers#supported-features)
  * [Built in server extensions](https://github.com/neoclide/coc.nvim/wiki/Language-servers#built-in-server-extensions)
  * [Register custom language servers](https://github.com/neoclide/coc.nvim/wiki/Language-servers#register-custom-language-servers)
  * [Debug language server](https://github.com/neoclide/coc.nvim/wiki/Debug-language-server)

* [ Statusline integration](https://github.com/neoclide/coc.nvim/wiki/Statusline-integration)

* [Create custom source](https://github.com/neoclide/coc.nvim/wiki/Create-custom-source)

* [F.A.Q](https://github.com/neoclide/coc.nvim/wiki/F.A.Q)

## Completion sources

Name         | Description                              | Filetypes   | Requirement
------------ | -------------                            |------------ |------------
`around`     | Words of current buffer.                 | all         |
`buffer`     | Words of none current buffer.            | all         |
`dictionary` | Words from files of `dictionary` option. | all         |
`tag`        | Words from `taglist` of current buffer.  | all         |
`file`       | Filename completion.                     | all         |
`omni`       | Invoke `omnifunc` for complete items     | []          |
`word`       | Words from google 10000 english repo.    | all         |
`emoji`      | Emoji characters.                        | all         |
`include`    | Full path completion.                    | all         |
`gocode`     | Completion using gocode                  | ['go']      | Install [gocode](https://github.com/mdempsky/gocode)
`ultisnips`  | Snippets completion                      | all         | Install [ultisnips](https://github.com/SirVer/ultisnips)
`neco`       | Viml completion                          | vim         | Install [neco-vim](https://github.com/Shougo/neco-vim)
`neosnippet` | Snippets completion                      | all         | Install [neosnippet.vim](https://github.com/Shougo/neosnippet.vim)

* To enable `omni` source for certain files, open `coc-settings.json` by `:CocConfig`, then add configuration like:

    ```
    "coc.source.omni.filetypes": ["python"],
    ```

* To complete sources: `include`, `emoji` and `word`, use mapping of `<Plug>(coc-complete-custom)`

## Extensions

Language server are decoupled from coc.nvim to make the core smaller, and easier
for user to use their own version of language server.

* **Tsserver**

    Used for `javascript` and `typescript`

        yarn global add typescript

* **Html**

    Used for `html` `handlebars` `razor`

        yarn global add vscode-html-languageserver-bin

* **Json**

    Used for `json` and `jsonc`

        yarn global add vscode-json-languageserver

* **Css**

    Used for `css` `scss` `less` and `wxss`

        yarn global add css-langserver

* **Wxml**

        yarn global add wxml-langserver

* **Vetur**

    Used for `vue`

        yarn global add vue-language-server

* **Solargraph**

    Used for `ruby`

    Install [solargraph](http://solargraph.org/) by:

        gem install solargraph

* **Pyls**

    Used for `python`

    Install [pyls](https://github.com/palantir/python-language-server) by:

        pip install 'python-language-server[all]'

* **Stylelint**

    Used for  `css` `wxss` `scss` `less` `markdown` `postcss` `sugarss` `vue`.

        yarn global add stylelint-langserver

* **Eslint**

    Used for `javascript`

        yarn global add eslint-server

* **Tslint**

    Used for `typescript`

        yarn global add tslint-server

**Note:** use `:CocConfig` to edit configuration file, auto completion is supported

## Example configuration

``` vim
" Better display for signatures
set cmdheight=2

" Use tab for trigger completion with characters ahead and navigate.
inoremap <silent><expr> <TAB>
      \ pumvisible() ? "\<C-n>" :
      \ <SID>check_back_space() ? "\<TAB>" :
      \ coc#refresh()
inoremap <expr><S-TAB> pumvisible() ? "\<C-p>" : "\<C-h>"

" Use <c-space> for trigger completion.
inoremap <silent><expr> <c-space> coc#refresh()

" Use <C-p> to complete 'word', 'emoji' and 'include' sources
imap <silent> <C-p> <Plug>(coc-complete-custom)

function! s:check_back_space() abort
  let col = col('.') - 1
  return !col || getline('.')[col - 1]  =~# '\s'
endfunction

" Use <cr> for confirm completion.
inoremap <expr> <cr> pumvisible() ? "\<C-y>" : "\<C-g>u\<CR>"

" Use `[c` and `]c` for navigate diagnostics
nmap <silent> [c <Plug>(coc-diagnostic-prev)
nmap <silent> ]c <Plug>(coc-diagnostic-next)

" Remap keys for gotos
nmap <silent> gd <Plug>(coc-definition)
nmap <silent> gy <Plug>(coc-type-definition)
nmap <silent> gi <Plug>(coc-implementation)
nmap <silent> gr <Plug>(coc-references)

" Use K for show documentation in preview window
nnoremap <silent> K :call <SID>show_documentation()<CR>

function! s:show_documentation()
  if &filetype == 'vim'
    execute 'h '.expand('<cword>')
  else
    call CocAction('doHover')
  endif
endfunction

" Show signature help while editing
autocmd CursorHoldI,CursorMovedI * silent! call CocAction('showSignatureHelp')

" Remap for rename current word
nmap <leader>rn <Plug>(coc-rename)

" Remap for format selected region
vmap <leader>f  <Plug>(coc-format-selected)
nmap <leader>f  <Plug>(coc-format-selected)

" Remap for do codeAction of selected region, ex: `<leader>aap` for current paragraph
vmap <leader>a  <Plug>(coc-codeaction-selected)
nmap <leader>a  <Plug>(coc-codeaction-selected)

" Remap for do codeAction of current line
nmap <leader>ac  <Plug>(coc-codeaction)

" Use `:Format` for format current file
command! -nargs=0 Format :call CocAction('format')

" Add diagnostic info for https://github.com/itchyny/lightline.vim
let g:lightline = {
      \ 'colorscheme': 'wombat',
      \ 'active': {
      \   'left': [ [ 'mode', 'paste' ],
      \             [ 'cocstatus', 'readonly', 'filename', 'modified' ] ]
      \ },
      \ 'component_function': {
      \   'cocstatus': 'coc#status'
      \ },
      \ }


" Shortcuts for denite interface
" Show symbols of current buffer
nnoremap <silent> <space>o  :<C-u>Denite coc-symbols<cr>
" Search symbols of current workspace
nnoremap <silent> <space>t  :<C-u>Denite coc-workspace<cr>
" Show diagnostics of current workspace
nnoremap <silent> <space>a  :<C-u>Denite coc-diagnostic<cr>
" Show available commands
nnoremap <silent> <space>c  :<C-u>Denite coc-command<cr>
" Show available services
nnoremap <silent> <space>s  :<C-u>Denite coc-service<cr>
```

## Trouble shooting

Don't be hesitated to [open a issue](https://github.com/neoclide/coc.nvim/issues).

## LICENSE

[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Fneoclide%2Fcoc.nvim.svg?type=large)](https://app.fossa.io/projects/git%2Bgithub.com%2Fneoclide%2Fcoc.nvim?ref=badge_large)
[Build Status Badge]: https://api.travis-ci.org/neoclide/coc.nvim.svg?branch=master
[Build Status]: https://travis-ci.org/neoclide/coc.nvim
[Coverage Badge]: https://codecov.io/gh/neoclide/coc.nvim/branch/master/graph/badge.svg
[Coverage Report]: https://codecov.io/gh/neoclide/coc.nvim
[Gitter Badge]: https://badges.gitter.im/coc-nvim/Lobby.svg
[Gitter]: https://gitter.im/coc-nvim/Lobby
[Doc Badge]: https://img.shields.io/badge/doc-%3Ah%20coc.txt-red.svg
[Doc Link]: doc/coc.txt

