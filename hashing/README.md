### Algorithms

Based on the famous [RELIC cryptographic library](https://github.com/relic-toolkit/relic) we implement:
 hashing to $\mathbb{G}_2$ on the BW13-P310 curve with two methods presented in https://eprint.iacr.org/2022/996. The first method (Method I) is seen as a generlized  Fuentes et al method. 
 The second one (Method II) is a further optimiation based on the first one.
The preset file can be found in  <preset> folder in the name of gmp-ecc-bw310.sh.<br/>

### Requirements

The build process requires the [CMake](https://cmake.org/) cross-platform build system. The [GMP](https://gmplib.org/) library is also needed in our benchmarks.

### Build instructions

Instructions for building the library can be found in the [Wiki](https://github.com/relic-toolkit/relic/wiki/Building).


### Source code
  
The main source code of our algorithms are distributed in different folders.  The main functions are:

* ep13_map(ep13_t p, const uint8_t *msg, int len) :Maps a byte array to a point of BW13-P310.
* ep13_cof_fuentes(ep13_t r, ep13_t p) : Given a random point p , hashing p to $\mathbb{G}_2$ using Method I.
* ep13_cof(ep13_t r, ep13_t p):Given a random point p , hashing p to $\mathbb{G}_2$ using Method II.

 hashing to $\mathbb{G}_2$  can be accomplished by perfroming ep13_map()+ep13_cof_fuentes() or  ep13_map()+ep13_cof.

 ### Benckmarks
 The functions for benckmarking are presented in [bench_pc.c](https://github.com/eccdaiy39/smt/blob/master/smt-relic/bench/bench_pc.c) for the BN-P446 curve and 
 [bench_pc_bw13.c](https://github.com/eccdaiy39/smt/blob/master/smt-relic/bench/bench_pc_bw13.c) for the BW13-P310 curve.
 Timing results can be obtained by performing the following commands：
  

  1. mkdir build && cd build 
  2. ../preset/gmp-ecc-bw310.sh ../
  3. make
  4. cd bin && ./bench_hash
  
 ### Contact
 email:daiy39@mail2.sysu.edu.cn<br/>
 
 Please contact me via email for any questions.



