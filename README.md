# webglsl-mandel

A GPU-accelerated fractal viewer.

Try out on http://divVerent.github.io/webglsl-mandel/

# Features

* Fast parameter editing.
* Scrolling by dragging.
* Zooming by mouse wheel (desktop) or pinching (mobile).
* Custom formulas in GLSL.

# Formula syntax

Formulas are directly evaluated in GLSL; for convenience a few functions are
provided. Do not use other constructs, as they may not work as you think!

* Variables:
  * `z`: the current iterator variable (Mandelbrot: initialized to the fixed
    parameter; Julia: initialized to the fragment position).
  * `c`: the current parameter (Mandelbrot: current fragment position; Julia:
    fixed parameter)
* Low level complex operations:
  * `vec2(r1, r2)`: building a complex number from reals
  * `z.x`: real component
  * `z.y`: imaginary component
  * `z*conj`: conjugation
  * `cabs(z)`: absolute value
  * `cabs2(z)`: squared absolute value
  * `carg(z)`: argument
* Elementary operations:
  * `z1 + z2`: addition
  * `z1 - z2`: subtraction
  * `z1 * r`: multiplication with real
  * `cmul(z1, z2)`: multiplication with complex
  * `z1 / r`: division by real
  * `cdiv(z1, z2)`: division by complex
* More complex-valued functions:
  * `cexp(z)`: exponentiation
  * `clog(z)`: logarithm
  * `cpow(z1, z2)`: power
  * `csin(z)`: sine
  * `ccos(z)`: cosine
  * `ctan(z)`: tangent
  * `ccot(z)`: cotangent
* Constants:
  * `u`: the unity (same as `vec2(1, 0)`)
  * `i`: the imaginary unit (also reachable as `j`, same as `vec2(0, 1)`)
  * `M_E`: Euler's number
  * `M_PI`: Archimedes' constant
