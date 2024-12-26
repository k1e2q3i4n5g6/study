# <center>在[这里][课程]学习</center>
# 2024-12-11 14:35:38
<标签名 属性名="属性值" 属性名="属性值">
在html5中属性名和属性值一样可以简写为一个单词


### 网页制作思路
从上到下，先整体后局部
### 快捷键；
ctrl+enter换行、注释和删除注释快捷键ctrl+/
选中左边表示行数的数字可对标签做删除、复制操作
### 标签关系：
嵌套、并列
### 注释：
\<!-- 里边写的内容只有在源代码里才能看到 -->，vscode中注释和删除注释的快捷键是ctrl+/得在html文件中使用此快捷键。 

---

## 双标签：
\<strong>字体加粗\</strong>

\<html>整个网页\</html>
\<head>网页头部，存放给浏览器看的\</head>
\<title>网页标题，浏览器标签上看到的标题就是\</title>
\<body>主体，给用户看的</body>
\<p>段落标签\</p>
\<h1~6> 标题标签：h标签有1到6级数字越大显示的标题越小\</h1~6>
\<a href="地址，属性值写#表示空链接，#也可以在其他有id属性标签id值的前边起到页内跳转的作用" target=_blank>超链接标签\</a>
target=_blank：在新窗口打开链接
\<audio src="地址，支持mp3，ogg，wav">音频标签\</audio>
\<video src="地址"，支持mp4，webm，ogg>
|属性|作用|说明
|:-:|:-:|:-:
|src|地址|必须属性
|controls|控制面板
|loop|循环
|autoplay|自动播放，浏览器一般会禁用
|muted|静音|想要视频自动播放(autoplay)得配合静音属性使用
### 文本格式化标签突出重点
    <strong>加粗重点</strong>
    <em>倾斜重点</em>
    <ins>下划线重点</ins>
    <del>删除线重点</del>
    <b>加粗</b>    
    <i>倾斜</i>
    <u>下划线</u>
    <s>删除线</s>




---

## 单标签：
\<br>换行，源代码里敲回车，在浏览器中不能换行因为浏览器不支持回车键换行得使用换行标签。
\<hr>水平线

### 图像标签
\<img src="图片地址">，src用于指定图像名称和地址

图像属性：
|属性|作用|说明
|:-:|:-:|:-:|
|src|地址|必须属性
|alt|替换文本|图片无法显示时显示的文字|
|title|提示文本|鼠标悬停在图像上边时显示的文字|
|width|宽度|默认等比例缩放
|height|高度|默认等比例缩放

vscode中快速生成骨架，在html文件中输入英文状态的!配合tab/enter键即可

---

[课程]: https://www.bilibili.com/video/BV1kM4y127Li/?spm_id_from=333.1007.top_right_bar_window_custom_collection.content.click&vd_source=ca0a9d1a85af002ad62c5c3e45f402c3

