# HW5 Report

Resulting images:\
![naive bezier 1](./naive_bezier_curve_0.png)\
![naive 2](./naive_bezier_curve_1.png)\
![recursive bezier 1](./recursive_bezier_curve_0.png)\
![recursive 2](./recursive_bezier_curve_1.png)\
![both naive and recursive bezier 1](./yellow_bezier_curve_0.png)\
![both 2](./yellow_bezier_curve_1.png)

I modified the `bezier()` and `recursive_bezier()` in `main.cpp`.
In `bezier(const std::vector<cv::Point2f> &control_points, cv::Mat &window)`, like in `naive_bezier()`, I increment `t` by 0.001. Then, in each loop, I call `recursive_bezier()` where De Casteljau’s Algorithm is implemented.

In `recursive_bezier(const std::vector<cv::Point2f> control_points, float t)`, I recursively subdivide each line segment using `lerp()` until there is only 1 point left, which is what we want to return.
