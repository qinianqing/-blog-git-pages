### 免费无限流的blog（发表文章）

* **优点**

  * 免费，无限流量。
  * 享受git的版本管理功能，不用担心文章遗失。
  * 你只要用自己喜欢的编辑器写文章就可以了，其他事情一概不用操心，都由github处理。

* 缺点

  * 有一定技术门槛，你必须要懂一点git和网页开发。
  * 它生成的是静态网页，添加动态功能必须使用外部服务，比如评论功能就只能用[disqus](http://disqus.com/)。
  * 它不适合大型网站，因为没有用到数据库，每运行一次都必须遍历全部的文本文件，网站越大，生成时间越长。

* 具体命令

  ```
  //创建一个项目文件夹
  $ mkdir demo
  //选择文件夹进行初始化
  $ cd demo
  $ git init
  //创建一个没有父节点的分支gh-pages。因为github规定，只有该分支中的页面，才会生成网页文件。
  $ git checkout --orphan gh-pages
  //在demo文件夹下面创建index.html
  $ touch index.html
  //在index.html里面写你的文章
  //提交
  $ git add .
  $ git commit -m "first post"
  $ git remote add origin https://github.com/username/demo.git
  $ git push origin gh-pages
  //访问网页
  http://username.github.com/jekyll_demo/就可以看到Blog已经生成了（将username换成你的用户名）。
  ```

  * **注意**

    修改之后提交：` git push --set-upstream origin gh-pages`

* 指向自己的域名

  如果你不想用**http://username.github.com/demo/**这个域名，可以换成自己的域名。

  具体方法是在repo的根目录下面，新建一个名为CNAME的文本文件，里面写入你要绑定的域名，比如example.com或者xxx.example.com。

  如果绑定的是顶级域名，则DNS要新建一条A记录，指向204.232.175.78。如果绑定的是二级域名，则DNS要新建一条CNAME记录，指向username.github.com（请将username换成你的用户名）。

  至此，最简单的Blog就算搭建完成了。进一步的完善，请参考Jekyll创始人的[示例库](https://github.com/mojombo/tpw)，以及其他用Jekyll搭建的[blog](https://github.com/mojombo/jekyll/wiki/Sites)。

