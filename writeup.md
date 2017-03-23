#**Finding Lane Lines on the Road**

### Reflection

###1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 8 steps:
1) First, I converted the images to grayscale.
2) Then I apply Gaussian blur.
3) After that, I used Canny method to find edges.
4) I used a mask to only include region containing the lane.
5) I used hough transform to generate line segments.
6) I used polyfit to convert line segments to two lines (one for left, one for right).
7) I drew the left and right line on top of the original image.
8) I used the region mask to mask out lines out of the region of interest.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by using a polyfit to find a line that pass the end points of line segments. Because there are two lines to fit, one for left and one for right, I used the slope of each line segments to group them to left group and right group before applying polyfit.

###2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when there is a left turn. The left/right line segments grouping logic would break.

Another shortcoming could be there are multiple parameters that are hand-tuned, for example, the region of interest. If lane falls out of the region, the pipeline would fail to find lines.


###3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
