# 图像可视化
## 三维重建知识
* [CT三维重建](https://blog.csdn.net/fanhenghui/article/details/51036422)
* [可视化重建](https://www.iih.xin/productinfo/1410267.html)

| 字段 | 说明 |
| - | - |
| 多平面重建(MPR/Multiplanar Reconstruction) | 适用于任一平面的结构成像，以任意角度观察正常组织器官或病变，可以显示腔性结构的横截面以观察腔隙的狭窄程度、评价血管受侵情况、真实地反映器官问的位置关系等 |
| 曲面重建(CPR/Curved Plannar Reconstruction) | 在一个维度上选择特定的曲线路径，将该路径上的所有体素在同一平面上进行显示，可以一次评价曲度较大的结构如脾动脉、胰管、冠状动脉等管状结构的全长情况。但CPR所显示的不是正常的解剖结构和关系（它是把管状结构拉直了看），同时需要多个角度曲面重建以完整评价病变。 |
| 容积重建(VRT) | 形态及色彩逼真，绝对是CT三维重建中的“高富帅”，可以对动静脉血管、软组织及骨结构等进行立体塑形成像，也可以显示支气管树、结肠及内耳等结构，对于复杂结构的成像有一定优势 |
| 仿真内窥镜(VE） | 可以模拟各种内镜检查的效果，它是假设视线位于所要观察的管“腔”内，通过设定一系列的参数范围，即可看到管“腔”内的结构 |
| 表面阴影成像(SSD) | 将操作者的眼睛作为假设光源方向，投射到CT值在设定阈值以上的体素上则不再透过继续成像，仅呈现所有表面体素的集合立体图形，适用手显示CT值与其他结构相差较大的组织结构成像（就像是黑白的塑形图像），所以临床上主要用于显示骨骼病变或是结肠CT重建 |
| 最大密度投影(MP) | 将一定厚度（即CT层厚）中最大CT值的体素投影到背景平面上，以显示所有或部分的强化密度高的血管/器官，所以变化层厚会对图像产生影响 |
| 最小密度投影 (min/p) | 和MIP正好相反，反映的是一定层厚图像中CT值最低的体素，所以常用来显示胆道、气道等组织结构 |

* [面绘制和体绘制](https://blog.csdn.net/weixin_42352178/article/details/109201572)
* [医学序列图像定位线绘制基本方法介绍](https://blog.csdn.net/inter_peng/article/details/62046916)
* 正切：沿着轴向的切割，步长和spacing相同，轴状位显示和原始dicom单层显示相同，pixel取值没有经过插值
* 斜切：通常说的任意切，斜切面上像素点是通过插值得到的，一般原始ct图像时通过线性插值，mask图像是通过最近邻插值，还有些其它的插值方法，比如双线性插值，样条插值

### 曲面重建(CPR)
* [血管的三维重建](https://blog.csdn.net/wei_cheng18/article/details/77919115)
* [VTK实现曲面重建](https://beondxin.blog.csdn.net/article/details/117248736)
* [VTK曲面重建技术](https://blog.csdn.net/Ericohe/article/details/116189837)

### Mesh
* [Mesh网格知识](http://www.jmecn.net/tutorial-for-beginners/chapter-4-mesh.html)
* [点云到Mesh](https://blog.csdn.net/Architet_Yang/article/details/90049715)

### 配准
* [3DSlicer多模态图像配准教程](http://www.360doc.com/content/22/0311/11/66272086_1021038063.shtml)
* [3DSlicer下图像的配准与融合（一）单模态图像的配准和融合](http://www.medtion.com/info/18758.jspx)

## 渲染知识
### 渲染方式
* Onscreen: Onscreen refers to the case where the rendering results are presented to the users in a viewable window. On Linux, this invariably requires a running and accessible X server. The desktop Qt client can only operate in on-screen mode and hence needs an accessible X server.
* Offscreen: Offscreen simply means that the rendering results are not presented to the user in a window. On Linux, this does not automatically imply that an accessible X server is not needed. X server may be needed, unless VTK was built with an OpenGL implementation that allows for headless operation. This mode is not applicable to the desktop Qt client and is only supported by the command line executables.
* Headless: Headless rendering automatically implies offscreen rendering. In addition, on Linux, it implies that the rendering does not require an accessible X server nor will it make any X calls.

### 图像驱动
| 项 | 说明 | 资料 |
| - | - | - |
| OpenGL | 图形界的工业标准，其仅仅定义了一组2D和3D图形接口API，无实现 | http://www.opengl-tutorial.org/cn/ |
| GLSL | OpenGL Shading Language，可以理解成GPU指令的C语言 | [OpenGL着色语言GLSL中文手册](https://blog.csdn.net/hk_shao/article/details/82084274) |
| Mesa3D | OpenGL API的一种开源实现的图形库。显卡不支持OpenGL2.0也可使用 |  |
| DRI | Direct Rendering Infrastructure |  |

| 操作系统 | 窗口系统 | OpenGL实现 |
| :-: | - | - |
| Apple OS | AGL | Cocoa/NSGL |
| Linux | GLX | Mesa/GLX |
| Windows | WGL | WGL |
| 嵌入式平台 | EGL | OpenGL ES |
| 跨平台	 |  | GLFW，GLUT |

### Mesa
* 对接各种GPU硬件，将应用层对GL API的调用转换到对硬件GPU的调用上；
* 各种GL API的纯软实现，当没有可用的硬件时，它可以提供传软件的GL API的实现；
  * libgl1-mesa-dev：OpenGL实现库
  * libglu1-mesa-dev：gl Utilities库
  * libosmesa6-dev：off screen库

## 渲染方案
### 方案比对
| 项 | 技术 | 优势 | 劣势 |
| - | - | - | - |
| 后端渲染 | 无头渲染(Headless): (VTK+EGL)+websocket | 支持复杂操作，终端开发容易，**一套环境维护成本低** | **依赖网络带宽**，需要后端大量的内存和算力 |
| 前端-浏览器渲染 | Onscreen渲染: H5+js库 | 终端不同可复用 | **依赖终端的内存和算力**；复杂操作的支持度有限制 |
| 前端-客户端渲染 | Onscreen渲染: QT+VTK | 支持复杂操作 | **依赖终端的内存和算力**；**需做系统和环境兼容**；终端不同需重做，比如手机端要换QT |

### 后端渲染
* 相比前端渲染，后端渲染需要大量切图操作，其他功能都一样。切图有：
  * 预先切图：无编辑
  * 实时切图：实时编辑
* 需考虑：服务器要求，图像要求，网速要求
* Linux的4种渲染方式

| 项 | 速度 | 使用GPU | 说明 |
| - | - | - | - |
| CPU渲染 | 慢 | N |  |
| xvfb虚拟xServer | 慢 | Y | 从GPU到CPU拷贝图像速度非常慢 |
| VTK OSMESA(CPU软件驱动) | 慢 | Y |  |
| VTK EGL(GPU加速) | 快 | Y | libegl1-mesa-dev，基于镜像nvidia/opengl:1.2-glvnd-devel-ubuntu18.04 |

## 资料
### 公司
* [英库医疗科技](https://www.incool3d.com/)
* [微至云动](https://www.weiyunyingxiang.com/)
* [AccuNavi-A手术导航系统](http://www.uegmedical.com/cn/products/AccuNavi-A_Surgical_Navigation_System.html)
