# Approximating Pi - with visualization

The mathematical constant _pi_ is approximately equal to 3.1415.

Determine an approximation of _pi_ by filling the square between [-1, -1] and [1, 1] with randomly created points and calculating how many of these points lie within the circle centered at [0, 0] with radius 1. This ratio should be approximately equal to _pi/4_. Visualize the process.

Steps for calculation:

- create an array of _n_ random points between [-1, -1] and [1, 1]
- determine their distance from the origin by calculating _sqrt(x^2 + y^2)_ for each point
- filter out all points that are further away than 1
- determine what ratio of points is left
- multiply by 4 - the result is an approximation of pi.

Steps for visualization:

- plot the inner points with small dots, plot the outer points with small dots in grey. Start out with 10000 dots.
- draw a circle with radius 1
- set the axis scale to _scaled_
- set the axis ranges to -1...1
- set the title to: "Pi is approximately ..."

Start out with 1 million points. You can increase the number of points, but watch your RAM usage.
