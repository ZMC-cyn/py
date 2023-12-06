# 《Python程序设计基础》程序设计作品说明书

题目： 你选择的项目题目

学院： 21计科04

姓名：陈宥男

学号： B20210302425

指导教师： 周景

起止日期：2023.11.10-2023.12.10

## 摘要

_介绍本次设计完成的项目的概述，本文的主要内容，总结你主要完成的工作以及关键词。_

本次我选择的项目是外星人入侵小游戏，使用pip下载paygame库进行小游戏的编写，编写飞船控制函数对键盘
进行监听让玩家能够通过键盘控制飞船消灭外星飞船。

## 第1章 需求分析

1. 创建游戏需要用到的所有元素
2. 为所有玩家控制的元素编写控制函数，其次编写外星飞船npc元素
3. 对所有元素的动作编写函数
4. 对玩家的得分进行统计

## 第2章 分析与设计

1. 首先想要玩这个小游戏，需要主文件alien_invasion.py创建一系列整个游戏都要用到的对象：存储在
ai_settings中的设置、存储在screen中的主显示surface以及一个飞船实例。文件alien_invasion.py还包含
游戏的主循环，这是一个调用check_events()、ship.update()和update_screen()的while循环。 要玩游戏
《外星人入侵》，只需运行文件alien_invasion.py。其他文件（settings.py、game_functions.py、
ship.py）包含的代码被直接或间接地导入到这个文件中。
2. 其次需要通过一个文件对小游戏的难度进行控制的设置文件settings.py包含Settings类，这个类包含方法
__init__()、初始化游戏设置的方法initialize_dynamic_settings()、随游戏进程提高速度的方法
increase_speed()。
3. 创建玩家控制的飞船类，这个类包含方法__init__()、管理飞船位置的方法update()、在屏幕上绘制飞船的
方法blitme()以及让飞船在屏幕底部居中的方法center_ship()。表示飞船的图像存储在文件夹images下的
文件ship.bmp中。
4. 创建入侵的外星飞船类，这个类包含方法__init__()、管理外星人位置的方法update()、检测外星人是否位
于屏幕边缘的方法check_edges()以及在屏幕上绘制外星人的方法blitme()。表示外星人的图像存储在文件
夹images下的文件alien.bmp中。
project_report.md 2023-11-23
2 / 3
5. 创建玩家控制飞船射出的子弹类，这个类包含方法__init__()、管理子弹位置的方法update()以及在屏幕上
绘制子弹的方法draw_bullet()。
6. 创建一个动作game_functions.py，它包含一系列函数，游戏的大部分工作都是由它们完成的。函数
check_events()检测相关的事件，如按键和松开，并使用辅助函数check_keydown_events()和
check_keyup_events()来处理这些事件。就目前而言，这些函数管理飞船的移动。模块game_functions还
包含函数update_screen()，它用于在每次执行主循环时都重绘屏幕。
7. 创建游戏得分显示scoreboard.py包含Scoreboard类，这个类包含方法__init__()、渲染得分的方法
prep_score()、渲染最高得分的方法prep_high_score()、渲染等级的方法prep_level()、渲染剩余飞船的方
法prep_ships()及在屏幕上显示得分、最高得分、等级、飞船的方法show_score()。


## 第3章 软件测试
![](a.png)
## 结论
实现了飞机大战移动、消灭得分等目标，但只能左右移动，仍需要改进。
_本章的内容主要是对项目的总结，项目主要实现了哪些功能，达到了哪些目标，哪些不足之处，可以如何改进。_

## 参考文献
【python编程从入门到实践】