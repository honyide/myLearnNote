# SIKI学院

## 见缝插针

Canvas控件的event System用于响应事件，本次项目不需要，所以删除

修改Canvas的渲染模式为WorldSpace，这样就可以修改画布的大小至和我们的游戏环境一样，方便我们修改。canvas的大小和游戏环境的大小关系为1px：1网格

把canvas的event Camera 设置为Main Camera，让ui和精灵图统一使用MainCamera进行渲染

### 关键代码

###### 让中间小球旋转

  transform.Rotate(new Vector3(0,0, speed*Time.deltaTime));

###### 使物体到达目标位置

 transform.position = Vector3.MoveTowards(transform.position ,StartPoint.position, speed * Time.deltaTime);

###### 判断物体是否到达 目标位置

  if (Vector3.Distance(transform.position, StartPoint.position) < 0.05f)

###### 碰撞检测，比对物体标签

 private void OnTriggerEnter2D(Collider2D collision)
    {
        if (collision.tag == "PinHead")
        {
            GameObject.Find("GameManager").GetComponent<GameManager>().GameOver();
        }
    }

###### 获取实例化的预制体上的标签

​    private pin pinCurrent;

	public void SpawnPin()
	{
	   pinCurrent=GameObject.Instantiate(pinPrefab,SpawnPoint.position,pinPrefab.transform.rotation).GetComponent<pin>();
	}

###### 关闭物体上的组件

 GameObject.Find("Circle").GetComponent<rotate_self>().enabled=false;

###### 用协程来实现结束动画

```
 IEnumerator GameOverAnimation()
    {
       while(true)
        {

            mainCamera.backgroundColor= Color.Lerp(mainCamera.backgroundColor,Color.red,speed_Animation*Time.deltaTime);
            mainCamera.orthographicSize=Mathf.Lerp(mainCamera.orthographicSize,4,speed_Animation*Time.deltaTime);
            if (Mathf.Abs(mainCamera.orthographicSize - 4) < 0.01f) break;
            yield return 0;
        }
        yield return new WaitForSeconds(0.2f);
        SceneManager.LoadScene(SceneManager.GetActiveScene().buildIndex);
    }
```

  StartCoroutine(GameOverAnimation());



## 坦克大战

### 注意

制作U2D项目时，把导入的图片的Texture Type 由default 改为Sprite(2D and UI)

把需要切割使用的图片的 Sprite Mode 属性 改为Mutiple

一般我们在awake方法里获得物体组件的引用

### 制作动画

方法1：选中多张图片，拖拽入Hierarchy窗口中，即可生成动画

### 实现角色转向时的图片变化

1.在角色转向时切换渲染的图片

```

```

2.在角色切换方向时让角色的图片沿着z轴旋转

```

```

#### 注意

Inspector面板中显示的Rotation是欧拉角度数，但是Instantiate方法需要传递一个四元数的值，这里我们用Quaternion.Euler()来把欧拉角转为四元数





### 碰撞检测

在进行碰撞检测时把刚体挂载在运动的物体上，避免刚体休眠

避免碰撞时物体沿z轴发生旋转：找到物体的Rigid body2D组件，其中的Constraints -> Freeze Rotation z 打勾即可

### 解决抖动问题

update和Fixedupdate的区别

Time.deltaTime的值会随电脑性能而改变（帧数），用Time.fixedDeltaTime则是使用固定物理帧

所以update函数每次执行所花费的时间是不同的，而Fixed update每次执行花费的时间相同



```
把之前player脚本中update函数体剪切到fix update中后，把Time.deltaTime改为Time.fixedDeltaTime即可

```

### 2D层级渲染问题

Spirite Renderer组件中的Sorting Layer（大层级）属性和Order in Layer（小层级）属性来控制。值越大越后渲染，物体在上层

### 子弹生成的方法

### 子弹的发射

transform.Translate()方法接收两个参数，如果第一个参数是以世界坐标系移动，那么第二个参数可填可不填，如果第一个参数是以自身为参照移动，第二个参数必须为Space.World

### 设置子弹发射间隔

### 碰撞检测

通过标签判断物体

### 播放爆炸动画

### 播放tank的生成动画

Invoke方法

### 使用单例模式来实现玩家的复活

### OnTriggerEnter2D调用两次问题

修复自己的子弹对基地造成伤害的bug

把地图初始化单独封装成一个方法

用invoke方法让失败界面延迟显示

使用audio.source组件添加音效AudioClip

拓展：

帧动画实现开始ui的移动

InputManager

### 自适应屏幕缩放

canvas-> canvas Scaler->UI Scale Mode ->Scale with Screen Size

### 实例化预制体的两种方法

Instantiate和Resource.Load







## Unity中的动画系统和TImeLine













## unity常用API







## C#高级技巧

解决多线程中资源访问冲突问题（使用锁）、



### 字符串的常用方法和字符串格式化

1、CompareTo()方法，比较字符串的内容 

2、Replace()用另一个字符或者字符串替换字符串中给定的字符或者字符串 

3、Split()在出现给定字符的地方，把字符串拆分称一个字符串数组 

4、SubString()在字符串中检索给定位置的子字符串 

5、ToLower()把字符串转换成小写形式

 6、ToUpper()把字符串转换成大写形式 

7、Trim()删除首尾的空白 

8、Concat()方法，合并字符串 - 静态方法 

9、CopyTo()方法，把字符串中指定的字符复制到一个数组中

 10、Format()方法，格式化字符串 - 静态方法 https://www.cnblogs.com/net-sky/p/10250880.html https://www.runoob.com/csharp/csharp-string.html https://docs.microsoft.com/zh-cn/dotnet/api/system.string.format? view=net-5.0 

11、IndexOf()方法，取得字符串第一次出现某个给定字符串或者字符的位置

12、IndexOfAny()方法，

13、Insert()把一个字符串实例插入到另一个字符串实例的制定索引处

14、Join()合并字符串数组，创建一个新字符串

























