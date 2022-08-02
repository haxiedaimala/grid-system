# 栅格系统说明


https://haxiedaimala.github.io/grid-system/

## 思路
1. 将容器`.container`自然的分成12列，通过媒体查询浏览器的窗口宽度，进而使其容器在不同的窗口大小，占据不同的列数
2. 每一列的类名都是`col-*`。例如`col-1`意为占据容器的1/12，即calc（calc（1 / 12） * 100%）
3. 总共有五个栅格等级，每个响应式分界点隔出一个等级：
- 特小.col-
- 小.col-sm-*
- 中.col-md-*
- 大.col-lg-*
- 特大（大、特大也可以称为宽、超宽）.col-xl-*
4. 元素根据布局，占据不同的列数，但难免会处于属于同一行内，因此为了能够满足在一行内放置，需要这一行中给12列都设置float：left
5. 给不同.col-*的列设置不同百分比宽度

## 步骤
1. 声明不同窗口下的媒体查询

![image](https://user-images.githubusercontent.com/90816853/157893718-d0d2a39e-e181-408d-b171-e5631f8fc00e.png)

- `@media (min-width:xxx)` 
min-width指的是大于等于xxx宽度，因此不同的媒体查询需要按照宽度**由小至大**写下样式，使用类名，也同样需要遵循**由小至大**
- `@media (max-width:xxx)`
max-width指的是小于等于xxx宽度，因此不同的媒体查询需要按照宽度**由大至小**写下样式，使用类名，也同样需要遵循**由大至小**
2. 在不同的媒体查询内容里，需要让12列的类名都设置：`float:left;`,使其能够让元素一行展示
3. 设置占据不同列数的宽度百分比，计算公式为 占据列数/12*100%

## 使用步骤
1. 需要在同一行的元素，根据布局，考虑在不同窗口大小的情况下占据的列数
2. 给元素添加不同窗口大小下、占据列数的类名
3. 给添加类名的父元素进行清除浮动

**注意**
- 元素的多个类名需要按照窗口宽度由小到大的类名进行排序




