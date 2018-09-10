**University of Pennsylvania, CIS 565: GPU Programming and Architecture,
Project 1 - Flocking**

* Zichuan Yu
  * [LinkedIn](https://www.linkedin.com/in/zichuan-yu/), [Behance](https://www.behance.net/zainyu717ebcc)
* Tested on: Windows 10.0.17134 Build 17134, i7-4710 @ 2.50GHz 16GB, GTX 980m 4096MB GDDR5

## Screenshots

### Static

### Gif

## Performance Analysis

### Change number of boids, with visualization

![fps_with_visualization](images/FPS%20with%20visualization.png)

### Change number of boids, without visualization

![fps_without_visualization](images/FPS%20without%20visualization.png)

### Fix number of boids, change block size, without visualization

![fps_without_visualization_blocksize](images/FPS%20without%20visualization%20block%20size.png)

## Questions

### For each implementation, how does changing the number of boids affect performance? Why do you think this is?

Yes. The two advanced methoeds have much better preformance. Because we are saving a lot of unnecessary checkings. The larger the number of boids, the more we save.

### For each implementation, how does changing the block count and block size affect performance? Why do you think this is?

When the block size is small, the performance is not good. When it is larger or equal to 32, the performance is largely improved and doesn't change much as we increase the block size. Not sure why this happens. **Maybe** related to wrap size.

### For the coherent uniform grid: did you experience any performance improvements with the more coherent uniform grid? Was this the outcome you expected? Why or why not?

I experience much performance improvements with it. Because when we use scattered memeory method, why are accessing a random memeory place everytime we need to check a neigboring boids. Yet in coherent method, we only do this once when we shuffle the pos and vel.

### Did changing cell width and checking 27 vs 8 neighboring cells affect performance? Why or why not? Be careful: it is insufficient (and possibly incorrect) to say that 27-cell is slower simply because there are more cells to check!

When the number of boids becomes large, int 27 cells' case though we check more neighbors, the actuall boids we need to iterate through is actually less, so the performance is better.

