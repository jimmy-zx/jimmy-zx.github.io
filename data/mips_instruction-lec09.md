## MIPS Instructions

### Arithmetic instructions

- I-type: `IMM` is sign extended.
- `div?`: `lo = $rs / $rt`, `hi = $rs % $rt`.
- `mult?`: `hi:lo = $s * $t`.
- `(add|sub)?u`: same as `(add|sub)?`, but does not trap on overflow.
- `(mult|div)u` behaves differently from `(mult|div)`.

### Logical instructions

- I-type: `IMM` is zero extended.

### Shift instructions

- `sll*` operations will always sign extend into a 64-bit register, then
truncates the value into 32 bits.

### Jump instructions

- `j`: according to slides, `pc = (pc & 0xF0000000) | (IMM << 2)`, which is
different from the specification.

- The range of `j` is 256 MBytes.

### Branch instructions

- The offset is `i = (label - (next PC)) >> 2`. This is different from the slides.

- The range `b*` is +/- 128 KBytes.

### Comparison instructions
