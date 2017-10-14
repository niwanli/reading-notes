# MVR: an Architecture for Computation Offloading in Mobile Edge Computing

> X. Wei et al., "MVR: An Architecture for Computation Offloading in Mobile Edge Computing," 2017 IEEE International Conference on Edge Computing (EDGE), Honolulu, HI, 2017, pp. 232-235.

## Abstract

 As communication and sensing capabilities of mobile devices increase, mobile applications are becoming increasingly complex. The ability of computation offloading, which is one of the main features of mobile edge computing gains relevance as a technique to improve the battery lifetime of mobile devices and increase the performance of applications. In this paper, we describe the offloading system model and present an innovative architecture, called "MVR", contributing to computation offloading in mobile edge computing.

**Keywords**:Mobile Edge Computing, Edge Cloud, Computation Offloading, Architecture, Internet of Things.

## 1. Introduction

1.  Mobile Edge Computing (MEC) as a
new paradigm provides IT and cloud computing capabilities
within the Radio Access Network (RAN) in close proximity to
mobile subscribers.

> 移动边缘计算(MEC) 作为一个新的范例，为在无线接入网(RAN)附近的手机用户提供IT和云计算能力。

2. A “3WH” issue, including: why to offload, what to offload, when to offload and how to offload.

> 一个“3WH”问题，包括：为何需要卸载（迁移？offload），什么需要卸载，何时需要卸载以及如何去卸载。

## 2. Offloading in MVR

3.  MVR, an innovative architecture through finegrained offloading execution to Edge Cloud platform. MVR enable the use of virtual resources (VRs) in Edge Cloud to alleviate the resource burden and reduce energy consumption of the mobile device itself and improve the application performance. Conceptually, MVR automatically transforms a singlemachine execution (on a mobile device) into a distributed execution (on the mobile device and Edge Cloud).

> MVR，是一种通过将程序执行过程迁移到Edge Cloud（边缘云）平台的细粒度的创新架构。MVR允许在Edge Cloud中使用虚拟资源（VR）去减轻资源负担和减少移动设备本身的能源消耗，并提高应用程序的性能。 在概念上，MVR架构会自动地将单机执行（只在在移动设备上执行）转换为分布式执行（同时在移动设备和边缘云上执行）。 

### A. MVR system model

4. Non-offloaded tasklets (marked as “0”), tasklets that were offloaded to Edge
Cloud (marked as “1” ). The role of VRs is responsible for the execution of the “1” tasklets.

> 未卸载的子任务（标记为“0”），卸载到Edge Cloud的子任务（标记为“1”）。 VR的角色是负责执行标记为“1”的子任务（微进程？tasklet）。

![](https://github.com/niwanli/reading-notes/raw/master/Mobile Edge Computing/pictures/fig-1.gif "MVR system model")

Fig. 1. MVR system model