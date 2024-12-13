<h1 id=1>使用h1标签跳转到这</h1>

# 多尝试嵌套
# 注意标签之间的缩进
***
# 1.标题
#号可以表示1~6级标题,一级标题对应一个#,二级标题对应两个#,以此类推。打完所有#号后要接空格

实例如下
# 一级标题
## 二级标题
***
# 2. 表格
用|分隔单元格,-分隔表头和其他行,:-设置左对齐,-:设置右对齐,:-:,设置居中对齐。

实例如下:

|表头一左对齐|表头二右对齐|表头三居中对齐|
|:-|-:|:-:|
|单元格填充内容和表头一左对齐|单元格填充内容和表头二右对齐|单元格填充内容和表头三居中对齐|

***
# 3. 折叠内容(展开收起黑三角)
details:折叠语法标签
summary:折叠语法展示的摘要
<details><summary>摘要(点击展开内容)</summary>详情(这是展开的内容)</details>

***
# 4. 转义符
## \

# 5. 图片
## 语法格式 !\[属性文本](图片地址)
## 本地图片地址需要用斜杠'/'，不是用反斜杠'\\'
实例如下
!\[](C:/Users/mwh12/Desktop/study/image/Snipaste_2024-12-05_13-06-04.png)
![Snipaste_2024-12-05_13-06-04.png](https://6f124247.cloudflare-imgbed-7p1.pages.dev/file/Snipaste_2024-12-05_13-06-04.png)
问题：不显示图片
!\[](C:/Users/mwh12/Desktop/study/image/Snipaste_2024-12-05_13-57-06.png)
![Snipaste_2024-12-05_13-57-06.png](https://6f124247.cloudflare-imgbed-7p1.pages.dev/file/Snipaste_2024-12-05_13-57-06.png)
解决
!\[](C:/Users/mwh12/Desktop/study/image/Snipaste_2024-12-05_14-28-18.png)
![Snipaste_2024-12-05_14-28-18.png](https://6f124247.cloudflare-imgbed-7p1.pages.dev/file/Snipaste_2024-12-05_14-28-18.png)

# <span id=2>使用span标签跳转到这</span>

# 6. 链接
语法格式：\[连接名称](链接地址)
实例如下
[我的github仓库](https://github.com/k1e2q3i4n5g6?tab=repositories)

# 7. 列表
## 有序语法格式：每个列表项前添加数字后面紧跟着.和空格。无序列表语法格式：每个列表项前添加-后面紧跟着空格。缩进一个或多个列表项可创建嵌套列表。
有序列表实例如下：

1. 第一个项目
2. 第二个项目
    1. 第二个项目的子项目、
3. 第三个项目

无序列表实例如下：
- 第一个项目
- 第二个项目
    - 第二个项目的子项目
- 第三个项目  
*** 
# 8. 页内跳转
## 链接语法结合html标签
实例如下：
方法一：
使用h标签
[使用h1标签跳转](#1)h后跟的数字越小字体越大，1对应markdown语法中的#，2对应markdown语法中的##，以此类推。写完h标签要回车空一行。
方法二：
[使用span标签跳转](#2)此法跳转字体大小由markdown语法决定

已知区别：
<details><summary><h3>在折叠语法中小三角在摘要上一行</h3></summary>内容</details>

<details><summary><span>在折叠语法中小三角和摘要同一行</span></summary>内容</details>

***
# 9. 引用
## 语法 > 
实例如下：
> 这里写下引用了谁的文章
> 引用中可以这样换行

# 10. 标签内换行
## 使用\<br>标签
实例如下：
<details>
<summary>展开内容(摘要)</summary>

- <details>
    <summary>展开内容(摘要)</summary>

    第一项<br>第二项</br>
    
  </details>

</details>

# 11. 分割线
## 语法 ***
实例如下：
***

# 12. 使用变量给链接赋值
## 
实例如下：
\[我的github仓库]\[github]
[我的github仓库][github]
!\[这是我图床里的一张图片]\[image]
![这是我图床里的一张图片][image]
\[github]: https://github.com/k1e2q3i4n5g6 给变量github赋值一个链接，一般放文本最后边，使源文本看起来更简洁

\[image]: https://6f124247.cloudflare-imgbed-7p1.pages.dev/file/Snipaste_2024-12-05_13-06-04.png 使用image变量代替图片并给其赋值图片链接，一般放文本最后边，使源文本看起来更简洁

[github]: https://github.com/k1e2q3i4n5g6
[image]: https://6f124247.cloudflare-imgbed-7p1.pages.dev/file/Snipaste_2024-12-05_13-06-04.png

---

# 13. 高亮文本
## 语法：\==高亮文本==
实例如下：
==高亮文本==

---

# 14. 文本格式化
## \*\*加粗\*\* 英文状态下的*
实例如下：
**加粗**

\_倾斜\_
实例如下：
_倾斜_
倾斜语法疑似不能和标题语法混用

## \~~删除线\~~
实例如下：
~~删除线~~