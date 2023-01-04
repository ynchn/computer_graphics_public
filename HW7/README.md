# HW7 Report

Result image:\
![result](./out.ppm)

* I copied over the code in `void Renderer::Render(const Scene& scene)` and `bool rayTriangleIntersect(...)` from HW6. The usage of `castRay(...)` was slightly modified to work with the new code skeleton.

* In `Bounds3.hpp`, I implemented `inline bool Bounds3::IntersectP(...)`, using `dirisNeg` (this direction parameter deterined how I find `tmax` and `tmin` of each axis). Following the algorithm described in lecture 16, I was able to find `t_enter` and `t_exit` to determine if ray bound intersect, returning `true if (t_enter < t_exit) && (t_exit >= 0)`.

* In `BVH.cpp`, I implemented `Intersection BVHAccel::getIntersection(...)`. The parameter `dirIsNeg` used in `IntersectP(...)` is set here.
  
  First we check if the ray intersects with the node's bounding box. If not, then we just need to return and empty `Intersection` object. Otherwise, we need to check the node further.

  * For the base case, when we're at a leaf node, i.e. both children of the current node are `NULL`. We just need to return what `node->object` intersects.
  * For the recursive case, we get intersections from the left and right children of the current node, and returns the closer intersection.
