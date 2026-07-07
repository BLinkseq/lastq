+++
title= "stLFR"
weight=5
+++

## Single-Tube Long Fragment Reads (stLFR)

Another of the presently available commercial linked-read options. stLFR data uses combinatorial barcodes
made up for three 10bp segments which are at the end of the `R2` read. Demultiplexing these data results
in the barcode being moved to the sequence ID using a pound (`#`) sign between the sequence ID and barcode, with
the barcode recoded in the `1_2_3` format, where each segment is an integer.

{{ img(path="img/lr_stlfr.png") }}

## Specification
- depending on the link sequence between segments, will be either the last 54bp or 42bp of the `R2` read
  - 54 base barcode: 10+6+10+18+10
  - 42 base barcode: 10+6+10+6+10
- barcode appended to sequence header with `#` sign
  - e.g. `@A003432423434:1:324#12_432_1`
- invalid barcode segment encoded as `0` (e.g., `1_0_29`)
- advertised to have a capacity over 3.6 **billion**, with up to 50 **million** per sample (actual results may vary)