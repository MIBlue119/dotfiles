#  Record some commands used

## Edit your `~/.gitconfig`

- [Example of gitconfig](./gitconfig)


## Submodule 
- Add submoudle
```
## Add submodule, PATH_OF_SUBMODULE could be the submodule name and if we don't give that would be set as the repo default
$ git submodule add GIT_REPO_URL PATH_OF_SUBMODULE
## Track the modified `.gitmodules` & submoudle_a
$ git add .gitmodules 
$ git add submodule_a 
$ git commit -a -m "Add submoudle_a" && git push
```
  - Ref
    - https://blog.wu-boy.com/2011/09/introduction-to-git-submodule/ 

  - An example of `.gitmodules`, we could see the added submodule at desired path 
  ```
  [submodule "drum_extractor/third_party/demucs"]
	  path = drum_extractor/third_party/demucs
  	url = https://github.com/welly/demucs.git
  ```
  - An example about the submodule would be added to `.git/config` 
  ```
  [submodule "drum_extractor/third_party/demucs"]
	url = https://github.com/DeepWaveInc/demucs.git
	active = true
  ```
  - A nice reading about `What is the point of 'git submodule init'?`
    - https://stackoverflow.com/questions/44366417/what-is-the-point-of-git-submodule-init   

- Remove submodule
```
## 1. Let the tracked directory untracked, move them from work tree and index and back to workspace
$git rm --cached submodule_a_dir 

## 2. Remove the untracked submodule directory 
$rm -rf submodule_a_dir

## 3. Edit `.gitmodules` to remove the related submodule setting 
$ vi .gitmodules

## 4. Edit `.git/config` to remove the related setting of submodule
$ vi .git/config 

## 5. Remove the submodule's .git directory
$ rm .git/modules/submodule_dir

## 6. Commit the changed 
$ git add .gitmodules && git commit -m "Remove the submodule"

## 7. Sync the git submodule 
$ git submodule sync 
## git submodule sync updates the metadata about a submodule
## to reflect changes in the submodule URL. It re-synchronizes 
## the information in .git/config with the information in .gitmodules.
## Ref: https://stackoverflow.com/questions/45678862/git-submodule-update-vs-git-submodule-sync 
```

  - Ref
    - http://jhjguxin.github.io/blog/2012/04/19/git-submodule-de-ren-shi-yu-zheng-que-shi-yong-!/  
    - https://stackoverflow.com/questions/1260748/how-do-i-remove-a-submodule

- Show the current submodule list 
```
$ git submodule--helper list 
```
  - Ref
    -  https://stackoverflow.com/questions/12641469/list-submodules-in-a-git-repository
 
## Show 

- Show the commits of specified file from who/when/changed what 
```
$git blame PATH_OF_FILE
``` 
   - Ref
   	- https://ithelp.ithome.com.tw/articles/10216358 
