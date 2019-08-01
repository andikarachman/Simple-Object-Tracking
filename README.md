# A Simple Object Tracker with OpenCV

Track objects using Python and OpenCV.

## Dependencies
  * opencv
  * numpy

## Command format

_$ python object_tracker.py [-h] [-v VIDEO] [-t TRACKER]_

- VIDEO: path to input video file. If it is not specified, the input will be image streaming from webcam.
- TRACKER: the type of tracker that will be used. There are 7 types of tracker that can be used:

1. BOOSTING Tracker ("boosting"): Based on the same algorithm used to power the machine learning behind Haar cascades (AdaBoost), but like Haar cascades, is over a decade old. This tracker is slow and doesn’t work very well. Interesting only for legacy reasons and comparing other algorithms. (minimum OpenCV 3.0.0)
2. MIL Tracker ("mil"): Better accuracy than BOOSTING tracker but does a poor job of reporting failure. (minimum OpenCV 3.0.0)
3. KCF Tracker ("kcf"): Kernelized Correlation Filters. Faster than BOOSTING and MIL. Similar to MIL and KCF, does not handle full occlusion well. (minimum OpenCV 3.1.0)
4. CSRT Tracker ("csrt"): Discriminative Correlation Filter (with Channel and Spatial Reliability). Tends to be more accurate than KCF but slightly slower. (minimum OpenCV 3.4.2)
5. MedianFlow Tracker ("medianflow"): Does a nice job reporting failures; however, if there is too large of a jump in motion, such as fast moving objects, or objects that change quickly in their appearance, the model will fail. (minimum OpenCV 3.0.0)
6. TLD Tracker ("tld"): I’m not sure if there is a problem with the OpenCV implementation of the TLD tracker or the actual algorithm itself, but the TLD tracker was incredibly prone to false-positives. I do not recommend using this OpenCV object tracker. (minimum OpenCV 3.0.0)
7. MOSSE Tracker ("Moses"): Very, very fast. Not as accurate as CSRT or KCF but a good choice if you need pure speed. (minimum OpenCV 3.4.1)
