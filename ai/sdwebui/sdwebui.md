# <center>在[这里][地址]学习</center>

## <ins>提示词</ins>
- ### ==提示词权重：==
  - ### 提示词越靠前权重越大
  - ### <ins>(prompts:1.5)1.5倍权重、(((prompts))) 1.1*1.1*1.1倍、{{prompts}} 1.05*1.05倍、\[\[\[prompts]]] 0.9*\*0.9*0.9倍</ins>
  - ### 并列：混合|混合 prompts、次序：[先生成|后生成]prompts、进程：(达到百分之八十前生成:达到百分之八十后生成:0.8)、[到百分之八十停止生成prompts::0.8]
  - > ### BREAK这个词会直接占满当前剩下的token，后面的提示词将在第二段clip中处理。AI在生成图像的时候会将一些提示词的特征放到其他的物品上，例如我在提示词中写了white clothes和Flower background，那么很有可能在衣服上出现花的装饰。如果我们不想在衣服上出现花的装饰，那么比较简单的方法就是把这两个词放到两段clip中处理
  - ### 负面提示词不是越多越好，负面提示词多少都会对画面产生影响

### [原理][引用1]：
### 关于自己的理解：
### 输入的提示词会被文本编辑器(clip)转换成可以被u-net读取的embedding形式，潜空间里u-net读取到文本后根据采样方法、CFG、controlnet等为随机种子(seed)生成的噪声图减去预测到的噪声得出一张图像样本，在潜空间里多次(steps)重复此过程后最终生成一张潜空间图片，潜空间里的图片需要VAE进行转码到像素空间才可以被人看到。
!\[原理1]
![Snipaste_2024-12-16_12-40-07.png]
!\[原理2]
![Snipaste_2024-12-16_12-47-41.png]
### 更正：图二是下边应该是使用当前种子生成噪声图
  - > ①首先我们输入的提示词（prompt）会首先进入TE（TextEncoder），而clip就是stable diffusion所使用的TE。TE这部分的作用就是把tag转化成U-net网络能理解的embedding形式，当然了，我们平时用的emb模型，就是一种自然语言很难表达的promot。（简单的说就是将“人话”转换成AI能够理解的语言）
  ②将“人话”转换成AI能够理解的语言之后，U-net会对随机种子生成的噪声图进行引导，来指导去噪的方向，找出需要改变的地方并给出改变的数据。我们之前所设置的steps数值就是去噪的次数，所选择的采样器、CFG等参数也是在这个阶段起作用的。（简单的说就是U-net死盯着乱码图片，看他像什么，并给出更改的建议，使得图像更加想这个东西）
  ③一张图片中包含的信息是非常多的，直接计算会消耗巨量的资源，所以从一开始上面的这些计算都是在一个比较小的潜空间进行的。而在潜空间的数据并不是人能够正常看到的图片。这个时候就需要VAE用来将潜空间“翻译”成人能够正常看到的图片的（简单的说就是把AI输出翻译成人能看到的图片）
  经过以上三个步骤，就实现了“提示词→图片”的转化，也就是AI画出了我们想要的图片。这三个步骤也就对应了模型的三个组成部分：clip、unet、VAE


---

### 内容型提示词：[主体](#主体)、[背景](#背景)、[构图](#构图)、[环境光](#环境光)
### 标准化提示词：[风格](#风格)、[媒介](#媒介)、[颜色氛围](#颜色氛围)、[画面清晰度](#画面清晰度)

---

### <span id='画面清晰度'>画面清晰度</span>

---

### <span id='主体'>主体：对主体的描述</span>
<details><summary><strong>1. 外貌</strong></summary>


- <details><summary>身体</summary>

  1. 状态
  2. 皮肤
  3. 胸
  4. 腰
  5. 腹
  6. 臀
  7. 腿
  8. 脚
  </details>

- <details><summary>发型发色</summary>

  0. 耳朵前面叫鬓角，盖额头的叫刘海，脖子后面叫马尾，头发前端叫发梢
  1. 发型
  2. 发色
  3. 发质
  4. 厚度
  5. 长度

  </details>

- <details><summary>五官特点</summary>

  1. 眉毛
  2. 眼睛
  3. 耳朵
  4. 鼻子
  5. 嘴巴
  </details>


- <details><summary>服装穿搭</summary>

  1. 外套
  2. 裤子
  3. 鞋子
  4. 袜子
  5. 内衣
  6. 内裤
  7. 装饰品：手套、戒指、猫耳、腿环、小尾巴
  </details>

</details>


<details><summary><strong>2. 神态</strong></summary>
</details>



<details><summary><strong>3. 肢体动作</strong></summary>

- <details><summary>整体</summary>
  
  1. 站
  2. 躺(睡、卧)
  3. 趴
  4. 坐
  5. 蹲
  6. 走
  7. 跪
  </details>

- <details><summary>头部</summary>
  </details>

- <details><summary>手臂</summary>

  1. 大臂
  2. 小臂
  </details>

- <details><summary>手</summary>

  1. 大拇指
  2. 食指
  3. 中指
  4. 无名指
  5. 小拇指
  </details>

