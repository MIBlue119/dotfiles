# Homebrew 

[Homebrew](https://brew.sh/index_zh-tw) is a packag manage tool for macos

## Installation 
- Paste the command at the terminal of macos
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
## Usage 
- Package our mac's installed app with brew 
```
$brew bundel dump --describe --force --file=="~/dotfiles/homebrew/Brewfile"
```
- Install the packages by the Brewfile
```
brew bundle --file="~/dotfiles/homebrew/Brewfile"
```
## Source
- [用Homebrew來安裝需要的App跟套件](https://htlin.site/posts/homebrew-basic)