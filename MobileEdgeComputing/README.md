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

![](https://github.com/niwanli/reading-notes/raw/master/MobileEdgeComputing/pictures/fig-1.gif "MVR system model")

Fig-1 MVR system model

### B. High-level view of the MVR architecture

5. On the Mobile Device, the MVR runtime consists of four
components:

* **Proxy Monitor**: discovers resourceful proxy
* **Decision Engine**
	* **Decision Engine**: identifies methods
	* **Dynamic Analyzer**: analyzes the cost and benefit  
* **Tasklet Distributor**: marks the tasklet as “0” or “1”
* **Executor**: executes the procedure and interacts with Edge Cloud

6. On the other side, each VRs in Edge Cloud have six main components:

* **Registration Manager**: responsible for the registering and authenticating of the mobile devices that are requesting services
* **Predictor**: predicts the arrival of the mobile user and execution time of tasklet
* **Partition Analyzer**: analyzes the current network conditions of Edge Cloud and construct offloading overhead function
* **Decision Solver**: provides a decision method
* **Virtual Resource Controller**: VRs is managed by a certain VRs Controller (VRC) and VRC need to aggregate the execution results and feed back to the mobile device
* **Executor**: executes the procedure and fulfill interaction during execution

![](https://github.com/niwanli/reading-notes/raw/master/MobileEdgeComputing/pictures/fig-2.gif "The MVR architecture of the prototype")

Fig-2 The MVR architecture of the prototype

### C. The process of MVR offloading

7. Characteristics of applications that can benefit from Edge Cloud are typically time-critical and require a very low computing and communication latency in an environment with limited bandwidth, and limited computing power.

> 可以从边缘云中获益的应用程序，通常具有时间关键的特征和在带宽与计算能力都有限的环境中需要非常低的计算和通信延迟的特征。

8. This section describes an application of MVR in augmented reality (AR).

> 本节将描述一个MVR在现实增强中的应用。

9. In this AR example, the Tasklets of VideoSource and the Renderer have to be executed on the mobile device, as they access device specific hardware. So, these tasklets would be marked as “0”.  

> 在这个AR示例中，视频源和渲染器这两个子任务必须在移动设备上执行，因为它们需要访问设备特定的硬件。因此，它们将被标记为“0”。

![](https://github.com/niwanli/reading-notes/raw/master/MobileEdgeComputing/pictures/fig-3.gif "The relation of the AR algorithm tasklets")

Fig-3 The relation of the AR algorithm tasklets

## 3. Related Work
10. **MAUI** maximize the potential for energy savings while minimizing the burden on the programmer by using a combination of code portability, programming reflection, serialization, type safety, and network costs. 

> MAUI最大化节约能源的潜力，同时通过使用一种将代码可移植性、编程反射、串行化、类型安全性和网络成本等相结合的方法发来最小化程序员的负担。

11. **CloneCloud** does not virtualize access to native resources that are not virtualized already and are not available on the clone. It may be pursued in conjunction with thread-granularity migration.

> 克隆云不虚拟化对本地资源的访问，这里的本地资源指的是那些已经不是虚拟化的，或者在克隆云上不可用的资源。

12. **COSMOS** applys the next important step further to bridge the gap between offloading demands and the availability of cloud computing resources.

> COSMOS进行了下一个重要步骤，进一步地缩小了卸载需求与云计算资源可用性之间的差距。

13. **Cloudlet** bring abundant resources closer to the users, only one hop distance between mobile device and Cloudlet.

> Cloudlet为用户提供更多的、更靠近用户的资源，移动设备与Cloudlet（小云朵）之间只有一跳距离。

14. **Femtocloud** system provides a dynamic, self-configuring and multi-device mobile cloud for a cluster of mobile devices.

> Femtocloud系统为一组移动设备提供动态，自配置和多设备移动云。

15. **Spontaneous proximity cloud** (SPC) drops the high delay between the mobile device and the cloud by a set of neighboring mobile devices in a collaborative manner.

> 自发接近云（SPC）以协作的方式通过一组相邻的移动设备降低移动设备和云之间的高延迟。

![](https://github.com/niwanli/reading-notes/raw/master/MobileEdgeComputing/pictures/fig-4.gif "The application model of computation offloading")

Fig-4 The application model of computation offloading

## 4. Conclusion

In this paper, we present MVR architecture for computation
offloading in Mobile Edge Computing to creat a wonderful
bridge between computation/interaction-intensive applications
and the resourceful Edge Cloud. With the advent of new technology such as 5G, there are many challenging work awaiting
us to solve. For example, there is a lack of understanding under
a multi-dynamic environment about the joint optimization
problem involving leasing cost, runtime, energy consumption,
delay time and so on. Can we design a mechanism to create
and maintain a stable “Mobile Federation”? How effective
is such an approach in a setting with multiple clouds and
multiple service providers? The security level of mobile users
can change from location to location frequently and quickly.
We predict that the use of privacy services for mobile users
in MEC environment will increase the computation offloading
complexity. In our future work, we will continue to explore
on the problem of computation offloading.

16. How effective is such an approach in a setting with multiple clouds and
multiple service providers?

> 在多云和多个服务提供商的设置中，这种方法的效果如何？

17. We predict that the use of privacy services for mobile users in MEC environment will increase the computation offloading complexity. 

> 我们预测：在MEC环境中为移动用户提供隐私服务，将会增加计算卸载的复杂度。

**Question**：Is it valuable to construct a simulation model to calculate the increase in complexity?

## My Thinking


