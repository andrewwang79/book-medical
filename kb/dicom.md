# DICOM
* 医学数字成像和通信(Digital Imaging and Communications in Medicine)
* [官网](https://www.dicomlibrary.com/)

## 知识
* [DICOM](https://baike.baidu.com/item/DICOM/2171358)
* [Transfer Syntax](https://blog.csdn.net/u014738683/article/details/54573611)
* [SOP](https://blog.csdn.net/u014738683/article/details/54573728)
* [数据类型](https://blog.csdn.net/inter_peng/article/details/46513847)
* [DICOM：C-GET与C-MOVE对比剖析](https://blog.csdn.net/zssureqh/article/details/46868695)
* [字段定义](http://dicom.nema.org/dicom/2013/output/chtml/part06/chapter_6.html)

* [GE](http://www3.gehealthcare.co.uk/~/media/documents/us-global/products/interoperability/dicom/radiology-pacs-ris/gehc-dicom-conformance_pathspeedpacs-v8-1_iisfp10282_rev2.pdf)
* [GE Private TS](https://blog.csdn.net/zssureqh/article/details/47222685)

## 常用字段
| 类型 | 名称 | 说明 |
| :----: | ---- | ---- |
| 最小图像像素值 | SmallestImagePixelValue(0028,0106) | 射线衰减值 |
| 最大图像像素值 | LargestImagePixelValue(0028,0107) | 射线衰减值 |
| 窗位 | WindowCenter(0028,1050) | 密度值，单位是HU |
| 窗宽 | WindowWidth(0028,1051) | 密度值，单位是HU |
| 缩放截距 | RescaleIntercept(0028,1052) |  |
| 缩放率 | RescaleSlope(0028,1053) |  |

## 公式
1. 密度值 = (像素值 * RescaleSlope) + RescaleIntercept
1. RGB = 像素值 * (LargestImagePixelValue - SmallestImagePixelValue) / 255
1. 密度值窗位选择: zoneMin < [WindowCenter-WindowWidth/2, WindowCenter+WindowWidth/2] < zoneMax。zoneMin的密度值是最小窗，zoneMax的密度值是最大窗