- <details><summary>胸部</summary>

  1. 左胸(左乳房)
  2. 右胸(右乳房)
  </details>

- <details><summary>腰部</summary>
  </details>

- <details><summary>腹部</summary>
  </details>

- <details><summary>臀部</summary>
  </details>

- <details><summary>腿</summary>

  1. 大腿
  2. 小腿
  </details>

- <details><summary>足</summary>
  </details>



</details>

---

### <span id='背景'>背景：地点</span>

<details><summary><strong>地点</strong></summary>

- 室内
- 室外

</details>

### 2. 大场景
### 3. 小细节

---

### <span id='环境光'>环境光</span>
### 1. 白天黑夜 
### 2. 特定时段
### 3. 光环境
### 4. 天空

---

### <span id='构图'>构图：图像的组成和视角</span>

<details><summary><strong>1. 景别</strong></summary>

  - ### 特写镜头extreme close-up 
  - ### 近景close-up 
  - ### 中近景medium close-up 
  - ### 中景 medium shot 
  - ### 全景long shot、full shot 
  - ### 中全景medium full shot
  - ### 定场镜头establishing shot (交代地点的镜头，通常是视野宽阔的远景)
  - ### 主观视角point-of-view 
  - ### 西部牛仔镜头，见到上半身以及大腿cowboy shot
  - ### 上半身upper body 
  - ### 全身full body 
</details>
    


<details><summary><strong>2. 拍摄方向</strong></summary>

  - ### 正面front view 
  - ### 左右对称bilaterally symmetrical 
  - ### 侧面side view 
  - ### 后面back view 
  - ### 从上拍攝from above 
  - ### 从下拍攝from below 
  - ### 后拍from behind 
  - ### 广角镜头wide angle view  
  - ### 鱼眼镜头fisheyes view 
  - ### 微距macro view 
</details>


<details><summary><strong>3. 镜头高度</strong></summary>

  - ### 俯视 overhead shot 
  - ### 由上向下top down 
  - ### 鸟瞰bird's eye view 
  - ### 高角度high angle 
  - ### 微高角度slightly above 
  - ### 水平拍攝straight on 
  - ### 英雄视角hero view  
  - ### 低视角low view  
  - ### 仰视worm's eye view 
  - ### 自拍selfie 
</details>

---

### <span id='风格'>风格：画风</span>

---

### <span id='媒介'>媒介：绘画使用的工具</span>

---

### <span id='颜色氛围'>颜色氛围：改变色调</span>

---

### ==实例如下==

### 主体：girl   对主体的描述：身穿black sweater


<details><summary><strong>扩展插件</strong></summary>

- <details><summary>图像浏览器</summary>

  1. [image browser1][image browser1]
  2. [image browser2][image browser2]



ss

</details>



</details>

### 初识别界面

<!-- ![interface_1] -->
![Snipaste_2024-12-14_21-47-52.png]

<!-- ![interface_2] -->
![Snipaste_2024-12-14_22-18-05.png]


### embedding模型：可以被理解为一组提示词的集合(打包提示词)，用来减轻用户编写提示词的麻烦

### 让sd生成某游戏的某个角色，正常要输入大量的提示词加以修改，才能达到我们想要的效果，使用embedding模型就不用这么麻烦，只需要调用它就可以。

> embedding是针对textencode进行预训练的权重集合
> lora是针对textencode+u-net进行预训练的权重集合
### lora模型：？提取特征信息？参考对模型的微调、矩阵知识、全量微调、Lora训练少量参数

#### 一般来说：embedding和lora可以做同一件事时优先选lora

---


### VAE：AI原本的生成图不是人能看的正常图片，VAE的作用就是把AI的这部分输出转化为人能够看的图片

---
### 低分辨率出图后再进行以下操作
## 图生图
### ==原理：通过增加噪声的方法抽象化一张又一张图片，通过去噪的方法具象化一张又一张图片==

### 重绘幅度：重绘幅度越大越接近模型，重绘幅度越小越接近原图

## 三种放大修复方案
1. ### 高分辨率修复hires.fix (本质就是把低分辨率图像图生图，先生成一张低分辨率图像，在根据该图生成一张高分辨率图像)
2. ### 图生图里面调比例，放大算法在设置里找到!\[interface_3]![Snipaste_2024-12-15_14-08-12.png]，脚本放大!\[interface_4]![Snipaste_2024-12-15_14-34-01.png]
3. ### 附加功能：可以理解为一个重绘幅度为0的高清修复


## 1. 关于差异随机种子
### 给出随机种子A，差异随机种子B，就是两个不同的种子，差异强度越高种子A就会越像种子B?，单独调整宽度或高度都没用？可用于融合？

!\[差异随机种子1]
![Snipaste_2024-12-16_13-19-55.png]

!\[差异随机种子2]
![Snipaste_2024-12-16_13-26-01.png]

!\[差异随机种子3]
![Snipaste_2024-12-16_13-27-27.png]

