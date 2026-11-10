# ORVIBO_Device_Control 协议修复版  v1.0.1
基于 https://github.com/jzgods/ORVIBO_Device_Control
我这在ha装上后无法获取实体，借助WB修复，只有s20c，测试后正常。

# 安装方式 
  1. 把本包里的 custom_components 目录整个复制到 HA 的 /config/ 下，或覆盖已有的 ORVIBO_Device_Control 目录下内容。
  2. 重启 Home Assistant（必须重启，不能只重载集成）。
  3. 添加集成，输入智家365 账号密码；已配置过的账号无需重配。
  注意：domain 与原版完全相同，两个版本不能并存，必须覆盖。



# 以下是原版说明

ORVIBO_Device_Control

欧瑞博设备控制 Home Assistant 自定义组件
前期连入智家365APP以及S20c、S30c的整套代码参考自：https://github.com/abb3421/orvibo_switch
本组件在此项目基础上增加了MixSwitch系列开关、AirMaster Max控制器、多功能控制盒的适配

## 支持的设备型号

| 设备型号 | 设备类型 | 备注 |
|---------|---------|------|
| 56d124ba95474fc98aafdb830e933789 | Switch | S20c |
| 04aa419575be4714a853a82be3f22035 | Switch | S30c |
| f3be30b8c43c44da85aac622e5b56111 | Switch | MixSwitch |
| 71a0b275d9ba4895afdaf400bc7e3a0d | Switch | MixSwitch |
| b7313321dbe74da384d136a2a3fa2005 | Switch | MixSwitch |
| 2e13af8e17434961be98f055d68c2166 | Switch | MixSwitch |
| f5f2d6e6f4a14a82bee85032c27dbd1e | Air Conditioner | AirMaster Max(空调) |
| 396483ce8b3f4e0d8e9d79079a35a420 | Ventilation | 多功能控制盒(通风设备) |

## 使用方法

1. 将本组件放入 Home Assistant 的 `custom_components` 目录
2. 重启 Home Assistant
3. 在 Home Assistant 界面中添加集成
4. 输入欧瑞博账号和密码完成配置

## 功能

- 支持开关设备控制
- 支持空调设备控制
- 支持风扇设备控制
- 实时更新设备状态

## 注意事项

由于某些设备是通过欧瑞博适用的“中转”设备连接的，比如中央空调、新风系统等就是通过空调网关以及mini控制盒接入欧瑞博服务器的
所以这一类设备的控制与实时状态的数据传输是受两个设备之间连接的方式而改变的，简单来说就是两个设备之间线头的连接方式的不同
会导致最终看到的设备状态不同，所以这一类设备在非标准连接方式之外的情况下，并不能保证该组件获取的设备状态以及控制能够达到
预期
