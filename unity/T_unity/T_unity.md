# T_unity



## unity基础

### 3D数学

Mathf和Math
//Math是c#中封装好的用于数学计算的工具类一位于system命名空间中
//Mathf是unity中封装好的用于数学计算的工具结构体_位于UnityEngine命名空间中
//他们都是提供来用于进行数学相关计算的

区别
//Mathf和Math中的相关方法几乎一样
//Math是C#自带的工具类主要就提供一些数学相关计算方法
//Mathf是unity专门封装的，不仅包含Math中的方法，还多了一用于游戏开发的方法
//所以我们在进行Unity游戏开发时
//使用Mathf中的方法用于数学计算即可．



插值运算 -Lerp

Lerp方法:result =Mathf.Lerp(start , end , t);

​		 reuslt=start + (end -start)*t; //t的范围为0-1

用法：1.

每帧改变start的值,变化速度先快后慢，位置无限接近但是不会到达end位置
start=mathf.Lerp（start,10,Time．deltaTime)；
用法2

//每帧改变t的值一变化速度匀速，位置每帧接近，当t>=1时，得到结果
time+=Time.deItaTime;
resultMathf．Lerp(starts,end,Time.deltaTime);









 视口坐标系(详见入门篇的transform组件)

//摄像机上的 视口范围#
 坐标转换相关

//世界转本地
//this.transform.InverseTransformDirection//this.transform.InverseTransformPoint//this .transform.InverseTransformVector
//本地转世界
//this.transform.TransformDirection//this.transform.TransformPoint//this .transform.TransformVector
//世界转屏幕
//Camera.main.WorldToScreenPoint
//屏幕转世界
//Camera.main.screenToworldpoint;