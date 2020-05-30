# SoftLiu_UnityPackageManager
Create UnityPackageManager

发布UPM包
如果想要发布 UPM 包，我们必须通过如下git 命令把插件包所在的文件夹创建为 subtree
git subtree split --prefix=Assets/PackageName --branch upm

这个命令将 "Assets/PackageName" 目录放到“ upm” 分支。
通过这一步其他目录及文件不会出现在 upm 分支中。
接下来，为这个分支添加一个 tag 并推到远端。
git tag 1.0.0 upm       
git push origin upm --tags

版本更新
在 "master" 分支开发和调试然后在 package.json 更新版本信息
执行 "git subtree split"
添加 tag 然后 push。

安装UPM包
UPM Install via manifest.json
打开项目根目录manifest.json文件, 合并以下代码就可以安装UPM包


{
  "dependencies": {
    "com.sourcemuch.quickeditor.monitor": "https://github.com/henry-yuxi/QuickEditor.Monitor.git#0.0.8",
  }
}

