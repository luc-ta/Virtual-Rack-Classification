# Virtual-Rack-Classification
GAP programs for tabulating virtual racks and virtual quandles of a given order. Data up to order 8.

Compiled by Lực Ta

Based on the rack library of Petr Vojtěchovský and Seung Yeop Yang (https://www.cs.du.edu/~petr/libraries_of_algebraic_structures.html)

See OEIS sequences [A385040](https://oeis.org/A385040) and [A385041](https://oeis.org/A385041) for enumerations.

# Usage
`virtual-rack-finder.txt` exhaustively searches for virtual structures on all racks of a given order _n_ in Vojtěchovský and Yang's library, searches for isomorphisms between them, and outputs a list of all virtual racks of order _n_ up to isomorphism.

For example, to run the search for all _n_ between 1 and 3, load Vojtěchovský and Yang's library and then run the following. The following assumes that you've saved `virtual-rack-finder.txt` in the same folder as the rack library; if not, then replace "LRQ.path" below and in `virtual-rack-finder.txt` with the path to wherever you've saved `virtual-rack-finder.txt`.
```
racks:=[1, 2, 6, 19, 74, 353, 2080, 16023, 159526, 2093244, 36265070];
for n in [1..3] do
	ReadAsFunction(Concatenation(LRQ.path, "virtual-rack-finder-2.txt"))()(n,racks[n]);
od;
```
Here, `racks` is a list whose _n_th entry is the number of isomorphism classes of racks of order _n_. The entries of `racks` are taken from OEIS sequence [A181770](https://oeis.org/A181770).
