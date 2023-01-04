# HW2 Report

You can access the bonus feature by running the program from the command line which saves the resulting image.

To run the bonus part:

```bash
./Rasterizer -r 20 rod 1 2 3 bonusimage.png
# Runs the program, rotates the triangle 20 degrees around axis (1, 2, 3) using Rodrigues' Rotation Formula, and saves the output to a file named bonusimage.png

# The general formatting for the bonus part command:
./Rasterizer -r <degrees_to_rotate> rod <n_x> <n_y> <n_z> <image_name.png>
```

---

Generated images located in the `./imgs/` folder:

- `no_rotation.png`: original triangle without rotation
- `rot20.png`: rotate 20 degrees (`./Rasterizer -r 20 rot20.png`)
- `rot45.png`: rotate 45 degrees (`./Rasterizer -r 45 rot45.png`)
- `rot180.png`: rotate 180 degrees (`./Rasterizer -r 180 rot180.png`)
- `rod45001.png`: rotate 45 degrees around axis (0, 0, 1) (`./Rasterizer -r 45 rod 0 0 1 rod45001.png`)
- `rod45111.png`: rotate 45 degrees around axis (1, 1, 1) (`./Rasterizer -r 45 rod 1 1 1 rod45111.png`)
