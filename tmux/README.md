# tmux 

[tmux](https://github.com/tmux/tmux) is a teminal multiplexer.
- It could enables a number of terminal to be created 
- It support detached from a window

## Installation 

### Install 
- Mac 
    ```
    $ brew install tmux 
    ```
- Ubuntu
    ```
    $ apt-get install tmuux
    ```

### Check install 
```
$ which tmux
```

### Construct the `.tmux.conf` Config 

```
$ vim ~/.tmux/conf
```
- The `.tmux.conf` could be adjusted to your favorite style.
- The basic setting could reference [./.tmux.conf](./.tmux.conf)


## Basic command

- Execute tmux
    ```
    $ tmux
    ```
- List current tmux
    ```
    $ tmux ls
    ```
- Kill current all tmux 
    ```
    $ tmux kill-server
    ```
- Source the new config at tmux windows
    ```
    $ tmux source ~/.tmux.conf
    ```

## Resource
- [終端管理工具 tmux](https://mropengate.blogspot.com/2017/12/tmux.html)
- https://gist.github.com/v-yarotsky/2157908

- [How to record the setting of tmux](https://stackoverflow.com/questions/48619192/tmux-split-window-using-shell-script)
    - Use shell script to splits
       ```
        tmux split-window -h
        tmux split-window -h
        tmux select-layout even-horizontal
        tmux split-window -v
        tmux select-pane -t 0
       ```
    - Also has a plugin to save the config and reset[tmux-resurrect](https://github.com/tmux-plugins/tmux-resurrect)
- [tmux-plugin-manager](https://github.com/tmux-plugins/tpm)
    
    - Enable the tmux plugin manager
        - Clone tpm
    ```
    $ git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
    ```
    
    - Put this at the bottom of ~/.tmux.conf ($XDG_CONFIG_HOME/tmux/tmux.conf works too):
    ```
    # List of plugins
    set -g @plugin 'tmux-plugins/tpm'
    set -g @plugin 'tmux-plugins/tmux-sensible'

    # Other examples:
    # set -g @plugin 'github_username/plugin_name'
    # set -g @plugin 'github_username/plugin_name#branch'
    # set -g @plugin 'git@github.com:user/plugin'
    # set -g @plugin 'git@bitbucket.com:user/plugin'

    # Initialize TMUX plugin manager (keep this line at the very bottom of tmux.conf)
    run '~/.tmux/plugins/tpm/tpm'
    ```
    
    - Reload TMUX environment so TPM is sourced:
    ```
    $ tmux source ~/.tmux.conf
    ```
- Copy & Paste at tmux 
    - Ref
       - https://www.rockyourcode.com/copy-and-paste-in-tmux/ 
    ```
    ## prefix weould be our setting to activate tmux hot key 
    1. Enter copying mode:  prefix + [ 
    2. Select the part we want:  ctrl + space 
    3. Save the selectec part in buffer: ctrl + w 
    4. Paste th buffer to pane: prefix + ]
    ```
    - A success way to enable the copy to clipboard of the mac 
        - Ref: [vim copy paste style at mac](https://blog.subash.com.au/vim-style-copy-paste-in-tmux/)
        - Install dependency: `$brew install reattach-to-user-namespace`
        - The copy paste would support with these
            - Enter the copy mode with
                - Use the mouse to select the content at tmux windows 
                - Enter with Prefix(Ctrl+a) + [
            - Select the contents with `v` 
            - Exit the copy mode: `y`
            - How to paste? 
                - Use Prefix(Ctrl+a)+p        
    ```
    # The setting about copy, ref: https://blog.subash.com.au/vim-style-copy-paste-in-tmux/
    bind Enter copy-mode # enter copy mode
    # Enable the mouse to copy mode
    set-window-option -g mode-keys vi
    bind-key -T copy-mode-vi 'v' send-keys -X begin-selection
    bind-key -T copy-mode-vi 'y' send-keys -X copy-selection-and-cancel
    bind-key p paste-buffer

    # The code below is only word in MacOS
    # You have to install reattach-to-user-namespace first
    # $brew install reattach-to-user-namespace
    # The code below support to pipe the contents to mac's pbcopy
    # These command given contents to OSX clipboard
    set -g default-command "reattach-to-user-namespace -l ${SHELL}"
    bind-key -T copy-mode-vi 'y' send-keys -X copy-pipe-and-cancel 'reattach-to-user-namespace pbcopy'
    ```
    
