---
layout: post
title: "2020CIIE工博会|部分收获+AMR&运动控制&其他配件信息"
date: 2020-9-27
excerpt: "一点小小的收获以及AMR企业展品、AMR机器人功能模块整合、机器人运动控制企业及信息、自动化配件企业及信息（传动机构、末端执行器、激光雷达等） "
tags: [jottings]
comments: true
robotics: true
timeline: true
---

<b><center><font size="4" face="Segoe Script">写在前面</font></center></b>
今年（2020年）中国国际工业博览会关键词有三个： <b>协作机器人、AMR和数字化</b>，而前两个与我专业关系更为紧密，因此我主要参观了机器人展。最初我对这个展览的期待有四个，第一个是希望了解新技术是如何体现在机器人的新功能上的；第二个是希望能通过再迈出一步，以获得某些关于未来发展方向的灵感；第三个是希望能偶遇一些有趣（愿意交流）的展商，收获一些预期之外的知识；第四个是希望能有近距离接触一些明星企业or与学校有合作关系的企业的机会。我深知以自己的知识储备，肯定没办法在初次接触产品时就提出有意义的问题，因此还专门分开两天分别完成收集资料和进一步探索的“任务”。展览结束后，以上的预期收获基本没有达成，我感到自己还是在技术外层兜圈子，毫无深入内部汲取知识的办法，但我明白了一点：这种困境无法在短期内靠我自己的主观意志打破，因为它源于我的身份“西交利物浦大学本科大二学生”。当参展商询问道：“您的企业是专注于哪个领域啊？”的时候我总是希望我能接着他的话说“我是X企业的采购部门经理，我们生产环境是…对产品的需求是…”但没办法，我是行外人，连扯淡的资本都没有。但另一方面，它也源于参展商的身份“企业”，这意味着他们不会主动（被动也很难）分享自己的技术详情，更意味着他们的产品都是依托于客户需求的，他们不会（也没必要）通过（我所期待的）大幅度的创新来维持自己的地位，大部分工程师要做的只是在原有的技术基础上不断优化、提升（精度、载荷、臂展、能耗、系统效率等等）、增加功能（根据不同行业用户的需求增加功能并不断debug）。我没有信心成为那少数能研发新技术的工程师，同时也意识到自己确实太过贪心（在反思日记中我已经无数次斥责过自己这一点了，不想再插一刀哈哈哈），因此从这次展览回校后，我更改了自己的学习方向的优先级并采取了逐个攻破的策略（希望我能坚持一段时间）。

由于协作机器人产品实在是太多了，这一篇文章放不下，也因为自己还没整理好叙述思绪，所以将协作机器人单独放在下一篇文章中。而这篇文章将会包括以下几个模块：<b>AMR企业展品、AMR机器人功能模块整合、机器人运动控制企业及信息、自动化配件企业及信息</b>（传动机构、末端执行器、激光雷达等）。

<b><center><font size="4" face="Segoe Script">AMR机器人</font></center></b>

（移动机器人四代发展史：导轨AGV -- 二维码AGV（自主移动、灵活实施提升）-- 激光AMR（高校协同提升）-- 视觉AMR（快速部署和其他都有提升）

