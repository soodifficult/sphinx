=======================
PLC Supervisor用户手册
=======================
PLC Supervisor App（以下简称PLC Supervisor）为用户提供了便捷的数据采集、数据处理和数据上云功能，支持Snap7、ModbusRTU等多种工业协议解析。本手册以采集PLC的数据并上传至Thingsboard云平台为例说明如何通过PLC Supervisor App实现PLC数据采集和数据上云。以下将InGateway500简称为“IG500”；InGateway900简称为“IG900”。

环境准备_

:ref:`环境准备`

---------------
概览
---------------

使用过程中，您需要准备以下项：

* 边缘计算网关IG500/IG900
* PLC设备
* 网线/串口线
* \*更新软件版本所需的固件、SDK和App
* \*Thingsboad演示账号

整体流程如下图所示：



.. image :: images/2020-03-12-22-26-27.png





节标题3
=============

节标题4
-------------

节标题5
`````````````


节标题6
'''''''''''''
1.1 硬件接线
1.1.1 以太网接线
IG900以太网接线

接通IG900的电源并按照拓扑使用以太网线连接IG900和PLC。 
_images/2020-03-12-14-02-22.png 

IG500以太网接线

接通IG500的电源并按照拓扑使用以太网线连接IG500和PLC。 
_images/2020-03-12-14-03-03.png

1.1.2 串口接线
IG900串口接线

接通IG900的电源并按照拓扑连接IG900和PLC。 
_images/2020-03-12-14-03-36.png

IG900正上方的端子接线说明如下图： 
_images/2020-01-09-18-47-30.png

IG500串口接线

接通IG500的电源并按照拓扑连接IG500和PLC。 
_images/2020-03-12-14-04-05.png

IG500正下方的端子接线说明如下图： 
_images/2020-03-11-11-38-45.png



1.3 设置WAN网络参数：传输数据至MQTT服务器
设置IG900 WAN网络参数，请参考IG900连接Internet。
设置IG500 WAN网络参数，请参考IG500连接Internet。

1.4 更新InGateway设备软件版本
如需获取InGateway产品最新软件版本及其功能特性信息，请联系客服。如需更新软件版本，请参考如下链接：



更新IG900软件版本
更新IG500软件版本

2.配置PLC Supervisor App
安装并运行PLC Supervisor
PLC Supervisor数据采集配置
添加PLC设备
添加变量
配置变量分组

.. _环境准备:

2.1 安装并运行PLC Supervisor
IG900如何安装并运行Python App请参考IG900安装和运行Python App，PLC Supervisor正常运行后如下图所示： _images/2020-02-21-17-57-15.png  
IG500如何安装并运行Python App请参考IG500安装和运行Python App，PLC Supervisor正常运行后如下图所示：_images/2020-02-21-17-57-15.png

2.2 PLC Supervisor数据采集配置

2.2.1 添加PLC设备
添加S7通讯的PLC设备

点击“添加PLC”按钮，在添加设备页面选择PLC协议为“Snap7”并配置PLC的通讯参数。（除PLC为S7-200 Smart时机架号和槽号需要配置为0，1；其余类型的S7系列PLC默认使用0，0即可）注意：设备名称不能重复。

_images/2020-02-27-14-18-01.png

添加成功后如下图所示：_images/2020-02-27-14-32-51.png 


添加ModbusTCP通讯的PLC设备

点击“添加PLC”按钮，在添加设备页面选择PLC协议为“ModbusTCP”并配置PLC的通讯参数。（端口号和字节序默认为502和abcd；使用时需根据实际情况调整）注意：设备名称不能重复。

_images/2020-03-06-15-02-16.png

添加成功后如下图所示：_images/2020-03-06-15-02-42.png 


添加ModbusRTU通讯的PLC设备

点击“添加PLC”按钮，在添加设备页面选择PLC协议为“ModbusRTU”并配置PLC的通讯参数。注意：设备名称不能重复。

_images/2020-02-27-14-19-59.png

添加成功后如下图所示： _images/2020-03-06-15-03-41.png

如需修改RS232/RS485串口的通讯参数，请在“边缘计算>>PLC Supervisor>>全局参数”页面修改。修改后所有串口设备的通讯参数将自动修改并按照修改后的通讯参数通讯。