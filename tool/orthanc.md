# Orthanc

## 安装使用
* [Orthanc官方网站](https://www.orthanc-server.com/)下载适Windows的安装程序。
* 配置文件是安装目录下的Configuration/orthanc.json
  * "Name"：指定 Orthanc 实例的名称，用于标识该实例。
  * "DicomAet"：指定 Orthanc 实例的 DICOM AE 标识，用于与其他 DICOM 设备进行通信。
  * "DicomPort"：指定 Orthanc 实例监听的 DICOM 端口号。
  * "DicomModalities"：配置与 Orthanc 实例连接的 DICOM 设备的信息，包括设备名称、IP 地址、端口号等。
  * "HttpPort"：指定 Orthanc Web 界面监听的 HTTP 端口号。
* 启动 Orthanc：执行安装目录中的Orthanc.exe或者OrthancService.exe
  * 执行"services.msc" 打开Windows的服务管理器，启停Orthanc服务
* Web界面：http://localhost:8042，支持影像的上传、查看和管理

## 安装使用storescu等
```
sudo apt-get install dcmtk

storescu -v -aet <本地AE标识> -aec <Orthanc的AE标识> <Orthanc的IP地址> <Orthanc的端口号> <要上传的DICOM文件>

storescu程序在运行时自动创建AET，不需要提前准备。
find ${DICOM_PATH} -type f -name "*" -exec storescu -v -aet AETSender -aec AECReceiver 192.168.0.49 4242 {} \;
storescu -v -aet AETSender -aec AECReceiver 192.168.0.49 4242 ${DICOM_PATH}
```

## 使用实践
1. Windows电脑A安装Orthanc并启动，Linux电脑B安装storescu。注意防火墙导致端口无法访问
1. A在配置文件里加个AET
```
"DicomModalities" : {
    "AETSender" : [ "AETSender", "192.168.0.49", 2000 ]
```
1. B通过storescu发送Dicom文件
