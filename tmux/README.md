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
    
