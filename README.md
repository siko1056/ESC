# SDP Benchmark Problems from Electronic Structure Calculations

> This GitHub repository is a "modern" presentation of the original ESC
> library by Mituhiro Fukuda hosted at
> http://www.is.titech.ac.jp/~mituhiro/software.html.
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

<TABLE BORDER="2" BGCOLOR="white">
<TR><TH>r</TH><TH># equality constraints</TH><TH>Size of block matrices</TH><TH>Size of the diagonal matrix</TH></TR>
<TR><TH>12</TH><TD ALIGN="center">948</TD><TD>6, 6, 6, 6, 15, 15, 36, 15, 15, 36, 72, 36, 36, 20, 90, 90, 20, 306, 306, 90, 90</TD><TD ALIGN="center">94</TD></TR>
<TR><TH>14</TH><TD ALIGN="center">1743</TD><TD>7, 7, 7, 7, 21, 21, 49, 21, 21, 49, 98, 49, 49, 35, 147, 147, 35, 490, 490, 147, 147</TD><TD ALIGN="center">122</TD></TR>
<TR><TH>16</TH><TD ALIGN="center">2964</TD><TD>8, 8, 8, 8, 28, 28, 64, 28, 28, 64, 128, 64, 64, 56, 224, 224, 56, 736, 736, 224, 224</TD><TD ALIGN="center">154</TD></TR>
<TR><TH>20</TH><TD ALIGN="center">7230</TD><TD>10, 10, 10, 10, 45, 45, 100, 45, 45, 100, 200, 100, 100, 120, 450, 450, 120, 1450, 1450, 450, 450</TD><TD ALIGN="center">230</TD></TR>
</TABLE>


## Repulsion Energies (in Hartree units)
<a id="repulsion"></a>

