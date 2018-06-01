### 5. Homework

1. C)
  * we first find the eigenvalues, get the largest ones and project X onto them
  * we end up with a basis where the data grows the most in the direction of the 
    first basis vector, then 2. and so on
  * we then find the eigenvalues of the result
  * it is natural, that the largest eigenvector would be the first basisvector
  * therefore, Y_{*, 1} = z

2. D)
  * Dense -> 128*128*256 + 256*128*128 = 8 388 608 parameters (no biases)
  * Convolutions
    * 64*8*8 * 2 = 8 192
3. A)
  * 1) the covariance matrix is symmetric, therefore has real eigenvalues
  * 2) C is symmetric, therefore correct
  * 3) When x is eigenvalue, then A.v = x.v for v eigenvector corresponding to x.
	But then as well A.v.-1 = x.v.-1 = -x.v, so -x is eigenvalue too.
       In the algorithm in the lecture though, we look for the normalized eigenvalues
	with values >= 0

4. A)
  * input 130x130x3
  * after 11x11, 32 filters, stride(1,1), no padding (valid padding)
    * -> Out = (W - F + 2P) / S + 1 = (130 - 11) + 1 = 120
    * same in other direction, 32 filters, so -> 120x120x32
  * max pooling, stride 2, 2x2 reception field
    * -> Out = In / 2 = 60x60x32
  * convolution, 64 filters, stride = 1, receptive field = 7x7, padding = same 
	(enough zero padding to keep image dimensions, in our case for 
	receptive field 7 this should be 3 (calculate by (F - 1) / 2))
    * -> 60x60x64, same as input, 64 filters (because of same padding)
  * max pooling (same as above)
    * -> Out ->  30x30x64
  * conv with 256 filters, same padding (analogue to above)
    * -> Out = 30x30x256
5. A)
  * https://stats.stackexchange.com/questions/123413/using-a-gaussian-kernel-in-svm-how-exactly-is-this-then-written-as-a-dot-produc
  * https://stats.stackexchange.com/questions/163983/understanding-gaussian-process-regression-via-infinite-dimensional-basis-functio
  * yes, this can be done, but only for kernels with (Mercer's condition)
  * didn't go into the matter really deep, but gaussian kernels tend to fulfill this condition

6. A)
  * width = (W - F + 2P) / S + 1 = (w - n) / s + 1
  * height = (h - n) / s + 1

7. B)
  * we look at the bigger dimension (height) (as it scales slower in this direction)
  * in a convolution, a map's pixel value depends on all the pixels in the receptive field
  * so after 1. layer, value of 3. pixel also depends on 1. one
  * after 2. player, value of 5. pixel also depends on 1. one
  * 3. layer, 7. pixel
  * 4. layer, 9. pixel
  * 5. layer, 10. pixel, ready
8. B)
  * (20 - 4) // 2 + 1 = 9
  * (9 - 4) // 2 + 1 = 3
  * at layer 3, the dimension is already smaller than receptive field
