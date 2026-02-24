# Introduction
In this project, our group implements a de Bruijn graph algorithm for genome assembly. De Bruijn graphs represent sequence overlaps by breaking reads into k-mers, using (k−1)-mers as nodes and overlaps as edges. By constructing the graph and finding an Eulerian path, we can reconstruct the original sequence from fragmented reads. This method is especially effective for handling large, repetitive genomes and high-throughput sequencing data.

# Pseudocode
Put pseudocode in this box:
For our pseudocode, we broke the individual methods down and worked on them one by one.
```
Add_edge
Append the right kmer to the left kmer
{left: [right]}

Remove_edge
Check the left exists and then remove the right 

build_graph_from_reads(ATGCG, k=4)
→ {ATG: [TGC], TGC: [GCG]}
Raise exception if k < 2
Calcualte k-1mer
Loop through each read
	Walk through read by k-1mers
		For each k-1mer → add_edge(left, right)
	
eulerian_walk(node, graph)
Scan through list of dict to find node
Once we find node, record key associated with list
Remove edge with (key, node)
Call the function again using recorded key as the node
Final output would be a list
Reverse list at the end

Assemble_contigs
Build the graph from reads
While dictionary is not empty:
	Scan dictionary for k-1-mer that is in a list but not a key (guarantees it’s at end of a seq)
Do eulerian walk with that k-1-mer
Tour_to_sequence → append to contigs list
Repeat until dictionary is empty

Tour_to_sequence
Take first value of list and append to each remaining kmer
```

# Successes
Description of the team's learning points

# Struggles
Description of the stumbling blocks the team experienced

# Personal Reflections
## Group Leader
Group leader's reflection on the project

## Other member
Other members' reflections on the project

# Generative AI Appendix
As per the syllabus
None was used
