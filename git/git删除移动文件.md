#### git 删除文件
1. 删除文件
` git rm file_name`
2. 删除暂存区文件
` git rm -f file_name `
3. 删除暂存区文件，本地文件不删除（忘记添加文件到.gitignore）
` git rm --cache file_name `
4. blog 方式删除文件
` git rm /log/\*.log `

#### 移动文件
` git mv file_from file_to`
