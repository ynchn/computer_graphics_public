# README for HW8


* For `Rope::rope(...)`, I created a new `Mass` object for each of the nodes, set each node's position to `start + ((end - start)/(num_nodes - 1))*i`, i.e. position of the first node plus `i` number of spaces between node, and created a new `Spring` object for between each node.

* For `void Rope::simulateEuler(...)`, in the springs loop, I implemented Hooke's law, and added the calculated spring force to both of the masses with the correct direction. Then, in the masses loop, I first added gravitational force to `m->forces`, and calculated the acceleration for the current mass.

  * For Explicit Euler, formula: `x(t+1) = x(t) + v(t) * delta_t`. I used `m->velocity` to update `m->position` first, before updating `m->velocity`.

  * For Implicit Euler, formula: `x(t+1) = x(t) + v(t+1) * delta_t`. I first calculated `v(t+1)` by adding `acceleration * delta_t` to `m->velocity`, before using it to calculate `x(t+1)` to update `m->position`.

  After that, I reseted all forces on each mass.

* For `void Rope::simulateVerlet(...)`, in the springs loop, I used the same code for Hooke's law to calculate a half displacement, used to set the positions of the masses on either side of each spring.

  Depending on how the nodes are pinned, if both sides of the spring are pinned, then no displacement happens for either node. If one side of the spring is pinned, the other side gets the entire displacemnet instead of half. Otherwise, both nodes gets half of the displacment in opposite directions.

  In the masses loop, `m->last_position` is `x(t-1)`. A damping factor of `0.00005` is added for Part 4. Following the given formula, `m->position` is set to `x(t) + (1 - dampling_factor) * (x(t) - x(t-1)) + a(t) * delta_t * delta_t`. Resulting in the green verlet rope to slowly become still in the end.
