# measure-width-of-finger
Get the width of fingers according the photo with a hand and a coin besides the hand.
![image](https://github.com/livezingy/measure-width-of-finger/blob/master/measureFinger.gif)

# How to Run the program
1. open the cmd.exe and enter the path where measureSize_V1.0.py is located.

2. Take the testPalm.png as the test image, input the command and Run:
```	
    python measureSize_V1.0.py -i testPalm.png -w 1
```	

3. You could change the testPalm.png to your own test image name.
    -i : the name of the test image.
    -w : the width of the reference(coin). The unit of the results will be the same with the width.
    
4. Please make sure that reference(coin) is left on the hand. 

5. Please make sure that the contrast between background and foreground is obvious.

# Process steps
1.  Threshold the source image and Distinguish the reference and the hand.
![image](https://github.com/livezingy/measure-width-of-finger/blob/master/FingerThresh.png)

2.  Calculate the “pixels per metric” ratio according to the reference and the input parameter "-w".

3.  Find the keypoints of the hand with convexHull and convexityDefects.
![image](https://github.com/livezingy/measure-width-of-finger/blob/master/FingerKeypoints.png)

4. Get the smallest circumscribed rectangle of the finger and caculate their width and height.
![image](https://github.com/livezingy/measure-width-of-finger/blob/master/FingerMeasure.png)
