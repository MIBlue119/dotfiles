# How to install miniconda?


## Installation 

- Construct a directory to install the libraries of the miniconda
```
$mkdir -p ~/miniconda3
```
- Download the installation script/files to the directory
```
$wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda3/miniconda.sh
```
- Install the libraries at the directory
```
$bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
```
- Edit the `~/.bashrc` to set the conda path
   - Open the file to edit  
   ```
   $vim ~/.bashrc
   ```
   - Add this line to the bottom 
   ```
   # Add the conda path 
   export PATH=$HOME/miniconda3/bin/:$PATH
   ```
- Source the new setting 
```
$source ~/.bashrc
```
- Add the initial decription at the conda script
```
$conda init bash
```
  - After use `conda init bash` the `./bashrc` would be like this 
  ```
  # >>> conda initialize >>>
  # !! Contents within this block are managed by 'conda init' !!
  __conda_setup="$('/home/welly/miniconda3/bin/conda' 'shell.bash' 'hook' 2> /dev/null)"
  if [ $? -eq 0 ]; then
      eval "$__conda_setup"
  else
      if [ -f "/home/welly/miniconda3/etc/profile.d/conda.sh" ]; then
          . "/home/welly/miniconda3/etc/profile.d/conda.sh"
      else
          export PATH="/home/welly/miniconda3/bin:$PATH"
      fi
  fi
  unset __conda_setup
  # <<< conda initialize <<<
  ```
  - If you use other shell, just replace `bash` with other shell like `zsh`
    - Add `export PATH=$HOME/miniconda3/bin/:$PATH` to `~/.zshrc`
    - Use `conda init zsh` 


  