<TABLE BORDER="2" BGCOLOR="white">
<TR><TH>System</TH><TH>N</TH><TH>r</TH><TH>Repulsion Energy</TH></TR>
<TR><TH>LiH</TH><TD ALIGN="right">4</TD><TD>12</TD><TD ALIGN="right">0.9948810848</TD></TR>
<TR><TH>BeH</TH><TD ALIGN="right">5</TD><TD>12</TD><TD ALIGN="right">1.5772794307</TD></TR>
<TR><TH>BH+</TH><TD ALIGN="right">5</TD><TD>12</TD><TD ALIGN="right">2.1782219849</TD></TR>
<TR><TH>BH</TH><TD ALIGN="right">6</TD><TD>12</TD><TD ALIGN="right">2.1469378814</TD></TR>
<TR><TH>CH+</TH><TD ALIGN="right">6</TD><TD>12</TD><TD ALIGN="right">2.8075545972</TD></TR>
<TR><TH>CH</TH><TD ALIGN="right">7</TD><TD>12</TD><TD ALIGN="right">2.8351312564</TD></TR>
<TR><TH>CH-</TH><TD ALIGN="right">8</TD><TD>12</TD><TD ALIGN="right">2.9398736056</TD></TR>
<TR><TH>NH+</TH><TD ALIGN="right">7</TD><TD>12</TD><TD ALIGN="right">3.4619072364</TD></TR>
<TR><TH>NH</TH><TD ALIGN="right">8</TD><TD>12</TD><TD ALIGN="right">3.5748318307</TD></TR>
<TR><TH>NH-</TH><TD ALIGN="right">9</TD><TD>12</TD><TD ALIGN="right">3.5379567746</TD></TR>
<TR><TH>OH+</TH><TD ALIGN="right">8</TD><TD>12</TD><TD ALIGN="right">4.1145086908</TD></TR>
<TR><TH>OH</TH><TD ALIGN="right">9</TD><TD>12</TD><TD ALIGN="right">4.3656986614</TD></TR>
<TR><TH>OH-</TH><TD ALIGN="right">10</TD><TD>12</TD><TD ALIGN="right">4.3643484454</TD></TR>
<TR><TH>HF+</TH><TD ALIGN="right">9</TD><TD>12</TD><TD ALIGN="right">4.7578374036</TD></TR>
<TR><TH>HF</TH><TD ALIGN="right">10</TD><TD>12</TD><TD ALIGN="right">5.1948028370</TD></TR>
<TR><TH>BH2</TH><TD ALIGN="right">7</TD><TD>14</TD><TD ALIGN="right">4.7269615539</TD></TR>
<TR><TH>CH2(1A1)</TH><TD ALIGN="right">8</TD><TD>14</TD><TD ALIGN="right">6.0430274001</TD></TR>
<TR><TH>CH2(3B1)</TH><TD ALIGN="right">8</TD><TD>14</TD><TD ALIGN="right">6.1757874267</TD></TR>
<TR><TH>NH2</TH><TD ALIGN="right">9</TD><TD>14</TD><TD ALIGN="right">7.5640948299</TD></TR>
<TR><TH>H2O+</TH><TD ALIGN="right">9</TD><TD>14</TD><TD ALIGN="right">8.7976559250</TD></TR>
<TR><TH>H2O</TH><TD>10</TD><TD>14</TD><TD ALIGN="right">9.1949655162</TD></TR>
<TR><TH>NH3</TH><TD>10</TD><TD>16</TD><TD ALIGN="right">11.9103794143</TD></TR>
<TR><TH>H3O+</TH><TD>10</TD><TD>16</TD><TD ALIGN="right">14.0016864732</TD></TR>
<TR><TH>Li2</TH><TD ALIGN="right">6</TD><TD>20</TD><TD ALIGN="right">1.7818082386</TD></TR>
<TR><TH>B2</TH><TD>10</TD><TD>20</TD><TD ALIGN="right">8.3203969969</TD></TR>
<TR><TH>C2+</TH><TD>11</TD><TD>20</TD><TD ALIGN="right"> 13.5783185773</TD></TR>
<TR><TH>C2</TH><TD>12</TD><TD>20</TD><TD ALIGN="right">15.3322985626</TD></TR>
<TR><TH>C2-</TH><TD>13</TD><TD>20</TD><TD ALIGN="right">15.0239597508</TD></TR>
<TR><TH>LiF</TH><TD>12</TD><TD>20</TD><TD ALIGN="right">9.1359970094</TD></TR>
<TR><TH>BeO</TH><TD>12</TD><TD>20</TD><TD ALIGN="right">12.7234743166</TD></TR>
<TR><TH>NaH</TH><TD>12</TD><TD>20</TD><TD ALIGN="right">3.0841102782</TD></TR>
<TR><TH>BeF</TH><TD>13</TD><TD>20</TD><TD ALIGN="right">13.9973408993</TD></TR>
<TR><TH>BO</TH><TD>13</TD><TD>20</TD><TD ALIGN="right">17.5733416023</TD></TR>
<TR><TH>N2+</TH><TD>13</TD><TD>20</TD><TD ALIGN="right">23.2261601585</TD></TR>
<TR><TH>N2</TH><TD>14</TD><TD>20</TD><TD ALIGN="right">23.6218321955</TD></TR>
<TR><TH>CO+</TH><TD>13</TD><TD>20</TD><TD ALIGN="right">22.7786816895</TD></TR>
<TR><TH>CO</TH><TD>14</TD><TD>20</TD><TD ALIGN="right">22.5121935230</TD></TR>
<TR><TH>BF</TH><TD>14</TD><TD>20</TD><TD ALIGN="right">18.8617633307</TD></TR>
<TR><TH>AlH</TH><TD>14</TD><TD>20</TD><TD ALIGN="right">4.1743350953</TD></TR>
<TR><TH>CF</TH><TD>15</TD><TD>20</TD><TD ALIGN="right">22.4686046910</TD></TR>
<TR><TH>O2+</TH><TD>15</TD><TD>20</TD><TD ALIGN="right">30.3362091867</TD></TR>
<TR><TH>O2</TH><TD>16</TD><TD>20</TD><TD ALIGN="right">28.0474898021</TD></TR>
<TR><TH>SiH</TH><TD>15</TD><TD>20</TD><TD ALIGN="right">4.8749631414</TD></TR>
<TR><TH>SiH-</TH><TD>16</TD><TD>20</TD><TD ALIGN="right">5.0261068426</TD></TR>
<TR><TH>NO-</TH><TD>16</TD><TD>20</TD><TD ALIGN="right">23.3154413407</TD></TR>
<TR><TH>NF</TH><TD>16</TD><TD>20</TD><TD ALIGN="right">25.3156402817</TD></TR>
<TR><TH>HS+</TH><TD>16</TD><TD>20</TD><TD ALIGN="right">6.1603870664</TD></TR>
</TABLE>

> For inquires about information posted here, mail to `mituhiro`
> followed by `@is.titech.ac.jp`.
