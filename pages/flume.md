---
title: flume
---

## flume如何保证数据不丢失？
## 配置方面：TailDir source + File channel + HDFS sink
## 常见配置项：
### 🌌**source**
#### ref:https://flume.apache.org/FlumeUserGuide.html#flume-sources
#### **Spooling Directory Source**：^^a1.sources.src-1.type = spooldir^^
##### 监测并读取指定文件夹下的新增文件，并读取内容，准实时级别
#### **Taildir Source**：^^a1.sources.r1.type = TAILDIR^^
##### 监测多个文件，记录消费位置
#### **Kafka Source**：^^tier1.sources.source1.type = org.apache.flume.source.kafka.KafkaSource^^
##### 作为消费者，从Kafka的 **Topic** 读取数据
#### **Avro Source**：^^a1.sources.r1.type = avro^^
##### 监听Avro端口并接受Event
##
### 🌌**channel**
#### **FileChannel**：
##### 使用基于本地磁盘的事务实现模式
###
##
