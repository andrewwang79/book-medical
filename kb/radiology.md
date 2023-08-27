# 放射科

## 术语
### 名词
| 英文 | 中文 | 说明 |
| :-: | - | - |
| patient | 病患 |  |
| study | 检查 |  |
| series | 影像序列 |  |
| instance | 单张图片 |  |
| nodule | 结节 | 生物体表面或内部组织中圆形的小突起 |
| nidus | 病灶 | 疾病集中的部位或是综合病症、感染的主要部位 |
| registration | 影像配准 |  |

### 医学成像
| 名称 | 说明 | 数据的物理原理 |
| - | - | - |
| B超 | 发出超声波，然后用反射的回声来画像的检查方式 |
| 核磁共振(MRI/magnetic resonance imaging) | 是利用一个强大的磁场，让身体里的氢原子，先排好队再解散，接受这期间的电磁波信号，再给身体内部画像 | 磁共振信号 |
| DR(数字化放射成像) |  |  |
| X光 | 用X光给你的身体拍了一张照片的检查方式。所以也叫拍片子 |  |
| 计算机断层扫描(CT/computed tomography) | 实际上也是用X光给身体拍照片的检查方式。不过不是拍一张，而是要拍很多张，一层一层地查。 | X线衰减系数，使用扫描式X射线进行成像 |
| CT平扫(NCCT/Noncontrast CT) |  |  |
| 螺旋CT |  |  |
| CTA(CT血管成像/CT Angiography) | 增强CT。将动脉血管显影的药物注射到静脉内，利用CT机扫描获得的图像数据进行处理后，使头颈、心脏、肺动脉、主动脉等血管显影成像 |  |
| CTP(CT灌注成像/CT Perfusion) | 增强CT。[原理](https://blog.csdn.net/chenran187906/article/details/110387736) |  |
| DSA(数字减影技术/Digital subtraction angiography) | 将注入造影剂前后拍摄的两帧X线图像通过数字化处理(减影、增强和再成像)，把不需要的组织影像删除掉，只保留血管影像 |  |
| [锥形束CT(CBCT/Cone Beam CT)](https://www.cn-healthcare.com/articlewm/20220531/content-1367848.html) | 西门子的成像视野是16立方厘米。主要应用于口腔、颌面部、耳鼻喉、乳腺等局部区域，常用于牙科、骨科、耳鼻喉科等领域 <br> [螺旋CT、增强CT、CBCT](https://www.sohu.com/a/233743240_100130383) | 使用锥形束的X射线进行成像 |
| [C形臂(C型的机架)](https://zhuanlan.zhihu.com/p/265023777) | 大C(DSA，固定的)、中C(大C80%以上手术需求)、小C(骨科C臂) |  |
| 经胸壁超声心动图(TTE/transthoracic echocardiography) |  |  |
| [经食道超声心动图(TEE/transesophageal echocardiography)](https://e.dxy.cn/wisdom/front/zhihuihao/6961) | 通过超声探头位置的改变，由后向前近距离扫查心脏深部结构，显示出三维心脏结构的可视图像。TEE能比TTE更好地显示心脏后部结构 |  |
| IVUS(Intravascular Ultrasound) | 通过超声波成像技术来检测冠状动脉病变的医疗设备。可以在血管内部实时显示血管壁的厚度、斑块的性质和位置等信息，帮助医生评估血管狭窄的程度和位置 |  |
| OCT(光学相干断层扫描/通常指（Optical Coherence Tomography) | 高分辨率的成像技术，利用光学干涉原理，通过测量光的反射和散射来获取眼部组织的高清图像，可以显示眼部各个结构的层次结构和细节。用于检测和诊断多种眼部疾病，例如黄斑病变、青光眼、视网膜脱离等 |  |

* 其他

| 名称 | 说明 |
| :-: | - |
| POI | point of interest，兴趣点，GIS是坐标点 |
| ROI | region of interest，GIS是区域 |

## 影像文件
* 放射的6种主要格式：DICOM、NIFTI、PAR/REC（飞利浦 MRI 扫描格式）、ANALYZE（Mayo医疗成像）、NRRD、MNIC 格式。
* [3D模型(mesh)](https://blog.csdn.net/cloudqiu/article/details/98595029)格式：STL、OBJ

| 类型 | 全称 | 说明 |
| - | - | - |
| DICOM | 医疗中的数字图像和通信/Digital Imaging and Communication In Medicine | Orthanc - DICOM Server |
| mha/mhd |  | 体数据，mhd包含图像的meta data（.mhd）和图像裸数据(.raw) |
| NIFTI | 神经影像学信息技术计划/Neuroimaging Informatics Technology Initiative | 体数据，nii/nii.gz |
| [NRRD](http://teem.sourceforge.net/nrrd/format.html) | 近乎原始光栅数据/Nearly Raw Raster Data | “扩散加权图像”和“扩散张量图像”数据可以被解读为一个“3D切片机”，能够直观地确定张量图像的方向与神经解剖的预期是一致的。 |
| STL | stereolithography，光固化立体造型术 | 三维重建模型的表面MESH，用三角形网格来表现3D CAD模型，只能描述三维物体的几何信息，不支持颜色材质等信息 |
| [OBJ](https://blog.csdn.net/cloudqiu/article/details/98595029) |  | 三维重建模型的表面MESH，支持四边形网格 |
| JPG/PNG/tiff |  | 图片 |

## 资料
### 显示器
* 普通显示器分辨率1920*1080，DELL E2216HV
* 医用专业显示器
  * 黑白影像诊断显示器分辨率是1600*1200。巨鲨JUSHA-M21
* 产品用普通显示器，点击分屏时会把影像及其功能投放到医用专业显示器

### 标定设备
* https://calib.io/

### 医院工作流程
![](../s/radiology/workflow.jpg)

### 数据结构
![](../s/radiology/data_struct.png)
