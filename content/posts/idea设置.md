---
title: idea设置
aliases: 
tags:
  - idea
date: 2024-10-24
lastmod: 
time: 21:52
---
## 必要设置
### Maven
1. 配置maven的主目录（当下方显示处Version:版本号说明成功了）
2. 配置maven的配置文件，在`maven主目录/conf/settings.xml`，然后勾选Override之后，你会发现Local repository变成了maven配置文件内所配置的仓库地址。
3. 如果如果想自定义仓库地址，勾选Local repository的Override，然后就可以配置了。

![](../assets/Pasted%20image%2020241118170113.png)
### 自动编译
在Compiler中勾选上，就可以开启自动编译，在修改完代码后，会自动进行编译。
![](../assets/Pasted%20image%2020241121201955.png)

### 关闭自动更新
1. 点击菜单栏中的`File`选项
2. 在下拉菜单中选择`Settings`选项
3. 图片是弹出的弹窗，找到Updates，取消掉图中的勾选  

![|680](../assets/Pasted%20image%2020241025155756%201.png)
### 自动接受不信任的证书
问题：每一次打开idea都会弹出证书确认的弹窗
解决办法：把Server Certificates页面的第一个选型勾选上就可以了
![](../assets/Pasted%20image%2020241117193714.png)
## 基础设置
### 字体和主题
这里可以idea的主题和字体
![](../assets/Pasted%20image%2020241118164031.png)
### 编辑器字体
在font里可以选择合适的字体
![](../assets/Pasted%20image%2020241112200342%201.png)
### 编码
修改编码格式，最下边的一定要勾选
![](../assets/Pasted%20image%2020241118165254.png)
### 自动导包
自动导包的规则：在编写代码的时候，如果遇到需要导包的情况，而且只有一个包的情况下，会自动导入。
导包优化：自动删除无用的包
![](../assets/Pasted%20image%2020241121200708.png)

### 屏幕竖着的分割线
在选项卡栏中双击打开的文件，文件页面会变大，就会看到有一个竖着的分割线。取消下方截图中的选项，竖线就消失了。
![](../assets/Pasted%20image%2020241122162949.png)
### 方法之间的分割线
就是方法和方法中间会有一条线，看起来更容易分清楚方法
![](../assets/Pasted%20image%2020241121204339.png)
### ES6语法支持
下拉框内可以选择语法
![](../assets/Pasted%20image%2020241118171622.png)
### 代码补全模板
第一种玩法
![](../assets/Pasted%20image%2020241118171914.png)
第二种玩法
![](../assets/Pasted%20image%2020241118171959.png)
通过后缀的方式实现代码自动补全，常见的：

| 代码   | 效果                      |
| :--- | :---------------------- |
| psvm | 自动生成main函数              |
| .var | 自动为对象生成声明               |
| sout | 输出：System.out.println() |
| .if  | 生成if判断                  |
| .for | 生成循环，默认是高级for           |
| fori | 用普通for进行遍历              |
| .try | 生成try ... catch         |
## 打开springboot的run dashboard
先看下run dashboard是什么：
![](../assets/1314186-20180413093018664-88251637.png)
可以看到，这里可以同时显示多个springboot项目，非常方便。

默认情况下，idea的run dashboard是关闭的，当检测到你有多个springboot项目时会弹出提示框，询问是否打开。

如果我们想要自己打开，需要修改配置。
在你的idea的项目目录中，有一个.idea目录：
![](../assets/1526786924641.png)

其中，有一个workspace.xml：

![](../assets/1526786976776.png)

打开，搜索Rundashboard，找到下面这段：
![](../assets/1314186-20180413093746177-931677889.png)
然后在Component中添加下面的内容：
```xml
<option name="configurationTypes">  
    <set>  
        <option value="SpringBootApplicationConfigurationType" />  
    </set>  
</option> 
```
## 快捷键
- `ctrl + 空格` 提示快捷键
- `Alt + Insert`（Code|Generate…）可以创建类里面任何字段的getter与setter方法
- `ctrl + D` 复制当前行
- `ctrl + Y` 删除当前行
- `ctrl + alt + L` 格式化
- `ctrl + alt + O` 导包
- `ctrl + alt + 左/右` 退回到上一次操作的地方
- `ctrl + alt + 上/下` 将代码向上/下移动一行
- `ctrl + H` 罗列类的继承关系
- `ctrl + shift + alt + U` 显示类继承结构图
- `双击shift` 查找所有的文件
- `ctrl + N` 查找类
- `ctrl + shift + N` 文件
- `ctrl + /` 单行注释
- `ctrl + shift + /` 多行注释
- `alt + shift + 上下箭头` 多行注释