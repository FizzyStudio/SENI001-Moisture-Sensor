# SENI001 土壤湿度传感器

###### 翻译

> `英文`请参考 [`这里`](https://github.com/FizzyStudio/SENI001-Moisture-Sensor/blob/master/README.md).

> `中文`请参考 [`这里`](https://github.com/FizzyStudio/SENI001-Moisture-Sensor/blob/master/README_CN.md).

![](https://github.com/FizzyStudio/SENI001-Moisture-Sensor/blob/master/pic/SENI001.jpg "SENI001") 

### 概述

> 这是一个简易的水分传感器可用于检测土壤的水分，当土壤缺水时，传感器输出值将减小，反之将增大。使用这个传感器制作一款自动浇花装置，让您的花园里的植物不用人去管理。
传感器表面做了镀金处理，可以延长它的使用寿命。将它插入土壤，然后使用AD转换器读取它。在他的帮助下，植物会提醒您：嘿，我渴了，请给我一点水。 
 
### 技术指标    

* 电源要求：+3.3-5V 
* 输出电压: 0~2.3v 
* 工作电流: 最大20mA
* 接口定义：1脚信号，2脚地，3脚电源正
* 使用寿命：1年左右 
* 模块尺寸: 60x20x5mm

##### 典型电压值（测试平台：10位AD，基准电压5V）:

* 0 ~300 : 干燥土壤
* 300~700 : 湿润土壤
* 700~950 : 放到水中

### 土壤湿度传感器工作原理

![](https://github.com/FizzyStudio/SENI001-Moisture-Sensor/blob/master/pic/SENI001_3.jpg) 

> 土壤湿度传感器是判断土壤中水分含量的多少来判定土壤的湿度大小。如图所示，当土壤湿度传感器探头悬空时，三极管基极处于开路状态，三极管截止输出为0；
> 当插入土壤中时由于土壤中水分含量不同，土壤的电阻值就不同，三极管的基极就提供了大小变化的导通电流，三极管集电极到发射极的导通电流受到基极控制，经过发射极的下拉电阻后转换成电压。

### 接线图

> 这里我们使用Arduino控制器来做测试，Arduino内部自带10位AD采样电路，程序简单，使用非常方便。

![](https://github.com/FizzyStudio/SENI001-Moisture-Sensor/blob/master/pic/SENI001_4.png "Connection")

### 样例代码

    /* # Example code for the moisture sensor   
       # Editor     : Lauren   
       # Date       : 13.01.2012   
       # Version    : 1.0   
       # Connect the sensor to the A0(Analog 0) pin on the Arduino board 
       # the sensor value description   
       # 0  ~300     dry soil   
       # 300~700     humid soil   
       # 700~950     in water 
    */  
    void setup(){       
       Serial.begin(57600);     
    }   
    void loop(){       
       Serial.print("Moisture Sensor Value:");
       Serial.println(analogRead(0));     
       delay(100);     
    } 

### 更多
