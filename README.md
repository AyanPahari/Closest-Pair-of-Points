# Closest-Pair-of-Points
Closest Pair of Points Problem using Divide and Conquer

## Pseudo-code of the algorithm

    Step 1- Sort the points on x-coordinate and on y-coordinate.

    Step 2- Divide them into two halves
        2.1) Let the value of the median(when sorted on x-coordnates) be x_mid.
        2.2) Split x into x_left and x_right. Points in x_left have the value when x-coordinate <=x_mid and x_right contains the rest of the coordinates.
        2.3) Split y into y_left and y_right. Points in y_left have the value when y-coordinate <=x_mid and y_right contains the rest of the coordinates.
        2.4) Let min1 and min2 be the two pairs of the form (x1,y1) and (x2,y2) containing the closest pair of points.

    Step 3- Recursive calls
        3.1) Let d1= distance of the closest pair on input (x_left,x_right) and d2=distance of the closest pair on input (y_left,y_right).
        3.2) Compute d=min(d1,d2) and similarly the closest pairs min1 and min2.
        3.3) Around x_mid we will consider a band of length d on both sides. Anything outside of the band will have a distance >d.

    Step 4- Combine step
        4.1) From the vector sorted on the basics of y-coordinate extract all the points for which point.x > x_mid – d and put in a separate vector called band.
        4.2) Scan band from top to bottom, comparing each point against a finite number of points(7 points) and computing the distance between them. 
             And if we get a distance smaller than the current distance then update both the distance and the closest pairs. This step will take O(n) time.

## Running time analysis of the Algorithm
    Let the time complexity of the above algorithm be T(n). As a preprocessing step we have used mergesort to sort the points on the basics of x-coordinates and y-coordinates respectively which runs in O(nlogn) time.
    The sorted points are then fed into the function which divides the set of points into two halves and recursively calls them. After dividing into parts it finds the band in O(n) time. Finally finds the closest points in the band in O(n) time.
    
    T(n)= 2T(n/2) + O(n) + O(n)
    T(n)=2T(n/2) + O(n)
    T(n)=O(nlogn)


- Proof of correctness of the algorithm can be found in the Report file.

