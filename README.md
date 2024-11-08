在github搭建越狱软件源

准备工作

1.拥有一个github账号

2.已经装载了filza文件管理器，终端（如newterm3或MTerminal）

3.已经准备好了deb插件文件

4.在sileo已经安装了这几个插件
- dpkg - 1.22.6
- dpkg-dev - 1.22.6
- dpkg-repack - 1.52
- libdpkg-dev - 1.22.6
- libdpkg-perl - 1.22.6

操作流程

1.在github创建一个新的存储库，名为xxxxx.github.io（xxxxx可以是你的名字）

2.添加一个名为Release的文件，这里面包含的软件源的基本信息，下面是一个示例

Origin: 🇨🇳lans233's repo
Label: lans233's repo
Suite: stable
Version: 1.0
Codename: ios
Architectures: iphoneos-arm64
Components: main
Description: QQ交流群157289939，欢迎进群！

其中，Origin是软件源的名字，Description是软件源介绍，别的自行对照，可将这个作为模版套用，记得冒号要用英文冒号

3.假设你已经用filza将deb插件文件全部存放在了/var/mobile/Documents/debs这个文件夹中。打开终端，输入cd /var/mobile/Documents/debs定位到这个文件夹，接着输入dpkg-scanpackages . /dev/null > Packages
，即可在这个文件夹里面生成一个名为Packages的文件

4.回到刚刚建的github存储库，将刚刚生成的Packages文件放进去

5.在存储库新建一个名为debs的文件夹，将所有的插件文件放入

github 发布网页

1.上面的项目创建好后，在网页访问 xxxxx.gitbug.io 会提示 404，页面中有个蓝色的链接，点击后 github 官方会有指导教程

2.项目下需有 index.html 作为项目访问默认页

结语：这个时候，你就已经完成搭建了，不过还有一些可以更完善这个源的方法，这个我们以后再讲
