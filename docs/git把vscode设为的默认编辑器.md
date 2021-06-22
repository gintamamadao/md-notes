# Parent Node

- [ROOT](./root.md)
- [git 学习杂记](./git学习杂记.md)

# Child Node

# git 把 vscode 设为的默认编辑器


- 使用组合键 command+shift+p,
- 输入intall，选择 'Shell Command: Install 'code' command in Path'
- 此时code命令就可以直接调用VS来编辑可打开文件。
- 终端输入 git config --global core.editor "code -w" 设置git编辑器为VS Code。
- 可查看 vim ~/.gitconfig 文件内，是否已经正确改变。