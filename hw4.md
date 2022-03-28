## 1. Detection & Segmentation
Image detection would be very useful for video surveillance technology. Unlike image segmentation, which classifies every single pixel in the image (utilizing skip connections to maintain precision past the vaguery of the bottleneck), image detection creates bounding boxes to label entire objects. Combining this with video surveillance would be useful, as you could analyze each frame (or certain frames, such as those which have detected movement of some kind, through other means) and then point out objects on the screen, such as people, or an object that has fallen or been moved, or even a difference in background objects such that you could see if an object was missing (by detecting it from the prior image & not detecting it in the new one).

Image segmentation could be used

## 2. YOLO, and YOLO vs RCNN
As the name suggests, You Only Look Once (YOLO) looks at each image only once at full size in order to generate its image detection bounding boxes, which means it's very fast. 

## 3. Negative Log Likelihood


## 4. Reverse Mode Trace
