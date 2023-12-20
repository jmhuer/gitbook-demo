# Sound Activity Recognition and Annomaly detection

[← Back to Projects](https://jmhuer.github.io/mini\_book/\_build/html/docs/portfolio.html)

\


In this post I will explore a few approaches and applications of sound classification. We use both a standard appraoch using spectrograms + CNNs and a more sophisticated approach using transformers on spectrogram patches. We are testing two different methods:

* Spectogram + CNN (pre-trained AlexNet). Here is the repository: [specCNN\_sound\_classification](https://github.com/jmhuer/specCNN\_sound\_classification)
* Spectogram + Transformer (16x16 image patches). Here is the repository: [spectogram\_transformer](https://github.com/jmhuer/spectogram\_transformer)

\


## Activity Recognition with Spectrogram Transformer

***

First I built a system that can detect what kind of activities are going on in a room and change color of a light automatically. To achieve this, we pre-train on collection of AudioSet data, and fine-tune on data collected from my room. Each class has about 100 labeled examples of 3 second clips. Training accuracy 93%, validation accuracy is 89%

\
\
\


## Laugh Detection + Philips Hue Bulb

***

Using AudioSet data we train a laugh detection sound classification and interpret the output for the laugh class as an intensity measure \[0,1] to control the intensity of a philips hue bulb [philips-hue-api](https://github.com/topics/philips-hue-api)

\
\
\


## Service Diagnostics Running iOS CoreML

***

Finally, we test anomaly sound classification. First, we collect labeled examples of the normal sound from a dryer and train a CNN-Autoencoder. During training we find the average latent-space code of the autoencoder training data; at inference time we measure distance from average-latent-space-code to inference--latent-space-code and accept or reject a sound according to a threshold. The threshold can be determined with different methods, we use the max distance of training code as a threshold.

To explore applications, we implement this model on [iOS CoreML](https://developer.apple.com/documentation/coreml) and run tests using an iPad.

\
\
\
