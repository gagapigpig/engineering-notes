# 企业级航踪系统

整合多个物流数据供应商的数据，对原始轨迹数据进行采集、清洗、分析并转换为统一标准格式，最终构建通用的货运与载具跟踪数据模型。  
该系统从多个维度为公司内外系统提供统一、稳定的航运跟踪服务，确保端到端运输信息可追溯。

主要技术栈：Spring Boot、Spring Cloud、DDD、Axon、RabbitMQ、Redis、MySQL、MongoDB

---

## 一、项目背景

- 对单个集装箱从提空（Empty Pickup）到还空（Empty Return）的全过程进行轨迹与风险跟踪  
- 建立公司内部统一的航踪数据标准，并逐步向行业标准靠拢  
- 为客户提供端到端的航运跟踪能力  
- 为公司内部多个系统提供统一的业务数据查询能力  

---

## 二、要解决的核心问题

- 从集装箱、载具、船舶等多个维度提供航踪服务  
- 确保端到端运输信息可追溯  
- 行业内缺乏统一的航踪数据标准  
- 多数据源接入，数据格式不统一、更新频率不同  
- 构建公司级数据底座，为下游系统提供原始数据、标准数据及业务数据  

---

## 三、系统整体架构

<img width="2086" height="1188" alt="系统架构_副本" src="https://github.com/user-attachments/assets/5b2faad1-47b5-49d0-95b9-dcb9d2e100fd" />


---

## 四、核心领域模型（DDD 思路）

- Shipment（运单）  
- Container（集装箱）  
- Vessel（船舶）  
- TrackingEvent（轨迹事件）  

---

## 五、数据流转过程

<img width="1800" height="892" alt="数据流程过程_副本" src="https://github.com/user-attachments/assets/f455e90a-ffc1-4143-b4c9-55b1b73daac1" />


---

## 六、关键技术选型

- Spring Boot / Spring Cloud  
- DDD + Axon  
- RabbitMQ  
- Redis  
- MongoDB / MySQL  

---

## 七、关键设计点

- 幂等处理  
- 轨迹事件去重  
- 缓存分层设计  
- 异步化处理  

---

## 八、核心处理伪代码


    save(event)
    publishDomainEvent(event)
