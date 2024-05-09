[[I2C资料]](https://www.ti.com/lit/an/slva704/slva704.pdf?ts=1713762347563)
> General IIC Operation （feature）


### feature
1. 不同设备共享同一套I2C总线，具有不同地址
2. 从机只有在主机寻址到从机时才对主机进行数据传输（双端通讯，但是主机绝对主导）
3. 许多从属设备将需要在启动时进行配置，以设置设备的行为（需要预先配置）
4. IIC接口分为SCL和SDA两条线，均需要通过上拉电阻器连接Vcc
5. 总线空闲时才可以进行数据传输，而总线空闲的条件是stop condition之后双线拉高

* master send data to a slave

* master want to recv/read data from a slave
