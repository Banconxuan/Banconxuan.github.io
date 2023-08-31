---
layout: post
title: "[Paper Reading] StreamMapNet Streaming Mapping Network for Vectorized Online HD MapConstruction"
subtitle: 
categories: [Paper Reading]

banner:
  image: "/assets/images/banners/paperreading.png"
  opacity: 0.618
  background: "#000"
  height: "100vh"
  min_height: "38vh"
  heading_style: "font-size: 4.25em; font-weight: bold; text-decoration: underline"
  subheading_style: "color: gold"

tags: [Static Perception, BEV]
---

## Summary
1. Multi-Point Attention: 一个query过mlp生成N个点和对应的weight，采样N个点的特征并使用生成的weight加权求和更新query。作者称这是远距离的关键。
2. streaming strategy: bev特征在longterm传输上比较困难，因此使用query的传递方式。将query生成的点使用pose转换到当前帧后，继续更新query。可以当成用以往帧结果当作当前帧的proposal，因此可以在遮挡出表现较好。
3. 更改了nuscenes的train/val 划分。nuscenes的train/val划分有overlap的部分，动态还好，静态影像较大。所以使用新划分来避免。
