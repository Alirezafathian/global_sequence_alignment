Global Sequence Alignment
==============================
Global pairwise alignment of two sequences using a dynamic programming algorithm of <a href="https://en.wikipedia.org/wiki/Needleman%E2%80%93Wunsch_algorithm">Needleman and Wunsch (1970)</a> for global alignment.

it can be described in three steps:
(1) Scoring matrix cunstruction; (2) TraceBack; and (3) Alignment;

For more information about sequence alignment and Needleman and Wunsch algorithm, look at
Edwards, Yvonne & Abnizova, Irina. (2004). Bioinformatics and Functional Genomics. Briefings in Functional Genomics and Proteomics. 3. 10.1093/bfgp/3.2.187. 


A simple example:

	> Example12 := [a, t, c, g];
	> Example11 := [t, c, g];

(1) Scoring Matrix

	> MA(Example11, Example12, 1, -2, -2)
	[[[[t, a], [0, 0]], [[t, t], [0, a]], [[t, c], [t, t]], [[t, g], [t, c]],
	[[c, a], [t, a]], [[c, a], [t,0]], [[c, t], [t, t]], [[c, c], [t, t]],
	[[c, g], [c, c]], [[g, a], [c, a]], [[g, a], [c, 0]], [[g, t], [c, t]],
	[[g, c], [c, c]], [[g, g], [c, c]]], 1]

(2) TraceBack

	> TraceBack(mma, LL1, LL2)
	[[g, g], [c, c]], [[c, c], [t, t]], [[t, t], [0, a]]

(3) Alignment

	> Align(Example11, Example12, 1, -2, -2)
	[[[t, c, g]], 
	[[t, c, g]]],	 1
