# DICOM
* 医学数字成像和通信(Digital Imaging and Communications in Medicine)
* [官网](https://www.dicomlibrary.com/)
* [DICOM](https://baike.baidu.com/item/DICOM/2171358)

## 数据结构和字段
* [Dicom数据结构](https://zhuanlan.zhihu.com/p/102590860)
* [数据类型](https://blog.csdn.net/inter_peng/article/details/46513847)
* [字段定义](http://dicom.nema.org/dicom/2013/output/chtml/part06/chapter_6.html)
* [人体常见组织CT值](https://www.jianshu.com/p/3778324574d4)
* [GE](http://www3.gehealthcare.co.uk/~/media/documents/us-global/products/interoperability/dicom/radiology-pacs-ris/gehc-dicom-conformance_pathspeedpacs-v8-1_iisfp10282_rev2.pdf)，[GE Private TS](https://blog.csdn.net/zssureqh/article/details/47222685)
* 窗宽窗位: 是对于X线衰减系数的筛选，即常说的密度值。如窗宽值为300，窗位为-100，那么窗宽窗位的范围是-250到50，计算公式：[窗位-窗宽/2，窗位+窗宽/2]，那么CT值小于（窗位-窗宽/2）的时候就变成（窗位-窗宽/2），如果CT值大于（窗位+窗宽/2）的时候就变成（窗位+窗宽/2）。

## 常用字段
| 类型 | 名称 | 说明 |
| :-: | - | - |
| 最小图像像素值 | SmallestImagePixelValue(0028,0106) | 射线衰减值 |
| 最大图像像素值 | LargestImagePixelValue(0028,0107) | 射线衰减值 |
| 窗位 | WindowCenter(0028,1050) | 密度值，单位是HU |
| 窗宽 | WindowWidth(0028,1051) | 密度值，单位是HU |
| 缩放截距 | RescaleIntercept(0028,1052) |  |
| 缩放率 | RescaleSlope(0028,1053) |  |

## 通讯协议
* [DICOM通信介绍.pptx](https://medical.wangyaqi.cn/s//radiology/DICOM通信介绍.pptx)
* [Transfer Syntax](https://blog.csdn.net/u014738683/article/details/54573611)
* [SOP](https://blog.csdn.net/u014738683/article/details/54573728)
* [DICOM：C-GET与C-MOVE对比剖析](https://blog.csdn.net/zssureqh/article/details/46868695)

### 术语
| 名称 | 中文 | 说明 |
| :-: | - | - |
| SOP（Service-Object Pair）| 对象对 | Service(DICOM服务，如存储服务) + Object(DICOM对象，如CT影像) |
| SCP（Service Class Provider）| 服务类提供者 | 服务端 |
| SCU（Service Class User）| 服务类使用者 | 客户端，设备 |
| SOP Class（Service Object Pair Class Unique Identifier）| 对象对类 | 等同Abstract Syntax |
| AE（Application Entity）| 应用实体 | SCP和SCU的实体就是AE。2个AE传输前需确定好：SOP，SCP，SCU，SOP Class |

### 服务命令
| 服务 | 命令 | 说明 |
| :-: | - | - |
| 存储服务 | C-STORE | SCU传输DICOM图像到SCP， 也就是PUSH推图模式 |
| Query/Retrieve服务 | C-FIND | SCU向SCP请求某个级别(Patient/Study/Series/Image)的信息 |
| Query/Retrieve服务 | C-MOVE | ![C-MOVE](../s/radiology/c-move.png) |

## 公式
1. 密度值 = (像素值 * RescaleSlope) + RescaleIntercept
1. RGB = 像素值 * (LargestImagePixelValue - SmallestImagePixelValue) / 255
1. 密度值窗位选择: zoneMin < [WindowCenter-WindowWidth/2, WindowCenter+WindowWidth/2] < zoneMax。zoneMin的密度值是最小窗，zoneMax的密度值是最大窗

## 脱敏
* 行业脱敏TAG参考：https://www.dicomlibrary.com/terms-of-service/，https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4636522/
* 匿名但保留追溯能力设计：[{脱敏tag,修改值,原始值}]用json格式保存在1个私有tag上，可以考虑RSA加密内容

## 资料
* [Orthanc-轻量级开源DICOM服务器](https://www.orthanc-server.com/)
