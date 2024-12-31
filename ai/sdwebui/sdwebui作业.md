## 提示词
### 生成
1. purple_hair
2. black_hair
3. white_hair

每种组合生成两遍


1. 选一个作为主体的发色
2. 选两个颜色搭配作为主体的发色
3. 选两到三个颜色作为主体的发色
4. 让颜色之间有and关系

#### 生成
1. purple_long_hair
2. purple_short_hair
3. black_long_hair
4. black_short_hair
5. white_long_hair
6. white_short_hair

对比blush权重为0.8、0.9、1.05、1.1、1.2的差距

0~0.6绘制white_glove、0.6~1绘制black_glove

混合渲染白色头发和紫色头发，使白色头啊权重提升1.1、紫色头发权重提升1.2

进程到0.6停止渲染blue_eyes

到第十步停止生成wedding_dress

不要渲染table

进程到0.2开始绘制window直到结束

进程到0.2开始绘制stool直至进程0.8

渲染一张白色发木制的stool

不要生成白色curtains只要黑色curtains 



## 脚本

比较同一张噪声图经过不同采样器采样的最终表现