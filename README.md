This is the repository to hold my personal VIM development
configuration.

Put this in your ~/.vimrc.after file:

```
" NERDtree configuration
"
"
autocmd vimenter * NERDTree
autocmd StdinReadPre * let s:std_in=1
autocmd VimEnter * if argc() == 0 && !exists("s:std_in") | NERDTree | endif

autocmd StdinReadPre * let s:std_in=1
autocmd VimEnter * if argc() == 1 && isdirectory(argv()[0]) && !exists("s:std_in") | exe 'NERDTree' argv()[0] | wincmd p | ene | endif

map <C-f> :NERDTreeToggle<CR>

autocmd bufenter * if (winnr("$") == 1 && exists("b:NERDTree") && b:NERDTree.isTabTree()) | q | endif

"
" Vim airline configuration
"
let g:airline#extensions#tabline#enabled = 1

"
" Neocomplcache configuration
"
"let g:neocomplcache_enable_at_startup = 1

```
