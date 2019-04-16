
#### 忽略文件
1. 新建 .gitignore 文件
2. 
| 目录 | 说明|
--|:--
| /vendor | 忽略/vendor下的文件  |
| /public/hot | 忽略 /ublic/hot 下的文件 |
| /storage/*.key | 忽略 /storage下的.key 的文件 |
| .env | 忽略 .env 文件 |
格式规范:
>>>
- 所有空行或者以 ＃ 开头的行都会被 Git 忽略。
- 可以使用标准的 glob 模式匹配。
- 匹配模式可以以（/）开头防止递归。
- 匹配模式可以以（/）结尾指定目录。
- 要忽略指定模式以外的文件或目录，可以在模式前加上惊叹号（!）取反。
>>>
例子：
```
/node_modules
/public/hot
/public/storage
/storage/*.key
/vendor
.env
.phpunit.result.cache
Homestead.json
Homestead.yaml
npm-debug.log
yarn-error.log
```