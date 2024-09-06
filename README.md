# BMP2RIC
 Converts bitmap files/images into [Robot Is Chill](https://github.com/balt-dev/robot-is-chill) renders.
# USAGE
1. Download index.html and open it or head to [https://dogeiscut.github.io/BMP2RIC/](https://dogeiscut.github.io/BMP2RIC/)
2. Upload a .bmp (bitmap) file to the 'Choose File' button.
4. Copy your result from the result field at the bottom.
# EXPERIMENTAL ALGORITHM
By default, this tool used greedy meshing, but if you enable the experimental algorithm, it does this instead:
1. Pick a random pixel from the non processed pixels grid.
2. Create a 1x1 rect there
3. Check if expanding up would hit processed, the bounds, or other color pixels, if so, skip 4
4. Expand upwards
5. Check if expanding right would hit processed, the bounds, or other color pixels, if so, skip 6
6. Expand rightwards
7. Check if expanding down would hit processed, the bounds, or other color pixels, if so, skip 8
8. Expand downwards
9. Check if expanding left would hit processed, the bounds, or other color pixels, if so, skip 10
10. Expand leftwards
11. if all direction checks fail, finish the rectangle, mark the pixels as processed, and remove them from the non processed grid
12. repeat 1-11 until the non processed grid is empty
13. repeat 1-12 as many times as the iteration count and saving the rectangles only if the count is lower than the previous.

If allow overlap is enabled, the algorithm when expanding will ignore same colored pixels.
# CHANGELOG
- **1.0.0**: Release, page is very very basic, and there are no settings, only an upload box.
- **2.0.0**: Complete overhaul, new preview, settings, output box, etc.
- **2.1.0**: Added the experimental algorithm and its settings.
- **2.1.1**: Adjusted the info descriptions of some of the experimental algorithm stuff.
- **2.2.0**: 24 bit bmp support, fixed bug with uploading the same image twice, fixed loading screen.
- **2.2.1**: Changed text length limit warnings to account for =file command.
- **2.2.2**: zminor style and text changes.