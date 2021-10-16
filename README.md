# Blog

When update, using following:

``` 
cd 本地库目录
git add .
git commit -m "版本日志"
git push -u origin master
```

## [部分桌游玩法速查](https://github.com/Jade2121/Blog/blob/master/%E7%8E%A9%E6%B3%95%E9%80%9F%E6%9F%A5%E6%89%8B%E5%86%8C.md)


## Debug笔记
1.无法pull
```
C:\Users\han\Desktop\Githubpages>git pull
There is no tracking information for the current branch.
Please specify which branch you want to merge with.
```

解决办法：
```
cd 本地库
git pull
```
不是本地文件夹，而是本地文件夹下的文件夹

2. jekyll
加载错误：无法加载此类文件
```
使用 Ruby 3.0.1 在已擦除的 Mac 上重新安装 Jelly 后遇到了同样的问题。
解决使用：

bundle add webrick
```
https://talk.jekyllrb.com/t/load-error-cannot-load-such-file-webrick/5417




### Reference:
https://www.jianshu.com/p/5f3effb3eaad
https://www.jianshu.com/p/eb9af1279499
http://www.ruanyifeng.com/blog/2012/08/blogging_with_jekyll.html
