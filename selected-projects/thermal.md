---
jupytext:
  text_representation:
    extension: .md
    format_name: myst
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

## Automate Data Labeling using Temperature Differential

 <sub> <a href="https://jmhuer.github.io/mini_book/_build/html/docs/portfolio.html" style="color: red; text-decoration: underline;text-decoration-style: dotted;">← Back to Projects</a> </sub>

<img src="../.gitbook/assets/thermal.png" align="center" />

<br>

Data labeling for object detection/segmentation is expensive to acquire.  In this post we show we can sped up this proesses of labeling data for certain objects using a thermal camera, and standard computer vision techniques. We can create mask or ROI annotations depending on annotations of interest.

<br>


## Introduction
---

There are many popular dataset for computer vision, but for custom objects one might be required to collect and label data manually. For example, see below: 

<img src="../.gitbook/assets/labelex.gif" width="80%" align="center"/>

<br>
<br>

In this post I propose a new method that can be applied in two ways:
- To speed up objects labeling process to train supervised computer vision models
- For object localization in combination with a classification model, for a hybrid object detection approach. This can be useful in certain cases were you have a fixed camera, for example: refrigerator cameras, parking lot cameras, security cameras, etc.  


We have some requirements for when this method can be used. Primarily, we require a specific setting where the objects of interest have a noticeable temperature difference. Such as:
- Living things
- Stove top cooking, ovens, or cooking in general
- Items that can be cooled before collecting data

Here is the code used: [Auto-label](https://github.com/jmhuer/mask_from_thermal_image)


You will need a [Flir-camera](https://www.amazon.com/FLIR-ONE-Pro-Professional-Smartphones/dp/B072J49BX7/ref=sr_1_3?keywords=FLIR%2BInfrared%2BCamera&qid=1641504646&sr=8-3&th=1) specifically since it is crucial to be able to take an image with both RGB and Thermal sensors and calibrate overlay between the two images.

<br>

##  Method
---

The method consists of the following steps.

**Step 1**: Fix the Flir thermal/RGB camera
- It is possible to skip this step and take handheld images however you will need to be careful with your calibration. 

**Step 2**: Specify expected temperature of item of interest
- For example: *10**C** < temp > 30**C** or temp > 30**C*** and classes name

**Step 3**: Run
- Apply thermal image postprocessing: *Bucket fill -> K-means -> Find contour*, to obtain localization of objects. 
- Extract RGB image using python  
- Store RGB image and labeled image in desired format: ROI or PNG Mask

<br>


##  Stove Top Examples
---

Here we have an example applying our proposed method on food being cooked. This setting provides us a very natural temperature differential since the pan is almost always hotter than the food. Of course there are exceptions but this method is not meant to sutable for all settings, otherwise we wouldnt need any neural nets!

<img src="../.gitbook/assets/thermalfood.png" align="center"/>

<br>
<br>


##  Cooling Down Objects 
---

Here we have an example applying our proposed method on items that were left in the fridge for a few min. This creates the necessary temperature differential:

<img src="../.gitbook/assets/thermalwarm.png" align="center"/>

<br>
<br>



##  Humans or Animals
---

Finally mammals usually have a body temperature higher than the surroundings. In these settings our method can be applied naturally

<img src="../.gitbook/assets/thermal.png" align="center" />

<br>
<br>


##  Conclusion 
---

Altough these are just a few examples you can use the code to test and try new settings. Applying what we have shown here can save you many hours of labeling data, or help enchace certain computer vision systems!

<br>
<br>











