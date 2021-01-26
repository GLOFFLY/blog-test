# 个人介绍

![hello](hello.png)

我叫范立杨，祖籍河南南阳，现居郑州。

通信工程专业20界优秀毕业生，毕业于北京科技大学天津学院。

爱好范围：
* 声乐相关
* 编程。
  
学习经历：

1. 大二粗通C语言，用C写嵌入式（主要完成摄像头驱动代码移植，I2C、sccp等通信协议，电磁采集，自动化控制PID算法等），作品拿到全国大学生“恩智浦杯”智能车大赛华北赛区二等奖。
2. 大三学习Java语言，写了一个2D射击类小游戏。
3. 现正在学习前端。
   
下面是一段模拟I2C协议的启动I2C总线子程序：
```C
void iic_start(void)
{ 	
	BFSDA = 1;  
    BFdelay_1us(1);      // 延时1us 
    BFCLK = 1;
    BFdelay_1us(1);      // 延时5us 
    BFSDA = 0;
    BFdelay_1us(1);  
    BFCLK = 0;
    BFdelay_1us(2);
}
```

![end](end.png)