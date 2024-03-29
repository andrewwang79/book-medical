# 图像识别
* 识别，分割，配准

## 识别

## 分割
* [图像多label分割](https://blog.csdn.net/jancis/article/details/106209808)

## 配准
* [医学图像配准技术综述](https://zhuanlan.zhihu.com/p/267339046)
* [3DSlicer多模态图像配准教程](http://www.360doc.com/content/22/0311/11/66272086_1021038063.shtml)
* [3DSlicer下图像的配准与融合（一）单模态图像的配准和融合](http://www.medtion.com/info/18758.jspx)

### 刚性配准
> 给定两个点集，刚性配准会产生一个刚性变换矩阵，该变换矩阵将一个点集映射到另一个点集上，刚性变换定义为不改变任何两点之间距离的变换，一般这种变换只包括平移和旋转。
在术中导航中，刚性配准常通过在CT和患者身上都存在且明确可辨的点进行配准，常用植入骨内的配准钉、明确的解剖标志点例如支气管的隆突点。

* ICP配准算法
    1. 首先进行粗配准，初始化旋转平移矩阵  
    1. 对两组点集寻找最近对应点
    1. 根据对应点利用SVD分解计算新的旋转平移矩阵
    1. 对点集进行旋转平移变换，得到的新点集再和目标点集计算对应点
    1. 重复2-4，直到迭代次数或者变化量达到阈值

* [矩阵奇异值分解（SVD）](https://zhuanlan.zhihu.com/p/480389473)
