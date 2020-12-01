---
title: flume
---

## flume如何保证数据不丢失？
## 配置方面：TailDir source + File channel + HDFS sink
## 常见配置项：
### 🌌**source**
#### **Spooling Directory Source**：^^a1.sources.src-1.type = spooldir^^
##### 监测并读取指定文件夹下的新增文件，并读取内容，准实时级别
#### **Taildir Source**
##### 监测多个文件
##### ```xml
##### a1.sources = r1
a1.channels = c1
a1.sources.r1.type = TAILDIR
a1.sources.r1.channels = c1
a1.sources.r1.positionFile = /var/log/flume/taildir_position.json
a1.sources.r1.filegroups = f1 f2
a1.sources.r1.filegroups.f1 = /var/log/test1/example.log
a1.sources.r1.headers.f1.headerKey1 = value1
a1.sources.r1.filegroups.f2 = /var/log/test2/.*log.*
a1.sources.r1.headers.f2.headerKey1 = value2
a1.sources.r1.headers.f2.headerKey2 = value2-2
a1.sources.r1.fileHeader = true
a1.sources.ri.maxBatchCount = 1000
##### ```
#### **Kafka Source**
##### 作为消费者，从Kafka的 **Topic** 读取数据
#### **Avro Source**：^^a1.sources.r1.type = avro^^
##### 监听Avro端口并接受Event
### channel
###
##
