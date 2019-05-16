---
title: build_blog_diary
date: 2019-05-14 23:09:00
tags: 日记 blog gitpage hexo nexTDAY 01

---

# blog搭建日记


##  Day 1

### gitpage 初步尝试

参考： [gitpage官方介绍][1]

个人理解，gitpage应该是github 提供的静态网页托管服务，他和git仓库的某个分支绑定，自动部署。

- 创建username.github.io 为名的仓库

- 向master分支提交任意内容，此时，gitpage自动绑定好了，通过usename.github.io即可访问，访问效果如下：

  ![1557755944810](2019-05-14-build_blog_diary/1557755944810.png)

#### notice

- 关于gh-pages分支。个人主页只能绑定master分支，项目主页才可绑定在gh-pages分支上。[Github page shows master branch, not gh-pages][5]

### hexo 

> Hexo 是一个快速、简洁且高效的博客框架。Hexo 使用 [Markdown](http://daringfireball.net/projects/markdown/)（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。

[中文社区][2]

#### notice:

- 需要执行hexo deploy 前， 需要配置_config.yml 中的deploy项。



### 成果

按着教程按部就班，使得[个人主页][3]可以访问了。

![1557759138571](2019-05-14-build_blog_diary/1557759138571.png)

## Day 2

### 更换主题：nexT

[NexT User Docs – Starting to Use][4]

- 更改language:  后， 重启生效

### 新建post（博文）

```sh
hexo new post title
```

本质上是在hexo/source/_post/ 目录下创建了一个 *.md 文件， 文件中包含scaffolds中模板信息，如下，在此基础上继续编辑即可：

![scaffold](2019-05-14-build_blog_diary/scaffold.PNG)



- 引用文件通过相对目录引用
- [hexo博客添加图片][6] : 通过使用 hexo-asset-image插件实现mardowm文章内图片链接在生成静态页面时的映射

### 成果

![1557835573394](2019-05-14-build_blog_diary/1557835573394.png)
### 遗留问题

- 无法访问图片

## Day 3

### 博客中图片无法显示问题

- 原因：生成静态页面目录与实际文件目录不一致。

  图片访问地址为： 

  ```js
  src="/2019/05/14/build_blog_diary/**2019-05-14-build_blog_diary**/1557755944810.png"
  ```

  实际目录中文件路径为：

  ```sh
   public\2019\05\14\build_blog_diary\1557755944810.png
  ```

- 解决

  引用时直接引用文件名，省略标题同名目录。

  如文章名叫 title , 图片A 在 ./title/A.png， 此时应用时因输入 \!\[A desc\]\(A.png\) 而不是 \!\[./title/A desc\]\(A.png\)

### 遗留问题

- 上述问题解决后，本地编辑器无法很好地预览图片。

## Day 4

### hexo-asset-image 插件 本地 静态页面 插画图片统一问题

- 分析Day 3遗留问题，查看[hexo-asset-image插件源码](https://github.com/xcodebuild/hexo-asset-image/blob/master/index.js):

  ```javascript
  ....
  			  var srcArray = src.split('/').filter(function(elem){
  				return elem != '' && elem != '.';
  			  });
  			  if(srcArray.length > 1)
  				srcArray.shift();
  			  src = srcArray.join('/');
  			  $(this).attr('src', config.root + link + src);
  ....
  ```

  发现，插件将原文章中图片引用链接移除了第一个/ 及之前的内容。故相对路径引用**不应**使用 \[\]\(./title/A.png\) 而**应该**使用  \[\]\(tiltle/A.png\)

### 增加标签页和分类页

1. 查看hexo/theme/next/layout 目录内容,可以看到，其已经内置多种页面布局：

   ![next_layout](./2019-05-14-build_blog_diary/next_layout.png)

2. 

----

***参考资料***

[1]:https://pages.github.com/
[2]: https://hexo.io/zh-cn/docs/
[3]:  https://neversn.github.io/
[4]:https://theme-next.org/docs/getting-started/

[5]: https://stackoverflow.com/questions/25559292/github-page-shows-master-branch-not-gh-pages
[6]:https://www.jianshu.com/p/cf0628478a4e



---