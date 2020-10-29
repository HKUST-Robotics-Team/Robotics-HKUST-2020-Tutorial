# Advanced Tutorial 0 -  Homework

Author : Tang Pok Lam

## Question: Sobel Filter

In this homework, you are required to build a Sobel filter using the skeleton code provided. We have also provided you with an example of a median filter to show you how to use the QDBMP library. You can find this example in the example.md file.

### Additional library

In this homework, we need to import a library to read and write bitmap files. Here is the original link of [QDBMP library](http://qdbmp.sourceforge.net/). However, we have created some additional functions to work better with 8-bit grayscale images. As a result, please make sure you **download the library from our Github repository** instead of the original link provided above.

### Skeleton code
```c
#include <stdio.h>
#include <stdint.h>
#include <math.h>
#include "qdbmp.h"

int main(void) {

    // START CODE HERE (you may test other 8-bit grayscale bmp)
    BMP* imageIn = BMP_ReadFile("lenna.bmp");
    // END CODE HERE

    BMP_CHECK_ERROR(stdout, -1);

    int height = BMP_GetHeight(imageIn);
    int width  = BMP_GetWidth(imageIn);

    BMP* imageOut = BMP_Create(width, height, 8);
    for (int i=0; i<256; i++) {
    	BMP_SetPaletteColor(imageOut, i, i, i, i);
    }

    // START CODE HERE



    // END CODE HERE

    BMP_WriteFile(imageOut, "output.bmp");

    BMP_Free(imageIn);
    BMP_Free(imageOut);
    return 0;
}
```
### Example Input & Output
Input:

<img width="360" alt="colored" src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/3f/Bikesgray.jpg/300px-Bikesgray.jpg">

Output:

<img width="360" alt="colored" src="https://upload.wikimedia.org/wikipedia/commons/thumb/2/24/Bikesgray_sobel.JPG/300px-Bikesgray_sobel.JPG">

Note that the edge your program has detected might be **slightly different** than the example output. It is totally acceptable. Just make sure that the edge detected is **clear** to see. You may also try your program with other 8-bit grayscale bitmap images (.bmp).

You are **not required** to handle the outer edge (boundary) of the image.

## Submissions:

Submission deadline: 4/11 12:00 n.n. HKT.

You are required to upload both your program (.c), input BMP file, and output BMP file to GitHub.
