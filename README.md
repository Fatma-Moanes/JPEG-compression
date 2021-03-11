# JPEG-compression
This code implements a JPEG encoder and decoder for girl.png image with 8-bit grey scaled pixels, with the following steps:

## Encoder:
1- Reads and divides the image into blocks of 8x8 pixels. 

2- Performs DCT on each block.

3- Performs quantization step per 8x8 block using 3 different quantization tables.

4- Transforms each block from 2-D into 1-D vector using zig-zag pattern.

5- Performs run-length encoding to compress the stream of zeros that may result due to quantization.

6- Performs Huffman to encode the final stream into a further compressed bit stream.


## Decoder:
7- Performs Huffman decoding to decode the Huffman encoded stream.

8- Performs run-length decoding.

9- Transforms the 1-D vector into groups of 8x8 matrices.

10- Multiplies each group by the quantization tables.

11- Performs IDCT on each 8x8 pixel group.

12- Combines the 8x8 pixel groups into a single image and saves it back to a file.

13- Compares the original image with the compressed image when using each quantization table in step (3).


### Implemented functions:
* DCT, IDCT
* Quantization, Inverse Quantization
* Zig-Zag scan, Inverse Zig-Zag scan
* run-length encoding/ decoding
* Huffman encoding
