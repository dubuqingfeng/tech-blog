---
title: 基于 Arduino 的解魔方机器人软件设计与实现
date: 2015-04-10 16:25
updated: 2015-04-10 20:18
tags: 
  - 电子设计
  - 解魔方机器人
excerpt: 本文在上一篇解魔方机器人初步设计的基础上进行的详细设计，基于Android，和xxx控制板，后期可以扩展到Arduino,树莓派等，后期会陆续开源，从材料结构，到算法控制等的一些简单设计。
categories: 电子设计
permalink: 201504-Rubik's-Cube-Robot-Ruanjiansheji.html
author: admin
---

# 0x01 Android上位机设计部分
常见的魔方比赛可以
# 0x02 Android代码思路
# 0x03 Android软件测试
# 0x04 Arduino测试代码思路
首先通过官方示例程序Knob和Sweep测试舵机运行情况

	/* 
	 Controlling a servo position using a potentiometer (variable resistor) 
	 by Michal Rinott <http://people.interaction-ivrea.it/m.rinott> 

	 modified on 8 Nov 2013
	 by Scott Fitzgerald
	 http://arduino.cc/en/Tutorial/Knob
	*/
	#include <Servo.h>
	Servo myservo;  // create servo object to control a servo
	int potpin = 0;  // analog pin used to connect the potentiometer
	int val;    // variable to read the value from the analog pin
	void setup()
	{
	  myservo.attach(9);  // attaches the servo on pin 9 to the servo object
	}
	void loop() 
	{ 
	  val = analogRead(potpin);            // reads the value of the potentiometer (value between 0 and 1023) 
	  val = map(val, 0, 1023, 0, 180);     // scale it to use it with the servo (value between 0 and 180) 
	  myservo.write(val);                  // sets the servo position according to the scaled value 
	  delay(15);                           // waits for the servo to get there 
	} 

	/* Sweep
	 by BARRAGAN <http://barraganstudio.com> 
	 This example code is in the public domain.

	 modified 8 Nov 2013
	 by Scott Fitzgerald
	 http://arduino.cc/en/Tutorial/Sweep
	*/ 

	#include <Servo.h> 
	 
	Servo myservo;  // create servo object to control a servo 
		            // twelve servo objects can be created on most boards
	int pos = 0;    // variable to store the servo position 
	void setup() 
	{ 
	  myservo.attach(9);  // attaches the servo on pin 9 to the servo object 
	} 
	 
	void loop() 
	{ 
	  for(pos = 0; pos <= 180; pos += 1) // goes from 0 degrees to 180 degrees 
	  {                                  // in steps of 1 degree 
		myservo.write(pos);              // tell servo to go to position in variable 'pos' 
		delay(15);                       // waits 15ms for the servo to reach the position 
	  } 
	  for(pos = 180; pos>=0; pos-=1)     // goes from 180 degrees to 0 degrees 
	  {
		myservo.write(pos);              // tell servo to go to position in variable 'pos' 
		delay(15);                       // waits 15ms for the servo to reach the position 
	  } 
	} 

# 0x05 Arduino代码
Arduino代码部分在github上也可找到，

> 使用串口测试成对舵机的代码-->DoubleServo

> 约定一些操作码和公式进行方便控制舵机的代码
# 0x05 计算解法公式
涉及到魔方解法部分，
# 0x06 蓝牙发送操作码
分为普通公式与特定操作码部分，普通公式主要为使用二阶段算法计算出来的解法公式，并且约定带+号为顺时针旋转，带-号为逆时针旋转，特定操作码约定一些特定的舵机控制操作，主要以下列表所示：

> 全部还原固定角度

> 成对舵机转动固定角度

> 单个舵机转动固定角度

> 从舵机进行转动，使机械臂进行前进与后退操作

> 
# 0x07 魔方解法操作对应舵机动作分析
因为舵机转动角度为0～180度，所以在初始角度中有两种，可以在0度，使得可以一次性做U和U2类型的操作(关于魔方转法表示，参考详细思考)，魔方解法为上黄下白前橙的初始位置。

R动作分析如下：2f号舵机旋转到90度，延迟等待旋转完毕，2b号舵机旋转，使机械臂后退，延迟等待旋转完毕，2f号舵机旋转到0度，延迟等待旋转完毕，2b号舵机旋转，使机械臂前进卡住魔方。

