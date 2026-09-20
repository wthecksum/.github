<p align="center">
  <img src="../assets/logo/wthecksum-folded-bands.png" alt="WTHecksum logo" width="220">
</p>

<h1 align="center">WTHecksum</h1>

<p align="center">
  <a href="#studies"><strong>Studies</strong></a>
  &nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="#method"><strong>Method</strong></a>
  &nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="#target"><strong>Target</strong></a>
</p>

I wanted to build WTHecksum to organize my studies on checksum algorithms, their uses, and how their implementations behave on real machines. Maybe those studies will turn into useful APIs and fast implementations. Maybe they won’t. We’ll see.

### Studies

The first work covers CRC-32 and Adler-32.

- **CRC-32:** the first CRC study, using the ISO-HDLC parameter set. The suffix identifies the exact variant, because `CRC-32` alone does not identify every 32-bit CRC algorithm.
- **Adler-32:** algorithm behavior, reference results, and matched benchmarks.

### Method

I define the exact variant and byte contract first. I compare existing libraries, tools, and Zig's standard library before writing a native Zig version.

Each study records known vectors, benchmark inputs, build details, and the limits behind its results. Scalar correctness comes before SIMD and other CPU-specific paths.

<p id="target"><strong>First target:</strong> Linux x86-64 with AVX2. The implementation work is single-threaded and keeps an independently checked fallback. Results for this target do not describe other CPUs or operating systems.</p>
