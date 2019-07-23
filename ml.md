---
layout: post
title: Machine Learning
---

Our approach is to predict Wi-Fi loss 15 seconds ahead of time based on the past 60 seconds. To get the best possible result, we evaluated various ML algorithms, feature vectors and training sets. An overview will be given here.

# Feature Vectors
We evaluated three different feature vectors. The first one is the full feature vector, as can be seen below:

* Pressure (delta)
* Absolute Pressure
* Linear Acceleration (all axes separately)
* Linear Acceleration (all three axes together)
* Step Counter
* Power Data (if the phone is charging or not)
* Remaining Battery Capacity
* Gravity (all axes)
* Gyroscope
* Magnetic Field (all axes)
* Absolute Phone Orientation
* Phone Rotation (all axes)
* Wi-Fi Freuency (2.4 GHz or 5 GHz)
* Wi-Fi Speed (IEEE 802.11b, IEEE 802.11n, ...)
* Wi-Fi RSSI

Additionally, we used a reduced feature vector, containing the following sensors:

* Pressure (delta)
* Linear Acceleration (all three axes together)
* Step Counter
* Power Data (if the phone is charging or not)
* Gravity (Z-axis)
* Wi-Fi Freuency (2.4 GHz or 5 GHz)
* Wi-Fi Speed (IEEE 802.11b, IEEE 802.11n, ...)
* Wi-Fi RSSI

Finally, we also used just the Wi-Fi RSSI for comparison.

# Algorithms
Besides using different feature vectors, we also used different ML algorithms and different configurations.

Algorithm | Configuration
----------|--------------
Radom Forest      | 10 Trees<br />20 Trees<br />25 Trees
Multi-layer Perceptron Classifier | 1 Layer, 100 Neurons (NN1)<br />3 Layers, 100, 200, 300 Neurons (NN2)<br />5 Layers, 400 Neurons each (NN3)

# Training and Test Sets
Data from 5 volunteer testers were collected for this work. Thus, we tried two different Training and Test sets. First, all data was combined and than split randomly in 70:30 relation with 70% for training the Neural Network and 30% for testing. In the second approach the data was split per user, resulting in a model that was trained on a specific user.

# Results
{% include random-forest.md %}
{% include random-nn.md %}
{% include user-nn-reduced.md %}

## Notebooks
Alls Jupyter Notebooks can be downloaded from our [GitHub repo](https://github.com/umr-ds/seamcon-learning-wifi-loss). We provide a `Dockerfile` so that you can start the Docker container and see all steps done from preparing the data until the learning evaluation directly in a Jupyter Lab. Just check out the mentioned repo, build the container and start it. Please provide the right parameters in the commands below:

```
docker build .
docker run -p=8888:8888 -v <PATH_TO_SQLITE_TABLES>:/jupyter <CONTAINER_ID>
```

The output of the container will contain a URL (similar to `http://0.0.0.0:8888/?token=9b7e8f0aaec254f72bbed67074deae7bab1ceb6e8473e917`). Replace `0.0.0.0` with `localhost` or `127.0.0.1` and open the URL in your browser. That' it.