1. <b>灵动科技</b> [http://cn.forwardx.com/](http://cn.forwardx.com/)

    1. Max AMR家族

    2. 灵动科技Flex AMR家族

    3. F(x)集群调度系统

2. <b>SEER仙工智能</b> [https://www.seer-group.com/](https://www.seer-group.com/)

    1. AMB系列 无人搬运底盘

    2. SRC系列 核心控制器

    3. 基于SRC的激光SLAM自动叉车

3. <b>集萃制造</b> [http://www.iimt.org.cn/](http://www.iimt.org.cn/)

    1. 轻型协作机器人

    2. 无人清洗车

4. <b>Standard Robots</b> 

    1. Gulf-1400-CDD搬运式叉车机器人

    2. AMR-600移动机器人

    3. 移动复合消毒机器人


<b><center><font size="4" face="Segoe Script">AMR机器人功能模块整合</font></center></b>

1. <b>安全防护</b>

    1. <b>斯坦德</b>

        1. 360°双雷达+3-3D摄像头+TOFs传感器+超声组合

        2. 四边防撞角+四角急停按钮

        3. 报警方式：语音+灯光

    2. <b>仙工智能</b>

        1. SRC核心控制器的安全防护

            1. SRC核心控制器采用双层架构，分别为驱动层与功能层，驱动层使用稳定的嵌入式ARM芯片，功能层为智能导航以及避障算法，驱动层可以检测到功能曾发生的不可预计的错误并及时停止机器人。

            2. 导航激光雷达--由SRC核心控制器获取该元件数据，通过计算采集到的数据控制机器人减速或者停止。

            3. 避障激光雷达--270°，覆盖到导航激光雷达无法检测到的盲区。（SRC核心控制器对IO信号检测频率高达1000Hz）

            4. 3D相机--用于视觉检测，检测立体障碍物或者地面的坑洞。

            5. 安全触边（碰撞条）。安全触边被挤压后，SRC控制器收到电平信号会立即停止机器人。

            6. 节点保护--对于CAN总线发生的故障能够实时监测并报警。

        2. 多传感器安全防护：导航激光、避障激光、安全探照灯、声光提醒、安全触边、防撞光电传感器、急停等

    3. <b>灵动科技</b>

        1. 传感器：2个激光雷达+里程计+惯性测量单元

        2. 摄像头：4个摄像头（包括一个Intel RealSense 摄像头）

        3. 声光电报警+两个急停按钮

2. <b>导航技术</b>

    1. 斯坦德：激光slam导航，站点停止精度+-20mm/2°

    2. 灵动科技：vSLAM（视觉同步定位和地图绘制）

    3. 仙工智能：激光slam导航，定位精度+-5mm，+-0.5°


<b><center><font size="4" face="Segoe Script">运动控制模块</font></center></b>

1. <b>雷赛智能</b>

    1. 聚焦于包括 伺服电机驱动系统、步进电机驱动系统、运动控制卡、运动控制器等产品的研发、生产和销售。

    2. 官网：[https://www.leisai.com/index.html](https://www.wago.com/cn/)

    3. 产品

        1. DM3E总线型步进驱动系列

        2. CL1系列脉冲通用型闭环步进驱动器

        3. DM通用型步进驱动系统

        4.  LD2系列驱控一体型低压伺服系统

        5. mPLC2系列基本型运动控制PLC

2. <b>德国万可WAGO</b>

    1. 专注于电气连接技术、工业接口模块、自动化控制技术等

    2. 官网：[https://www.wago.com/cn/](https://www.wago.com/cn/) 

    3. 产品

		1. 自动化控制产品

			1. 软件&解决方案（工程软件，Runtime软件、移动应用软件）

			2. 操作&监控（Web和触控面板）

			3. 控制器

			4. I/O系统

		2. 工业接口模块

			1. 模拟信号转换模块

			2. 电力和能源测量技术

			3. 工业稳压电源系列

			4. 继电器和光电耦合器

			5. 电缆转换模块

3. <b>KEBA AG(&LTI motion GmbH)</b>

	1. 产品包括自动化系统、CNC系统、运动控制、风能系统、安全技术、伺服控制器、伺服电机、电机部件、工程工具、磁浮轴承技术、主轴技术

	2. 官网：[https://www.keba.com/en/home](https://www.keba.com/en/home)

	3. 展出产品

		1. MotionOne CNC（激光技术包）

		2. KeConnect C5 I/O module(新一代I/O模块）

		3. KeControl C5（新一代控制系统）

		4. SystemOne CM(纺织机械运动控制技术）

		5. LTI Motion 路斯特技术组合

			1. 变桨伺服驱动器

			2. 变桨电机

			3. 偏航伺服驱动器

4. <b>SERVOTRONIX</b>(被美的收购了)

	1. 专注于人机交互、运动控制器、伺服驱动器、伺服电机、集成式电机、编码器

	2. 官网：[http://www.servotronix.com/?lang=zh-hans](http://www.servotronix.com/?lang=zh-hans)

	3. 部分展出产品：

		1. PRHD2高动态伺服电机

		2. CDHD 高性能伺服驱动器

		3. LDHD2高性能伺服驱动器

		4. CDHD2高性能伺服驱动器


<b><center><font size="4" face="Segoe Script">自动化配件</font></center></b>


1. <b>滚珠丝杆</b>（网站均有附产品信息、CAD数据、寿命计算等服务） 

	1. TBI（全球传动）

		1. 致力于传动元件事业，主要产品包括 滚珠螺杆、线性滑轨、滚珠花键、旋转式滚珠螺杆/花键、单轴机器人、直线轴承、联轴器、螺杆支撑座……

		2. 官网网址：[https://www.tbimotion.com.tw/zh-CN/index.html](https://www.tbimotion.com.tw/zh-CN/index.html) 


	2. THK

		1. 开发直线运动 (LM. 导轨机构的先驱以及许多其他独特的机械组件，包括滚珠花键、滚珠丝杠和连杆球

		2. 官网网址：[https://www.thk.com/?q=cn](https://www.thk.com/?q=cn)

2. <b>激光雷达</b>

	1. 万集科技

		1. 轮廓测量雷达

		2. 高频扫描雷达

		3. 叉车导航雷达

		4. SLAM导航雷达

		5. 工业防撞雷达

		6. 安全防护雷达

		7. 车轨3D雷达

3. 末端执行器

	1. 大寰机器人（DH-ROBOTICS）

		1. 工业薄型平行电爪

		传动方式：齿轮齿条+交叉滚子导轨/直线导轨

		2. 协作型平行电爪

		传动方式：齿轮齿条+T型导轨/直线导轨

		3. 关节型自适应电爪

		传动方式：丝杆螺母+连杆机构（+齿轮传动）

		4. 通讯协议：Modbus RTU(RS485),Digital I/O

        * 以上描述&信息均来自各企业在展览中派发的产品手册以及官网。

<b>下期预告：协作机器人四大家族：ABB、FANUC、KUKA、安川电机，新松SIASUN，遨博机器人，节卡机器人、爱普生机器人、梅卡曼德等协作机器人介绍</b>

