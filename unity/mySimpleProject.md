# My Simple Project

## skiing

### Canvas的镜头跟随

创建一个空物体，把canvas和player放在该空物体下，调整距离即可

UI交互

通过手柄触控板来实现菜单栏，通过扳机键来确定

打开ui时暂停计时

手柄动作的获取

物体的抓取

人物的移动加速减速

手柄速度的获取

人物移动音效的添加和背景音乐的添加

### SteamVR不行，转战VIVEInput

#### viveInput的环境配置

##### Steam VR plugin(适配2.x以上版本)

OpenXR（需要Unity2020以上）

https://learn.microsoft.com/zh-cn/windows/mixed-reality/develop/unity/new-openxr-project-without-mrtk#configure-the-project-for-desktop-vr

导入插件后记得先save一下动作集



手柄射线的触发，生成，销毁



## SimpleShoot

从3D到VR

### 通过鼠标控制镜头移动

### Unity实现子弹射向准心位置



测试开始界面按钮的交互问题



### 实现隔一段时间改变靶子位置

总结以下三种方法，实现c#每隔一段时间执行代码：

方法一：调用线程执行方法，在方法中实现死循环，每个循环Sleep设定时间；

方法二：使用System.Timers.Timer类；

方法三：使用System.Threading.Timer，值得注意的是一定要声明成全局变量以保持对Timer的引用，否则会被垃圾收集器回收！



















