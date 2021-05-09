# Hand Gesture Recognition

This project uses OpenCV to recognize "rock", "paper", and "scissors" hand gestures from a video in order to play rock paper scissors.

### Python libraries required

* numpy
* cv2
* imutils

### Other requirements

* a webcam

### Usage details

Run the included IPython notebook. There are two different applications: the first recognizes hand gestures from livestream and the second allows you to play rock paper scissors with yourself or another person on camera.

#### Gesture recognition from livestream

Allow the region in the bounding box to remain stationary for a few moments so the background model can initialize. Place your hand in the bounding box and your gesture will be displayed on-screen. Additionally, your hand contour will be displayed in red and the convex hull in green. An additional window displaying the foreground mask is also shown.

#### Playing rock paper scissors

Allow the regions in the bounding boxes to remain stationary for a few moments so the background models can initialize. Have each player place a hand in one bounding box. The winner will be displayed on-screen.

### Tips/Troubleshooting

* Press `q` to quit the application.
* A dark, stationary background works best for hand detection.
* You can adjust the coordinates of the bounding box by editing the values of `start_point` and `end_point`. They correspond to the coordinates of the top-left and bottom-right of the box, respectively.
* If there was movement in the background during initialization, or there is some permanent camera/background shift after initialization, the foreground mask will be messed up. You'll have to quit and re-execute the cell.
* If the foreground mask doesn't look correct, try adjusting the value of `threshold` in `getForegroundMask()`. Lower values will let more into the foreground mask, and vice versa.
* If your gesture isn't being detected, try moving your hand towards/away from the camera. Detection is distance-sensitive. If that still doesn't work, try adjusting the value of `thresh` in `recognizeGesture()`. Lower values will work better for hands further from the camera, and vice versa.