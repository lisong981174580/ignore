# gitignore
git忽略文件的建立...
### 描述
> 我们在使用nodej开发前端的时候，常常会安装一些第三方包,或者node+react或vue的时候，常常会有一些并不需要提交的或者文件太大提交的压力太大，这个时候我们就需要添加忽略文件，
但是我们在添加忽略文件的时候经常会遇到一个问题，尤其是初次添加的时候...
### 问题
> 我在远端创建了一个仓库，然后拉取下来，本地再新建一个 .gitignore 忽略文件
```
.DS_Store
node_modules/
npm-debug.log*
yarn-debug.log*
yarn-error.log*
package-lock.json
dist/
test/
config/

# Editor directories and files
.idea
.vscode
*.suo
*.ntvs*
*.njsproj
*.sln

```
然后npm 装了几个包，然后再 git add .,git commit -m'test' ,git push 返现报错或者忽略文件不起作用

### 解决办法
#### 方法一：
> 我们在远程创建仓库的时候就把忽略文件创建好，完了本地直接拉取就可以了，这样不但不会报错，同时也可以生效(必须是文件而不是文件夹，这样也会报错)
