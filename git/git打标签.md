#### git 打标签
1. 列出标签
` git tag `
2. 列出指定标签
` git tag -l 'v1.*' `
3. 创建标签(附注标签，带i提交信息)(推荐)
` git tag -a v1.0 -m 'version 1.0' `
4. 查看标签信息
` git show v1.0 `
5. 轻量级标签(不带提交信息)
` git tag v1.0`
6. 后期打标签
` git tag -a v1.2 9fceb02 `
7. 提交单个标签到服务器
` git push origin v1.0`
8. 提交多个标签到服务器
` git push origin --tags `
9. 删除标签
``` 
git tag -d tag_name 
git push origin :refs/tags/v1.0 
 ```