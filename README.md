### Requirements

* Ubuntu 16.04 or 18.04 (maybe any debian based system? Not sure about package names...)
* Bash 

### Instructions
 
* Run the following two commands:

```

curl https://raw.githubusercontent.com/mjlbach/vim_it_up/master/vimitup.sh -sSf | bash 
source $HOME/.bashrc

```

### Features

* tmux
* fzf 
* bat
* rg
* fd
* neovim with:
    * Sensible leader key mappings
    * A Gruvy colorscheme
    * Git integration through vim-fugitive
    * Fuzzy jumping to tags (function and metho names), files, buffers, general strings, and more
    * Language server support (pip install python-language-server[all] in any activated virtual environment)
    
### Musings on useful features (by no means exhaustive)
* neovim
    * fzf
        * space is now leader key and most fzf commands are mapped to \<space\>\<key\>
        * \<space\>\<space\> pulls up an interactive list of open buffers. \<space\>\<space\>\<return\> jumps to last open buffer.
        * \<space\>s interactive searches for a string across your entire project with ripgrep.
        * \<space\>f pulls up an interactive list of all files in your git repo.
        * \<space\>t runs ctags with gutentags and pulls up a list of all methods/classes across your git repo.
        * \<space\>l pulls up a list of all lines in your current buffer. 
     
     * Language server
        * So long as you have an activated python environment with python-language-server installed (pip install python-language-server[all]) you will get code completion. \<ctrl\>\<n\> selects the next completion result. \<ctrl\>\<p\> selects the previous completion result.
        * gd in normal mode jumps to the definition of the method of your cursor across projects.
        * \<shift\>\<K\> in normal mode pulls up the definition of your method (including your own defined docstrings\>
        * F5 is the shortcut for major LSP features (refactoring, renaming, reformatting)
        * F2 renames current symbol
 
   * vim fugitive
        * :Gread [git branch]:path/to/your/file opens the file from the branch/path in your selected buffer
        * :Gdiff [git branch]:path/to/your/file (or currentfile use %) [git branch]:path/to/your/file opens vim diff between two branches/your file and master
        
   * vim commentary
       * gcc on current line comments it out
       * gc on selection comments block
       
   * Custom Michael-maps
       * \<space\>d opens a sidebar like nerdtree using netrw
       * F3 toggles paste mode
       * \<alt\>j moves current line down, \<alt\>k moves line up
       * F6 trims trailing whitespace
       * F9 can be configured to asynchronously run the current python file
       * gqq formats open json files
       * n always searches forward (for / and ?), N always searches backwards
 
 
### FAQ

* Why neovim? 

It comes with an appimage which makes it more modular, also it has more robust plugin support. Most of these plugins are vim compatible with minor modifications.

* Why? 

I program remotely on several different machines. This script makes it easy to replicate ~90% of my development environment anywhere. I typically program with ssh connected to a remote  vim 