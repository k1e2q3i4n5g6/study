
# <details><summary><span id='stop1'>1. 已解决</span></summary>1. [跳转到已解决仍有疑问](#stop2)<br>2. [跳转到未解决](#stop3)</br></details>
### [问题1.1](#1.1)
### [问题1.1](#1.2)
==下面是模板==

<h2 id='1.1'>问题描述</h2>

***

### 产生原因：

***

### 思考过程：

***

### 解决办法：

***

### 补充：

***

### [返回已解决](#stop1)


<h2 id='1.2'>问题描述</h2>

***

### 产生原因：使用clip反推提示词时出现以下报错!\[clip报错]![Snipaste_2024-12-18_17-51-02.png]

***

### 思考过程：没有思考直接去搜索，没解决，最后回来看报错提示，找源码，因为是下载的问题想必应该有缓存文件，命令行里也看不出在下的什么，直接根据提示去找clip相关的东西最后找到一个clip_model_name的变量指向vit-l/14!\[clip报错1]![Snipaste_2024-12-18_20-13-33.png]在interrogate.py里并没有找到指向它的链接，去提示里给的第二个文件里找到了下载地址!\[clip报错2]![Snipaste_2024-12-18_20-14-48.png]下载来放哪里，最后就是要找下载了百分之一的缓存文件在哪文件里搜到在用户目录下C:\Users\mwh12\.cache\clip!\[clip报错3]![Snipaste_2024-12-18_20-30-49.png]
***

### 解决办法：

***

### 补充：

***

### [返回已解决](#stop1)
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1










# <details><summary><span id='stop2'>2. 已解决仍有疑问</span></summary>1. [跳转到已解决](#stop1)<br>2. [跳转到未解决](#stop3)</br></details>

==下面是模板==

### [问题描述2.1](#2.1)

***

<h2 id='2.1'>问题描述</h2>

***

### 产生原因：

***

### 思考过程：

***

### 解决办法：

***

### 补充：

***

### [返回已解决仍有疑问](#stop2)

1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1
1











# <details><summary><span id='stop3'>3. 未解决</span></summary>1. [跳转到已解决](#stop1)<br>2. [跳转到已解决仍有疑问](#stop2)</br></details>

==下面是模板==

### [问题描述3.1](#3.1)
### [3.2 lora?全量微调？矩阵？](#3.2)
### [3.3 controlnet的openpose预处理器预览出现黑图](#3.3)
### [3.4高清放大算法选择]
***

<h2 id='3.1'>问题描述</h2>

***

### 产生原因：

***

### 思考过程：

***

### 补充：

***

### [返回未解决](#stop3)

<h2 id='3.2'>lora?全量微调？矩阵？</h2>

### 

***

### 产生原因：

***

### 思考过程：

***

### 解决办法：

***

### 补充：

***

### [返回已解决](#stop1)

***

<h2 id='3.3'>3controlnet的openpose预处理器预览出现黑图</h2>

***

### 产生原因：未知，同一张图早上用预处理器openpose能看到预览骨骼，晚上预览出现黑图，用其他预处理器正常显示预览

***

### 思考过程：图片没问题终端没报错,controlnet插件是最新的，删除预处理器重下还是没能出骨骼预览图

***

### 补充：

***

### [返回未解决](#stop3)

<h2 id='3.4'>高清放大算法选择</h2>

***

### 产生原因：1.生成过高分辨率可能会爆显存，2.生图时间过久

***

### 思考过程：

### 原图分辨率512*512
!\[高清放大原图]
![00000-3563668527.png]
### 放大后分辨率1024*1024
### 方法一：附加功能(不涉及重扩散)
!\[附加功能放大]
![00000.png]
### 方法二：图生图重绘幅度0.4，(图生图的放大算法可以在设置里面开启)
!\[图生图]
![00001-3563668527.png]
### 方法三：高分辨率修复(hires.fix)重绘幅度0.4，放大算法R-ESRGAN 4x+ Anime6B,这个方法=图生图+附加功能的不调分辨率只调放大算法？
!\[高分辨率修复(hires.fix)]
![00296-3563668527.png]
### 方法四：tiled diffusion插件图生图
!\[tiled diffusion插件]
![100000-3563668527.png]
### 方法五：controlnet_tile图生图？

### 方法六：controlnet_tile+controlnet_reference文生图or图生图
!\[controlnet_tile+controlnet_reference]

### 方法六：sd upscale脚本放大
!\[sd upscale脚本放大]
![200000-3563668527.png]

***

### 补充：

***

### [返回未解决](#stop3)




[clip报错]: /image\Snipaste_2024-12-18_17-51-02.png
[Snipaste_2024-12-18_17-51-02.png]: https://6f124247.cloudflare-imgbed-7p1.pages.dev/file/Snipaste_2024-12-18_17-51-02.png

[clip报错1]: /image/Snipaste_2024-12-18_20-13-33.png
[Snipaste_2024-12-18_20-13-33.png]: https://6f124247.cloudflare-imgbed-7p1.pages.dev/file/Snipaste_2024-12-18_20-13-33.png

[clip报错2]: /image\Snipaste_2024-12-18_20-14-48.png
[Snipaste_2024-12-18_20-14-48.png]: https://6f124247.cloudflare-imgbed-7p1.pages.dev/file/Snipaste_2024-12-18_20-14-48.png

[clip报错3]: /image\Snipaste_2024-12-18_20-30-49.png
[Snipaste_2024-12-18_20-30-49.png]: https://6f124247.cloudflare-imgbed-7p1.pages.dev/file/Snipaste_2024-12-18_20-30-49.png

[高清放大原图]: /image\00000-3563668527.png
[00000-3563668527.png]: https://6f124247.cloudflare-imgbed-7p1.pages.dev/file/00000-3563668527.png


[附加功能放大]: /image\00000.png
[00000.png]: https://6f124247.cloudflare-imgbed-7p1.pages.dev/file/00000.png

[图生图]: /image\00001-3563668527.png
[00001-3563668527.png]: https://6f124247.cloudflare-imgbed-7p1.pages.dev/file/00001-3563668527.png

[高分辨率修复(hires.fix)]: /image\00296-3563668527.png
[00296-3563668527.png]: https://6f124247.cloudflare-imgbed-7p1.pages.dev/file/00296-3563668527.png

[tiled diffusion插件]: /image\100000-3563668527.png
[100000-3563668527.png]: https://6f124247.cloudflare-imgbed-7p1.pages.dev/file/100000-3563668527.png

[controlnet_tile]: /



[controlnet_tile+controlnet_reference]: /


[sd upscale脚本放大]: /image\200000-3563668527.png
[200000-3563668527.png]: https://6f124247.cloudflare-imgbed-7p1.pages.dev/file/200000-3563668527.png