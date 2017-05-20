前两天谷歌宣布了使用Kotlin为官方语言，再加上kotlin本身的优点，那学习并使用kotlin就仿佛成了一种必然。今天和项目里的小伙伴稍微讨论了一下，便决定大家一起学习，并根据个人掌握情况，在合适的时候开始应用到项目上。今天是我开始学习kotlin的第一天，主要是配置环境，记录一下。

> kotlin官方中文网站：https://www.kotlincn.net/docs/reference/android-overview.html 

> Android Stuido 3.0以上已经开始集成了kotlin，可以直接使用；而3.0以下需要插件支持，其实使用起来也很方便。

# 一、安装kotlin支持（AS3.0及以上可跳过）

打开`Android Studio`的设置，找到`Plugins`，在里面搜索`kotlin`，点击安装，安装完成之后会提示你重新启动AS。这里可能需要翻墙，最少我最初是下载失败的，翻墙之后下载成功。*官网以及很多文章都推荐下载`anko`插件，个人这里先不推荐，具体原因下面会说到。*

# 二、添加kotlin依赖

在安装完`kotlin`支持后，现在在你的`module`下右键，会发现有两个新的kotlin选项，说明安装成功。
![new里有新的kotlin选项.png](http://upload-images.jianshu.io/upload_images/292429-9c9ece23b2838777.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
点击`Kotlin Activity`(另一个kotlin选项也可以)，创建一个`kotlin`文件，然后右上角会提示你`配置kotlin`，点击`Configure`，然后点击`Android with Gradle`
![配置kotlin.png](http://upload-images.jianshu.io/upload_images/292429-946471248c0f2488.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![配置kotlin2.png](http://upload-images.jianshu.io/upload_images/292429-a2743478a111f7e9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
kotlin会自动为你添加依赖，具体的修改为

1. 在项目的`build.gradle`文件中，增加了

```
classpath "org.jetbrains.kotlin:kotlin-gradle-plugin:$kotlin_version"
```

我这里的kotlin_version为1.1.2-4，目前的最新版

2.在`module`的`build.gradle`文件中，增加了

```
apply plugin: 'kotlin-android'
compile "org.jetbrains.kotlin:kotlin-stdlib-jre7:$kotlin_version"
```

# 三、安装android扩展

官网还推荐了一个插件：`kotlin-android-extensions`，能大大减少，甚至消灭`findViewById`，直接映射xml的组件，具体看<a href="https://www.kotlincn.net/docs/tutorials/android-plugin.html">官网的说明</a>

到这里，环境配置基本就完成了。

# 四、遇到的坑

1. 首先要说的就是配置支持时说到的`anko`插件，为什么说个人不推荐用呢，是因为我在安装了这个插件，重启AS之后（安装完插件要求重启AS），发现启动失败，报错弹框如下
  ![anko报错弹框.png](http://upload-images.jianshu.io/upload_images/292429-0ac27f90800a42e0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
  google了一下后，说是anko的问题，卸载之后果然启动了，但是具体原理现在还不清楚。如果谁了解这个原因，或者最棒的是知道解决办法，随时欢迎交流指导。

2. 添加完依赖进行重新构建的时候，在download环节卡了很久，而且我是翻墙的，后来不想等了，强杀AS后，重新发现build成功。之后又重启过几次，基本卡download和build成功基本一半一半，不知道是我的网络原因还是其他。

# 最后

刚刚接触kotlin，知道肯定有很多坑要踩，但是不会放弃，踩坑填坑的过程，才是真正进步的过程！同时希望同样在学kotlin的能多多交流，共同进步！