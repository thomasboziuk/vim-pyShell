# vim-pyShell

This project is a fork of https://github.com/tcarette/vim-sparkShell. TCarette initially developped this plugin for the spark-shell. I slighlty simplified/modified it for the sake of working with ipython.

This is a very basic integration of the ipython. 
So far it allows to start an ipython repl in tmux, then vimux is used to
send lines to it. There are also specific functions to work with pandas dataframes

## Dependencies

* tmux         (tested with version 1.9, fails with 1.6)
* ipython
* [vimux](https://github.com/benmills/vimux.git).


## Installation and usage

Install the above dependencies.
After installing the above dependencies, the easiest is to use `vim-plug`
and add the following line to your .vimrc

    Plug greghor/vim-pyShell

* Useful basic mappings (to include in your `.vimrc`)

		map <startMap>                  :call StartPyShell()<CR>
		nmap <killMap>                  :call StopPyShell()<CR>

		nmap <sendWordUnderCursor>      :call PyShellSendKey("<C-R><C-W>\r")<CR> 
		vmap <sendSelectionPerChar>    y:call PyShellSendKey(substitute('<C-R>0',"\"","\\\"","")."\r")<CR>
		vmap <seeObjectUnderCursor>    y:call PyShellSendKey(substitute('<C-R>0',"\"","\\\"","")."\r")<CR>

Be creative, ellaborate on that, and create your own mappings!

