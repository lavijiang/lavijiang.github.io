---
title: mit6.824-notes
date: 2022-01-25 14:33:04
tags:
---
# Introduction

## Why need distributed system
- 使用并行计算提高计算性能
- 提供容错机制
- 系统天然物理分布
- 将有安全隐患的代码隔离

## Problems and challenges
- 并发（同步、异步）带来的复杂交互
- 局部错误
- 如何设计可以有效利用资源，最终提升到理想的性能

## Scalability Availability and Consistency
- 实现强一致性代价很大，现实中经常使用弱一致性系统  
- BASE理论和CAP理论

# GFS
## Why Hard  

![](/images/why_hard.png)
