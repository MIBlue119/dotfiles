## Ohmyzsh is a commandline highlight tool
https://github.com/ohmyzsh/ohmyzsh

### Install at Ubuntu

1. Install zsh first
    ``` bash
    $ apt-get install zsh 
    ```
2. Clone `Ohmyzsh` 
    ``` bash
    $ git clone https://github.com/ohmyzsh/ohmyzsh.git
    ```
3. Install `Ohmyzsh`
    ``` bash
    $ cd /ohmyzsh/tools/
    $ ./install.sh
    ```
4. Change the setting
    ``` bash
    $ nano ~/.zshrc
    ZSH_THEME="agnoster"
    ```
    - Resolve the encode error
        -  Mac
            - https://nicksheng.github.io/2017/06/30/mac-zsh/
            - https://github.com/ccyongzhi/the-Learned/issues/33
        - Ubuntu
            - https://blog.csdn.net/CoderMannul/article/details/90https://blog.csdn.net/CoderMannul/article/details/90724645724645

5. Let the zsh opened when terminal is opened
    a. Add the `zsh` to bash
    ``` bash
    $ sudo vim ~/.bashrc
    ``` 
    b. Add this line
    ``` bash
    exec zsh
    ```
6. Use the theme `powerlevel10k`
    - Install the theme at oh-my-zsh: `git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k`
    - Set the theme at `/.zshrc`: `ZSH_THEME="powerlevel10k/powerlevel10k"`
    - Source the theme: `source ~/.zshrc`
    - Ref: https://holychung.medium.com/%E5%88%86%E4%BA%AB-oh-my-zsh-powerlevel10k-%E5%BF%AB%E9%80%9F%E6%89%93%E9%80%A0%E5%A5%BD%E7%9C%8B%E5%A5%BD%E7%94%A8%E7%9A%84-command-line-%E7%92%B0%E5%A2%83-f66846117921 

7. Install the nerd font to for `powerlevel10k`
    ```
    $brew tap homebrew/cask-fonts
    $brew cask install font-meslo-lg-nerd-font
    ```
    - Change the font of the shell preferences to `Meslo LG xxx` 
### Sources
- [用 zsh + zim + powerlevel10k 讓你的 Terminal 潮又快 ](https://dwye.dev/post/zsh-zim-powerlevel10k/)