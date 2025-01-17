---
title: \vspace{2in} 项目时间计划书
subtitle: "FaceGen: A face image generator website based on GAN"
author:
  - Shi, Ruixin^[Equal Contribution, Fudan University, 17302010065 (rxshi17@fudan.edu.cn)]
  - Zhang, Cenyuan^[Equal Contribution, Fudan University, 17302010068 (cenyuanzhang17@fudan.edu.cn)]
  - Zhang, Yihan^[Equal Contribution, Fudan University, 17302010076 (zhangyihan17@fudan.edu.cn)]
  - Wang, Chen^[Equal Contribution, Fudan University, 16307110064 (wangc16@fudan.edu.cn)]
  - Zhang, Hongnian^[Equal Contribution, Fudan University, 17302010061 (17302010061@fudan.edu.cn)]
  - Song, Puqi^[Equal Contribution, Fudan University, 17302010037 (17302010037@fudan.edu.cn)]
  - Huang, Huiru^[Equal Contribution, Fudan University, 17302010080 (17302010080@fudan.edu.cn)]
  - Tian, Ziwei^[Equal Contribution, Fudan University, 17302010071 (17302010071@fudan.edu.cn)]
date: "2020年11月10日"
documentclass: ctexart
output:
  rticles::ctex:
    fig_caption: yes
    number_sections: yes
    keep_md: yes
    keep_tex: yes
    extra_dependencies:
      multirow: null
      float: null
classoption: "hyperref, a4paper"
header-includes:
   - \usepackage{array}
   - \usepackage{amsmath}
---


\newpage

\LARGE

\begin{center}
\textbf{项目时间计划书}
\end{center}

\large
\begin{center}
\textbf{\emph{FaceGen: A face image generator website based on GAN}}
\end{center}



# 项目描述
随着互联网的发展，各种应用的出现，人们对塑造个性化的虚拟形象、定制具有某些特征的头像的需求也随之增多，生成的头像可以用于各类应用中，人脸生成这一项任务应运而生。
针对人脸生成任务，我们在项目中将使用TensorFlow搭建一个生成式对抗网络模型，并采用LSUN数据集，ImageNet1k和celebA数据集来对模型进行训练，最终得到能够产生人脸的图像的生成器。并且，在训练好的模型的基础上，我们将会完成一个前端网页，以可视化输入生成器的噪声向量并方便用户调整输入，以及在网页上展示生成器最终生成的图像。

## 项目分解
根据对本项目的分析，从项目生命周期的角度，通过项目WBS分解作到将项目分解到内容单一的、相对独立的、易于成本核算与检查的项目单元， 采用图表方式描述的任务分解结果（ WBS ）如图1所示

![FaceGen网站建设项目的WBS](WBS.pdf)

## 工作描述
见表1

\begin{table}
    \caption{任务描述}
    \centering
    \begin{tabular}{|p{5.0cm}<{\centering}|p{7.5cm}<{\centering}|}
    \hline
    任务       & 补充说明                                                 \\ \hline
    搭建生成模型   & 使用TensorFlow搭建DCGAN的生成器                             \\ \hline
    搭建判别模型   & 使用TensorFlow搭建DCGAN的判别器                              \\ \hline
    直接获取数据集  & 训练使用的数据集包括LSUN数据集，ImageNet 1k和celebA数据集             \\ \hline
    构造数据集    & 爬取网上社区的图片，通过openface进行修剪来构造数据集                      \\ \hline
    预处理数据集   & 调整图像大小，进行图像标准化处理                                    \\ \hline
    训练模型     & 通过优化目标函数训练模型                                        \\ \hline
    调整模型参数   & 调整参数进行多次训练，在验证集和测试集上进行测试来找到性能最好的参数                  \\ \hline
    实现Demo前端 & 前端需要实现一个网页，主要功能为展示生成的图像，并能显示其对应的输入z；前端网页使用vue框架来实现   \\ \hline
    实现Demo后端 & 后端需要提供相应接口，使网页能够获取图像与对应的输入                          \\ \hline
    \end{tabular}
\end{table}

# 项目计划
根据 WBS 的分解情况继续分解出相应的活动，使用 ProcessOn 工具，将分解后的所有活动和 WBS 的代码录入项目计划文件中，然后确定各活动之间的关系，经过不断的资源调整优化以及工期、活动关系的调整等，再经过多次的评审讨论，最后计划通过评审后，将此计划存为基准计划。项目的基准计划如下

## 项目进度计划
见表2

\begin{table}
    \caption{项目进度计划}
    \centering
    \begin{tabular}{|p{2.0cm}<{\centering}|p{1.0cm}<{\centering}|p{2.0cm}<{\centering}|p{2.0cm}<{\centering}|p{2.0cm}<{\centering}|}
    \hline
    任务名称     & 耗时（天） & 开始         & 结束         \\ \hline
    \textbf{DCGAN}    & \textbf{76}    & \textbf{2020-9-26}  & \textbf{2020-12-11} \\ \hline
    项目分析     & 5     & 2020-9-26  & 2020-9-31  \\ \hline
    搭建模型     & 18     & 2020-10-9  & 2020-10-27 \\ \hline
    获取与处理数据集 & 26     & 2020-10-15 & 2020-11-10 \\ \hline
    实现Demo   & 31    & 2020-11-10 & 2020-12-11 \\ \hline
    \end{tabular}
\end{table}

## 工作责任分配表
见图2

![责任分配表](1.png)

## 项目计划工作列表
见表3

\begin{table}
    \caption{工作列表}
    \begin{tabular}{|p{2.0cm}<{\centering}|p{2.0cm}<{\centering}|p{2.0cm}<{\centering}|p{2.0cm}<{\centering}|p{2.0cm}<{\centering}|}
    \hline
    任务编码 & 任务名称     & 紧前工作  & 时间估计（天） & 负责人 \\ \hline
    1    & 项目分析     & —     & 5       & 王宸  \\ \hline
    2    & 搭建生成模型   & 1     & 9       & 王宸  \\ \hline
    3    & 搭建判别模型   & 1     & 9       & 张岑湲 \\ \hline
    4    & 直接获取数据集  & 1     & 5       & 石睿欣 \\ \hline
    5    & 构造数据集    & 1     & 9       & 张逸涵 \\ \hline
    6    & 预处理数据集   & 4、5   & 6       & 黄蕙茹 \\ \hline
    7    & 训练模型     & 2、3、6 & 3       & 宋普琦 \\ \hline
    8    & 调整模型参数   & 7     & 5       & 张宏年 \\ \hline
    9    & 实现Demo前端 & 1     & 14      & 田紫薇 \\ \hline
    10   & 实现Demo后端 & 1     & 17      & 王宸  \\ \hline
    \end{tabular}
\end{table}

## 项目网络图
见图3

![网络图](network.pdf)

## 甘特图
见图4

![Gantt图](3.png)
