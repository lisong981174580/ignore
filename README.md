# gitignore
git忽略文件的建立...
> git教程地址 https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000

> git命令速查表  https://www.sheetgit.com/sheets/0d7ce5911254db982aa7b1601fa0fa6d
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
> 我们在远程创建仓库的时候就把忽略文件创建好，完了本地直接拉取就可以了，这样不但不会报错，同时也可以生效(必须是文件(.gitignore文件)而不是文件夹，否则这样也会报错)
#### 方法二：
> 创建好仓库后拉取后，第一件事就是创建忽略文件(.gitignore文件)，提交后再进行开发


## 克隆别人的脚手架
### 问题一：首次提交代码忽略文件没有生效

一般情况下，我们克隆别人的脚手架后，都会包含一份别人写好的.gitignore文件，但是如果对于小白的话，可能会直接把脚手架生成的代码，直接全部复制粘贴到自己的项目仓库中，但是发现首次提交代码的时候.gitignore文件并没有生效

### 原因：

忽略文件一定要在项目代码提交前提交，因为只有在远端有了忽略文件后才会生效，首次如果把忽略文件和其他代码一块提交的话，那么因为远端没有，所以首次也不会生效

### 问题二：粘贴别人代码后提交不到自己的仓库

### 原因：
通过脚手架生成的代码的package.json文件已经配置好了指定仓库，所以你虽然在提交，实际上你一直在向别人的仓库提交，所以不能盲目的粘贴，记得改配置

这些配置要么直接删掉，要么改成你自己的
```
  "repository": {
    "type": "git",
    "url": "git+https://github.com/PanJiaChen/vue-element-admin.git"
  },
  "bugs": {
    "url": "https://github.com/PanJiaChen/vue-element-admin/issues"
  },
```

这些不该虽然不影响运行，但是最改成自己
```
  "name": "vue-element-admin",
  "version": "3.9.0",
  "description": "A magical vue admin. Typical templates for enterprise applications. Newest development stack of vue. Lots of awesome   features",
  "author": "Pan <panfree23@gmail.com>",
  "license": "MIT",
```

### 一、vue-element-admin如何复制

> 学习网址 https://panjiachen.github.io/vue-element-admin-site/zh/guide/#%E5%8A%9F%E8%83%BD

1. 自己的仓库提前建好

2. 本地克隆一份 vue-element-admin

3. 先把vue-element-admin的.gitignore文件复制到自己的仓库，完了提交
 
4. 把剩下的复制过来，npm  i（个人建议不要用cnpm） ,完了照上面说的改package.json文件

5. 在吧剩下的文件提交，然后删掉本地的 vue-element-admin

### 二、create-react-app如何复制

1. 自己的仓库提前建好

2.create-react-app myapp 先在本地生成一份

3.npm run eject(生成配置文件)

4.照上面说的改package.json文件,删掉package-lock.json文件

这些不该虽然不影响运行，但是最改成自己

```
  "name": "vue-element-admin",
  "version": "3.9.0",
  "description": "A magical vue admin. Typical templates for enterprise applications. Newest development stack of vue. Lots of awesome   features",
  "author": "Pan <panfree23@gmail.com>",
  "license": "MIT",
```

5. 把myapp的.gitignore文件复制到自己的仓库，完了提交

6.把剩下的文件除了/node_modules和.gitignore不复制，剩下的全部复制，npm i ,运行没问题后，完了提交

7.删掉本地把myapp




