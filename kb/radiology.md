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
| MRI(核磁共振) | 是利用一个强大的磁场，让身体里的氢原子，先排好队再解散，接受这期间的电磁波信号，再给身体内部画像 | 磁共振信号 |
| DR(数字化放射成像) |  |  |
| X光 | 用X光给你的身体拍了一张照片的检查方式。所以也叫拍片子 |  |
| CT(计算机断层扫描) | 实际上也是用X光给身体拍照片的检查方式。不过不是拍一张，而是要拍很多张，一层一层地查。 | X线衰减系数 |
| CT平扫(NCCT/Noncontrast CT) |  |  |
| 螺旋CT |  |  |
| CTA(CT血管成像/CT Angiography) | 增强CT。将动脉血管显影的药物注射到静脉内，利用CT机扫描获得的图像数据进行处理后，使头颈、心脏、肺动脉、主动脉等血管显影成像 |  |
| CTP(CT灌注成像/CT Perfusion) | 增强CT。[原理](https://blog.csdn.net/chenran187906/article/details/110387736) |  |
| 数字减影技术(DSA/Digital subtraction angiography) | 将注入造影剂前后拍摄的两帧X线图像通过数字化处理(减影、增强和再成像)，把不需要的组织影像删除掉，只保留血管影像 |  |
| 锥形束CT(CBCT/Cone Beam CT) | 西门子的成像视野是16立方厘米 |  |
| [C形臂(C型的机架)](https://zhuanlan.zhihu.com/p/265023777) | 大C(DSA，固定的)、中C(大C80%以上手术需求)和小C(骨科C臂) |  |
| 经胸壁超声心动图(TTE/transthoracic echocardiography) |  |  |
| [经食道超声心动图(TEE/transesophageal echocardiography)](https://e.dxy.cn/wisdom/front/zhihuihao/6961) | 通过超声探头位置的改变，由后向前近距离扫查心脏深部结构，显示出三维心脏结构的可视图像。TEE能比TTE更好地显示心脏后部结构 |  |

* 其他

| 名称 | 说明 |
| :-: | - |
| HU | CT图像上每个像素所对应的物质对X线线性衰减量平均大小的表示，称为CT值，其单位为HU（豪斯菲尔德Housfield，英国科学家，发明了CT扫描仪） |
| POI | point of interest，兴趣点，GIS是坐标点 |
| ROI | region of interest，GIS是区域 |

## 影像文件
* 放射中主要有六种文件格式：DICOM（医疗中的数字图像和通信）、NIFTI（神经影像学信息技术计划）、PAR/REC（飞利浦 MRI 扫描格式）、ANALYZE（Mayo医疗成像）、NRRD（近乎原始光栅数据）、MNIC 格式。
* 3D模型(mesh)主要是STL和OBJ

| 类型 | 全称 | 说明 |
| :-: | - | - |
| dicom | Digital Imaging and Communication In Medicine | Orthanc - DICOM Server |
| mha/mhd |  | 体数据，mhd包含图像的meta data（信息头）和图像裸数据 |
| NIFTI | Neuroimaging Informatics Technology Initiative | 体数据，nii/nii.gz |
| [NRRD](http://teem.sourceforge.net/nrrd/format.html) | Nearly Raw Raster Data | “扩散加权图像”和“扩散张量图像”数据可以被解读为一个“3D切片机”，能够直观地确定张量图像的方向与神经解剖的预期是一致的。 |
| STL | stereolithography，光固化立体造型术 | 三维重建模型的表面MESH，用三角形网格来表现3D CAD模型，只能描述三维物体的几何信息，不支持颜色材质等信息 |
| [OBJ](https://blog.csdn.net/cloudqiu/article/details/98595029) |  | 三维重建模型的表面MESH，支持四边形网格 |
| JPG/PNG/tiff |  | 图片 |

## 资料
* [螺旋CT、增强CT、CBCT](https://www.sohu.com/a/233743240_100130383)

### 显示器
* 普通显示器分辨率1920*1080，DELL E2216HV
* 医用专业显示器
  * 黑白影像诊断显示器分辨率是1600*1200。巨鲨JUSHA-M21
* 产品用普通显示器，点击分屏时会把影像及其功能投放到医用专业显示器

### 医院工作流程
![](../s/radiology/workflow.jpg)

### 数据结构
![](../s/radiology/data_struct.png)
