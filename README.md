# SDP Benchmark Problems from Electronic Structure Calculations

> This GitHub repository is a "modern" presentation of the original ESC
> library by Mituhiro Fukuda hosted at
> http://mf.c.titech.ac.jp/mituhiro/software.html.
>
> The original page was last modified on Tuesday, May 2, 2017.

> Please refer to the new problem sets available from
> http://nakatamaho.riken.jp/rdmsdp/sdp_rdm.html,
> since the data below is obsolete.

The following set of SDPs are the actual ones solved in [[1]](#paper).  The
problem consists of determining the ground state energy of an N-electron system
in a given external potential through the so-called Reduced Density Matrix
Method.  A detailed description on the formulation be found in:

> <a id="paper"></a>
> Z. Zhao, B. J. Braams, M. Fukuda, M. L. Overton, and J. K. Percus,
> "The reduced density matrix method for electronic structure calculations and
> the role of three-index representability conditions,"
> *The Journal of Chemical Physics*, **120** (2004), pp. 2095-2104.
> [DOI: 10.1063/1.1636721](https://doi.org/10.1063/1.1636721)

[The sizes of SDPs](#sizes) depend on the size of the "spin-orbital basis",
`r`, which governs the discretization of the continuous wave function, but do
not depend on the number of electrons `N` of the system.  (Accurate electronic
structure calculations will have `r >= 2N`).

[The Benchmark SDPs](#problems) are in
[SDPA format](http://plato.asu.edu/ftp/sdpa_format.txt) and are divided
according to the basis size `r`.  See [sizes of corresponding SDPs](#sizes).

In our paper [[1]](#paper), we present several SDP calculations for each
molecule, but here we only provide the data for the most accurate SDP
calculations: those with the `P`, `Q`, `G`, `T1` and `T2` N-representability
conditions.  Our results are given in Tables 1 and 2 in [[1]](#paper).

To obtain the energies displayed in Tables 1 and 2 under column `E_{PQGT1T2}`
[[1]](#paper), it is necessary to add the
[nuclear repulsion energies](#repulsion) to the optimal values of each
corresponding SDP.  The important information we want to extract from solving
the SDPs are the optimal value, and the dual vector variable (which provides
the One-Reduced Density Matrix and the Two-Reduced Density Matrix).  The
applications typically require 4 digits of accuracy after the period for the
optimal values (which means 6 or 7 digits of accuracy in total).


## Electronic Structure Calculation Problems (47 problems)
<a NAME="problems"></a>

- [15 SDPs with `r = 12`](http://www.is.titech.ac.jp/~mituhiro/Fermion/r12.tar)
  (4.6 MB)

- [6 SDPs with `r = 14`](http://www.is.titech.ac.jp/~mituhiro/Fermion/r14.tar)
  (4.0 MB)

- [2 SDPs with `r = 16`](http://www.is.titech.ac.jp/~mituhiro/Fermion/r16.tar)
  (2.6MB)

- [24 SDPs with `r = 20`](http://www.is.titech.ac.jp/~mituhiro/Fermion/r20.tar)
  (94.2MB)

> Note: The above set of problems were replaced on December 26, 2003
> because the function `fromsdpa` from
> [SeDuMi 1.05 (currently, version 1.3)](http://sedumi.ie.lehigh.edu/)
> assumes that the data matrices in
> [SDPA format](http://plato.asu.edu/ftp/sdpa_format.txt) are ordered.
> We thank [Hans D. Mittelmann](http://plato.la.asu.edu/) for providing
> the new set of problems readable from all the SDP codes.

## Sizes of SDPs
<a id="sizes"></a>

| `r` | # equality constraints | Size of block matrices | Size of the diagonal matrix |
| --- | :--------------------: | ------------------------------------------------------------------------------------------------- | :-: |
|  12 |                    948 |  6,  6,  6,  6, 15, 15,  36, 15, 15,  36,  72,  36,  36,  20,  90,  90,  20,  306,  306,  90,  90 |  94 |
|  14 |                   1743 |  7,  7,  7,  7, 21, 21,  49, 21, 21,  49,  98,  49,  49,  35, 147, 147,  35,  490,  490, 147, 147 | 122 |
|  16 |                   2964 |  8,  8,  8,  8, 28, 28,  64, 28, 28,  64, 128,  64,  64,  56, 224, 224,  56,  736,  736, 224, 224 | 154 |
|  20 |                   7230 | 10, 10, 10, 10, 45, 45, 100, 45, 45, 100, 200, 100, 100, 120, 450, 450, 120, 1450, 1450, 450, 450 | 230 |


## Repulsion Energies (in Hartree units)
<a id="repulsion"></a>

|  System  | `N` | `r` | Repulsion Energy |
| -------- | --- | --- | ---------------: |
| LiH      |   4 |  12 |     0.9948810848 |
| BeH      |   5 |  12 |     1.5772794307 |
| BH+      |   5 |  12 |     2.1782219849 |
| BH       |   6 |  12 |     2.1469378814 |
| CH+      |   6 |  12 |     2.8075545972 |
| CH       |   7 |  12 |     2.8351312564 |
| CH-      |   8 |  12 |     2.9398736056 |
| NH+      |   7 |  12 |     3.4619072364 |
| NH       |   8 |  12 |     3.5748318307 |
| NH-      |   9 |  12 |     3.5379567746 |
| OH+      |   8 |  12 |     4.1145086908 |
| OH       |   9 |  12 |     4.3656986614 |
| OH-      |  10 |  12 |     4.3643484454 |
| HF+      |   9 |  12 |     4.7578374036 |
| HF       |  10 |  12 |     5.1948028370 |
| BH2      |   7 |  14 |     4.7269615539 |
| CH2(1A1) |   8 |  14 |     6.0430274001 |
| CH2(3B1) |   8 |  14 |     6.1757874267 |
| NH2      |   9 |  14 |     7.5640948299 |
| H2O+     |   9 |  14 |     8.7976559250 |
| H2O      |  10 |  14 |     9.1949655162 |
| NH3      |  10 |  16 |    11.9103794143 |
| H3O+     |  10 |  16 |    14.0016864732 |
| Li2      |   6 |  20 |     1.7818082386 |
| B2       |  10 |  20 |     8.3203969969 |
| C2+      |  11 |  20 |    13.5783185773 |
| C2       |  12 |  20 |    15.3322985626 |
| C2-      |  13 |  20 |    15.0239597508 |
| LiF      |  12 |  20 |     9.1359970094 |
| BeO      |  12 |  20 |    12.7234743166 |
| NaH      |  12 |  20 |     3.0841102782 |
| BeF      |  13 |  20 |    13.9973408993 |
| BO       |  13 |  20 |    17.5733416023 |
| N2+      |  13 |  20 |    23.2261601585 |
| N2       |  14 |  20 |    23.6218321955 |
| CO+      |  13 |  20 |    22.7786816895 |
| CO       |  14 |  20 |    22.5121935230 |
| BF       |  14 |  20 |    18.8617633307 |
| AlH      |  14 |  20 |     4.1743350953 |
| CF       |  15 |  20 |    22.4686046910 |
| O2+      |  15 |  20 |    30.3362091867 |
| O2       |  16 |  20 |    28.0474898021 |
| SiH      |  15 |  20 |     4.8749631414 |
| SiH-     |  16 |  20 |     5.0261068426 |
| NO-      |  16 |  20 |    23.3154413407 |
| NF       |  16 |  20 |    25.3156402817 |
| HS+      |  16 |  20 |     6.1603870664 |


> For inquires about information posted here, mail to `mituhiro`
> followed by `@is.titech.ac.jp`.
