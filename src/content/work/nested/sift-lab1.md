---
title: Lab 1 | Recognition of Object Instances 
publishDate: 2023-10-23 16:54:00
img: /labs/lab2_filtering/minia.png
img_alt: SIFT
description: |
 Course: Multimedia Indexing
tags:
  - Scale-Invariant Feature Transform
  - Interest Points Detection
  - Lab Report
---
<style>
  pre{
    border-radius: 5px;
    margin: 0 2px;
    background-color: #f2f2f2;
  }
</style>

---

#### Introduction

Scale-Invariant Feature Transformis is a feature detection, matching and description algorithm used for various Computer Vision tasks, such as object recognition, robotic mapping, image stiching, etc.

This lab will take interest in the object recognition task. The goal will be to *match interest points between a natural image pair.*
A **natural pair** is a set of two pictures of the same object taken separately. This means that the second image is not a simple geometrical transformation of the original image (translation, rotation, etc.).

Using such a matching allows to *classify* images by comparing it to an already labeled database and attributing it the label of the closest images found in said database.

We will be using MatLab and following this [lab' statement](https://www.di.ens.fr/willow/events/cvml2013/materials/practicals/instance-level-recognition.html).