### 2.关于controlnet
### [controlnet模型]
### 开启预览需要下载[controlnet预处理器]放到extensions\sd-webui-controlnet\annotator\downsloads文件夹下对应预处理器名称的文件夹即可(一般需要新建文件夹名为对应预处理器名称)

### ==openpose==
### 该预处理器用于姿势、面部表情、手、当涉及到肢体交叠时准确性会降低，可以结合depth使用
### 线稿提取
### - 按提取细节多到少lineart>canny>softedge>scribble>mlsd
> ### 线稿月精细对画面控制力度越大，但ai能发挥的空间小
> ### 线稿越粗，虽然对画面不可控，但留给ai发挥空间更大
> ### 想让画面接近参考图选精细线稿
> ### 想让画面与参考图差别更大，选粗略线稿

### 元素、深度、光影
### 1. segmentation语义分割
> ### 识别参考图元素类型。位置和大概轮廓，并把他们用不同的颜色标记出来，不能识别细节，常用于构图
### 2. depth深度
> ### 该预处理器传递的是空间信息，黑色为远距离，白色为近距离，ai根据参考图生成拥有> 同样景深的画面，使画面更有层次感，拉开主体与背景的关系常被用于大场景的绘制
### 3. normalmap法线贴图
> ### 使用参考图片显示三维模型细节，尤其是因为三维模型因灯光而产生的诸多信息，可用于控制画面轮廓，光影关系
### 细节调整
### 1.tile分块
> ### 忽略原图细节生成新的细节，提示词与画面内容不符时会忽略提示词，按照参考图本身的语义绘制
### 2.inpaint(局部重绘)



## 关于[c站]

!\[c站_]
![Snipaste_2024-12-15_12-15-47.png]

[地址]: https://www.bilibili.com/video/BV1As4y127HW/?spm_id_from=333.1007.top_right_bar_window_custom_collection.content.click&vd_source=ca0a9d1a85af002ad62c5c3e45f402c3

[image browser1]: https://github.com/AlUlkesh/stable-diffusion-webui-images-browser.git
[image browser2]: https://github.com/zanllp/sd-webui-infinite-image-browsing.git

[interface_1]: /image/Snipaste_2024-12-14_21-47-52.png
[Snipaste_2024-12-14_21-47-52.png]: https://6f124247.cloudflare-imgbed-7p1.pages.dev/file/Snipaste_2024-12-14_21-47-52.png

[interface_2]: /image/Snipaste_2024-12-14_22-18-05.png
[Snipaste_2024-12-14_22-18-05.png]: https://6f124247.cloudflare-imgbed-7p1.pages.dev/file/Snipaste_2024-12-14_22-18-05.png

[interface_3]: /image\Snipaste_2024-12-15_14-08-12.png
[Snipaste_2024-12-15_14-08-12.png]: https://6f124247.cloudflare-imgbed-7p1.pages.dev/file/Snipaste_2024-12-15_14-08-12.png

[interface_4]: /image\Snipaste_2024-12-15_14-34-01.png
[Snipaste_2024-12-15_14-34-01.png]: https://6f124247.cloudflare-imgbed-7p1.pages.dev/file/Snipaste_2024-12-15_14-34-01.png

[c站]: https://civitai.com/

[c站_]: /image\Snipaste_2024-12-15_12-15-47.png
[Snipaste_2024-12-15_12-15-47.png]: https://6f124247.cloudflare-imgbed-7p1.pages.dev/file/Snipaste_2024-12-15_12-15-47.png

[引用1]: https://docs.qq.com/doc/p/4d05d5a8f1282662dd5b7e526ecfe8d8ecbcee17?nlc=1

[原理1]: /image\Snipaste_2024-12-16_12-40-07.png
[Snipaste_2024-12-16_12-40-07.png]: https://6f124247.cloudflare-imgbed-7p1.pages.dev/file/Snipaste_2024-12-16_12-40-07.png

[原理2]: /image\Snipaste_2024-12-16_12-40-07.png
[Snipaste_2024-12-16_12-47-41.png]: https://6f124247.cloudflare-imgbed-7p1.pages.dev/file/Snipaste_2024-12-16_12-47-41.png

[差异随机种子1]: /image\Snipaste_2024-12-16_13-19-55.png
[Snipaste_2024-12-16_13-19-55.png]: https://6f124247.cloudflare-imgbed-7p1.pages.dev/file/Snipaste_2024-12-16_13-19-55.png

[差异随机种子2]: /image\Snipaste_2024-12-16_13-26-01.png
[Snipaste_2024-12-16_13-26-01.png]: https://6f124247.cloudflare-imgbed-7p1.pages.dev/file/Snipaste_2024-12-16_13-26-01.png

[差异随机种子3]: /image\Snipaste_2024-12-16_13-27-27.png
[Snipaste_2024-12-16_13-27-27.png]: https://6f124247.cloudflare-imgbed-7p1.pages.dev/file/Snipaste_2024-12-16_13-27-27.png


[controlnet模型]: https://huggingface.co/lllyasviel/ControlNet-v1-1/tree/main

[controlnet预处理器]: https://huggingface.co/lllyasviel/Annotators/tree/main

