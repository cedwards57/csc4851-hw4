## 1. Detection & Segmentation
Image detection would be very useful for video surveillance technology. Unlike image segmentation, which classifies every single pixel in the image (utilizing skip connections to maintain precision past the vaguery of the bottleneck), image detection creates bounding boxes to label entire objects. Combining this with video surveillance would be useful, as you could analyze each frame (or certain frames, such as those which have detected movement of some kind, through other means) and then point out objects on the screen, such as people, or an object that has fallen or been moved, or even a difference in background objects such that you could see if an object was missing (by detecting it from the prior image & not detecting it in the new one).

Image segmentation could be used for brain scans, for predicting precise boundaries of parts of the brain, and this could further be used to analyze the properties of these pieces in comparison to the equivalents in others' brains. Combined with other image evaluation/processing models or pieces, it could use these specific segmented pieces to be a predictor of disease

## 2. YOLO, and YOLO vs RCNN
As the name suggests, You Only Look Once (YOLO) looks at each image only once at full size in order to generate its image detection bounding boxes, which means it's fast. It achieves this by putting various grids on the image it's looking at, and determining what objects overlap with what cells. It uses these for bounding box regression, where it finds more precise bounds over each thing. In addition, it uses Intersection Over Union (IOU) to find how well the predicted object boundary overlaps with the real boundary, and it gives confidence scores for each object class.

RCNN looks at an image to propose a bunch of different regions within it to analyze for object classes, whereas Faster-RCNN takes an image and proposes anchor boxes within it, which get compared to the real bounding boxes, also using IOU for evaluation of foreground vs background areas against the real boundaries. YOLO uses the grid system, and its simpler architecture makes it faster than Faster-RCNN.

## 3. Negative Log Likelihood
I do not understand this question.

the Binary Cross Entropy function is a follows:<br>
εi = -(1/N)Σ[yi\*log(y'i) + (1-yi)\*(log(1-y'i)]

As epsilon approaches zero, data approaches convolutional cross entropy of standard distribution.

## 4. Reverse Mode Trace
See `hw4_4.png`. I've included the graph at the top to make clear what I am interpreting here, since there is both a multiplication sign AND a plus sign leading to the 2 and it's unclear what its role is, so I interpreted it as connecting to both of its preceding elements individually.

It's notable that dy/dx = 1, a constant, meaning that even when the gradient is zero as the question asks, the answer would still be at least 1. Without the direct skip connection of x -> y, an x=0 gradient could zero out everything else, even in a situation where v4 is evaluated before the derivative is taken. This helps avoid a vanishing gradient, which helps us see one big advantage of using skip connections.