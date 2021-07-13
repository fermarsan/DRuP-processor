# DRuP (Didactic Reduced microProcessor)

This a _Verilog_ description of a 4-bit didactic procesor developed at Universidad Distrital Francisco José de Caldas (Bogotá, Colombia) in the ARMOS research group. The main goal of the project is teaching the basic concepts of microprocessors by means of a simplified hardware description able to be implemented on small programable logic devices. The development of this work has been published in the following papers.

[Minimalist 4-bit processor focused on processors theory teaching](https://indjst.org/articles/minimalist-4-bit-processor-focused-on-processors-theory-teaching)

[Hardware description of a simplified 4-bit softcore processor with BCD capabilities](http://ijece.iaescore.com/index.php/IJECE/article/view/19346)

## Architecture

_DRuP_ is an 4-bit Harvard accumulator-based processor with a data memory of 16 positions (registes) and a 8-bit program memory of 256 positions.

## Finite state machine

````dot {cmd=true}
digraph G {
  reset -> fetch
  fetch -> decode
  decode -> "load acc"
  "load acc" -> fetch
  decode -> out
  out -> fetch
  decode -> store
  store -> fetch
  decode -> jump
  jump -> fetch
  decode -> "skip if"
  "skip if" -> fetch
}
