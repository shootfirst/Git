# Git


  + git常用命令(本地)
  
    - git init
        + 对现有项目进行管理
    
    - git status
        + 观察被跟踪的所有文件所处状态，注意，git clone下来的所有文件默认被跟踪，而git init与.git同目录下的文件则未被跟踪

    - git add
        + 开始跟踪一个新文件；将文件加入暂存区

    - git diff
        + 比较工作目录和暂存区文件之间的差异

        + --cached 比较暂存区与本地仓库文件之间差异

    - git commit
        + 用暂存区的文件创建一次新的提交，把此时的节点设为父节点，把当前分支指向新的节点

        + -m 提交说明
        + -a 把所有跟踪的文件暂存并且提交
        + --amend 使用与当前父节点进行一次新提交，旧提交被取消

    - git checkout
        + 从历史提交或暂存区拷贝文件到工作目录，当给定某个文件名（或者打开-p选项，或者文件名和-p选项同时打开）时，git会从指定的提交中拷贝文件到暂存区域和工作目录。比如
          ，git checkout HEAD~ foo.c会将提交节点HEAD~(即当前提交节点的父节点)中的foo.c复制到工作目录并且加到暂存区域中。（如果命令中没有指定提交节点，则会从暂存区域中拷贝内容。）
          注意当前分支不会发生变化
        + 当不指定文件名，而是给出一个（本地）分支时，那么HEAD标识会移动到那个分支（也就是说，我们“切换”到那个分支了），然后暂存区域和工作目录中的内容会和HEAD对应的提交节点一致
        + 如果既没有指定文件名，也没有指定分支名，而是一个标签、远程分支、SHA-1值或者是像main~3类似的东西，就得到一个匿名分支，称作detached HEAD（被分离的HEAD标识）。
        + 当HEAD处于分离状态（不依附于任一分支）时，提交操作可以正常进行，但是不会更新任何已命名的分支。(你可以认为这是在更新一个匿名分支。)一旦此后你切换到别的分支，比如说main，那
          么这个提交节点（可能）再也不会被引用到，然后就会被丢弃掉了。注意这个命令之后就不会有东西引用它，但是，如果你想保存这个状态，可以用命令git checkout -b name来创建一个新的分           支
    
    - git reset
        + 把当前分支指向另一个位置，如果不给选项，那么当前分支指向到那个提交，暂存区更新，如果用--hard选项，那么工作目录也更新，如果用--soft选项，那么都不变
        + 如果给了文件名(或者 -p选项), 那么工作效果和带文件名的checkout差不多，除了索引被更新

    - git merge
        + merge 命令把不同分支合并起来。合并前，索引必须和当前提交相同。如果另一个分支是当前提交的祖父节点，那么合并命令将什么也不做。 另一种情况是如果当前提交是另一个分支的祖父
          节点，就导致fast-forward合并。指向只是简单的移动，并生成一个新的提交。
        + 否则就是一次真正的合并。默认把当前提交和另一个提交以及他们的共同祖父节点进行一次三方合并。结果是先保存当前目录和索引，然后和父节点33104一起做一次新提交,若产生冲突，修改冲
          突文件，再add，commit
          
    - git cherry-pick
        + 复制"一个提交节点并在当前分支做一次完全一样的新提交(好像没啥用这命令，用得少)

    - git rebase
        + 衍合是合并命令的另一种选择。合并把两个父分支合并进行一次提交，提交历史不是线性的。衍合在当前分支上重演另一个分支的历史，提交历史是线性的。 本质上，这是线性化的自动的                 cherry-pick
  
  
  + git常用命令(本地)

    - git clone
        + 将远程仓库克隆到本地
    
    - git fetch
        + 同步o/main，本地main不受影响
        + git fetch origin main,更新o/main
        + git fetch origin xxx:yyy,更新远程xxx到本地分支yyy，可加~和^
        
    - git pull
        + 相当于git fetch xxx 加 git merge xxx
        + --rebase，将merge改成rebase
    - git push
        + 将本地仓库推送到远程

  
  
  + git 原理（日后补上）
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
