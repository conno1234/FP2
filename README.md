# Final Project Assignment 2: Exploration (FP2)
DUE Wednesday, March 23, 2016

## My Library: graphics/turtle
My name: Connor McGrory

For this assignment, I took a look at the turtles graphics library.  Using this along with a bit of
recursion, I was able to create some interesting images by simply drawing a line and then turning
at a specific angle.  Looping this created some of the images you will see below.

The code is broken down into two seperate functions.  The first one, ```make-image``` creates an image
by drawing fixed length lines and turning at a fixed angle.  To put it simply, the below code is looped:
```
(draw dist)  ;; dist and angle are variables passed to the make-image function
(turn angle)
```
Then the real interesting images are made in the second function, ```make-collage```.
This function repeatedly calls the ```make-image``` function with the same values, but
moves the turtle in between each drawing.  This makes a beautiful collage of the image
generated by ```make-image```.

Inside the ```make-collage``` function, the ```make-image``` function is called:
```
  (cond ((> iters2 0)                     ;; iters2 is the number of images left to draw
         (make-image dist angle iters1)   ;; draw the image
         (make-collage dist angle iters1 (- iters2 1)))  ;; recurse
        (else
         (display "Complete!\n"))))       ;; display message to the user that the collage is complete
```

Below are some images I created with this program.

![screenshot1](https://cloud.githubusercontent.com/assets/11009351/14005960/b25a5824-f13e-11e5-965b-1067407879d3.png)
![screenshot2](https://cloud.githubusercontent.com/assets/11009351/14005968/c27ef976-f13e-11e5-9c4a-e5fb77c309fb.png)
![screenshot3](https://cloud.githubusercontent.com/assets/11009351/14005975/ca6fd1fa-f13e-11e5-8df9-75e95a5d2e93.png)
![screenshot4](https://cloud.githubusercontent.com/assets/11009351/14005983/d516677c-f13e-11e5-9098-572b8552026c.png)
