# Hyperbolic-Tan-implementation-on-Verilog

Hyperbolic functions are analogous to trigonometric circular functions. The basic hyperbolic functions are sinh, cosh and tanh function is defined as tanh⁡(𝑥)= sinh⁡(𝑥) /cosh⁡(𝑥). Tanh is function widely used in many applications like digital neural network, image processing, filters, decoding algorithms etc. This paper aims to implement hyperbolic tan on Field programmable gate array(FPGA).In the first part a brief description of the theory behind the algorithm is presented. Then the extended theory called unified CORDIC algorithms is explained. In the second part implementation of algorithm on FPGA is shown.

This algorithm is derived from general rotation transform
                                              𝑥′=𝑥∗cos ∅ −𝑦∗sin ∅ 
                                              𝑦′=𝑦∗cos ∅ +𝑥∗sin ∅  
which rotates a vector in Cartesian form. The above two equations can be modified as                  
                                               𝑥′=cos ∅ 𝑥−𝑦∗tan ∅ 
                                              𝑦′=cos ∅ 𝑦+𝑥∗tan ∅ 
 If the rotation is restricted to tan(φ) = +/- 2(-i) ,the multiplication in the above equation will be replaced by simple shift operation. 
                                               𝑋𝑖+1=𝐾𝑖 𝑋𝑖−𝑌𝑖∗𝑑𝑖∗2 −𝑖 
                                               𝑌𝑖+1=𝐾𝑖 𝑌𝑖+𝑋𝑖∗𝑑𝑖∗2 −𝑖 
 Where i is the iteration count and 𝐾𝑖=cos tan−1 2−𝑖  and di = +/- 1. 


The advantage of the design proposed is that no DSP or multiplication blocks are used. 
As 10 bit precision is used, the accuracy of the design is high.
The only disadvantage is that the number of iterations required are slightly more. 
This block can be used in few decoding algorithms in communication systems. 
The design will be used in LDPC decoder sum product algorithm. 



