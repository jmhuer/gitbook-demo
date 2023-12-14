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

# Sound Activity Recognition and Annomaly detection

 <sub> <a href="https://jmhuer.github.io/mini_book/_build/html/docs/portfolio.html" style="color: red; text-decoration: underline;text-decoration-style: dotted;">← Back to Projects</a> </sub>

<img src="../.gitbook/assets/audio.png" align="center"/>

<br>

 In this post I will explore a few approaches and applications of sound classification. We use both a standard appraoch using spectrograms + CNNs and a more sophisticated approach using transformers on spectrogram patches. We are testing two different methods:
 - Spectogram + CNN (pre-trained AlexNet). Here is the repository: [specCNN_sound_classification](https://github.com/jmhuer/specCNN_sound_classification)
 - Spectogram + Transformer (16x16 image patches). Here is the repository: [spectogram_transformer](https://github.com/jmhuer/spectogram_transformer)

<br>

## Activity Recognition with Spectrogram Transformer
---

First I built a system that can detect what kind of activities are going on in a room and change color of a light automatically. To achieve this, we pre-train on collection of AudioSet data, and fine-tune on data collected from my room. Each class has about 100 labeled examples of 3 second clips. Training accuracy 93%, validation accuracy is 89%

<br>
 <div align="center">   <iframe width="560" height="315"
src="https://www.youtube.com/embed/snkbodqne9o"
frameborder="0"
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
allowfullscreen
></iframe></div>

<br>
<br>

## Laugh Detection + Philips Hue Bulb
---

Using AudioSet data we train a laugh detection sound classification and interpret the output for the laugh class as an intensity measure [0,1] to control the intensity of a philips hue bulb [philips-hue-api](https://github.com/topics/philips-hue-api)

<br>
 <div align="center">   <iframe width="560" height="315"
src="https://www.youtube.com/embed/bOG9VGZbTj8"
frameborder="0"
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
allowfullscreen
></iframe></div>

<br>
<br>

## Service Diagnostics Running iOS CoreML
---

Finally, we test anomaly sound classification. First, we collect labeled examples of the normal sound from a dryer and train a CNN-Autoencoder. During training we find the average latent-space code of the autoencoder training data; at inference time we measure distance from average-latent-space-code to inference--latent-space-code and accept or reject a sound according to a threshold. The threshold can be determined with different methods, we use the max distance of training code as a threshold.

To explore applications, we implement this model on [iOS CoreML](https://developer.apple.com/documentation/coreml) and run tests using an iPad.


<br>
 <div align="center">   <iframe width="560" height="315"
src="https://www.youtube.com/embed/eoMQt4muwW4"
frameborder="0"
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
allowfullscreen
></iframe></div>



<br>
<br>


