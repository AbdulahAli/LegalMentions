in raytracing and path tracing.. It is very simple, it has to be simple: My method is using linear interpolation to calculate whether the hit point is between or outside the triangle's edges, 
lets suppose a triangle with point  A, point B and point C,  First we need the x1 and x2 where the hitPoint is between in the x axis, to calculate x1 we use the fallowing expression:
 
float x1 = lerpf(A.y, C.y, t1);
float x2 = lerpf(B.y, C.y, t2);
//Where t1 is
t1 = (hitPoint.y - A.y) / |A.y - C.y|;
// And t2 is
t2 = (hitPoint.y - B.y) / |B.y - C.y|;

//Then we check..
if(x1 < hitPoint.x < x2){ return true; }

in cuda or any programing language

This code checks the hit in the x axis ,
it is just the same in the y axis 


Then we apply this method to work on the z axis as well, by dividing XY coordinates of ABC points by the Z coordinate of these points, or multiplying the rest sides of the equation by the value of Z and simplifying the inquality.


This method has some optimizations and simplfications and all of them are considered in this method.
