# 如何托管到Pages上

### 将_book发布到pages上
#### 一、将书籍源码托管到git远端仓库
这一环节的任务就是将书籍的源码（不含gitbook build生成的内容）推送到远端仓库。
##### 新建仓库
在GitBook项目目录，如mybook中，执行如下命令，创建本地git仓库：

```
git init
```

##### 添加忽略文件
使用文本编辑器在项目的根目录下，创建名为.gitignore的文件，内容如下：

```
*~
_book
.DS_Store
```
通过.gitignore文件，本地仓库将忽略临时文件和_book文件夹，达到只保存书籍源码的目的。

##### 添加文件
现在可以将本地书籍源码添加到本地git仓库中了：

```
git add .
```
##### 添加更新说明

```
git commit -m '更新说明文字'
```

##### 建立本地仓库与远端仓库的对应关系

```
git remote add origin https://远程仓库地址.git
```
##### 推送
将本地仓库内容同步到远端仓库：

```
git push -u origin master
```

至此，就完成了将gitbook源码推送到远程仓库的任务，之后书籍内容修改后，执行如下操作即可：

```
git add .
git commit -m '更新说明文字'
git push -u origin master
```

#### 二、使用pages服务展示gitbook书籍

将_book文件夹中的内容推送到远程仓库的pages分支，启用pages服务，最终达到免费发布电子书的目的。

##### 新建分支

```
git checkout --orphan pages
```
##### 添加文件

```
git add _book/
```
##### 添加更新说明

```
git commit -m '更新说明'
```
##### 推送

```
git push -u origin pages
```

##### 切回master分支
删除pages分支

可以不删除pages分支，下次可以再用
> 查看分支

```
git branch
```
> 回到master分支


```
git checkout master
```


#### 三、在gihub page开启服务

#### 四、其他
##### 想删除远程分支
代码实现
```
git push origin:分支名
```
或在客户端直接删除


