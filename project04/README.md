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

Get_assembly_stats
count the number of contigs
sum up the total length of all contigs
find the longest contig length
find the shortest contig length
calculate the mean length = total length / number of contigs

for N50:
    set threshold = total length / 2
    sort contigs from shortest to longest
    cumulative = 0
    for each contig in sorted order:
        add its length to cumulative
        if cumulative >= threshold:
            n50 = length of this contig

return all stats in a dictionary


Write_fasta
open the output file for writing

for each contig (numbered 1, 2, 3...):
    write a header line: ">Contig_1"
    write the sequence in chunks of 60 characters per line

close the file
```

# Successes
Our collaboration was one of the major successes with our project. We planned out our availability early on so we were able to allocate time to work on the pseudocode and its implementation together. Almost all of our work was done synchronously, which helped us bounce ideas and contribute towards the project. We also spent a significant amount of time on our pseudocode and planning, which made the coding part of our project much easier to tackle.

# Struggles
We did stumble across errors in our code while we were working through each method, but we were able to solve them as they came along. Thankfully, we didn't have any other major struggles holding back our productivity or getting us stuck in the code.

# Personal Reflections
## Group Leader
## Shameem
I found the project to be fairly straightforward to understand, and working with my team was a great experience. Our meetings went well ansomething I appreciated was being able to ask questions and help each other stay on the same page. After the last few projects, we all knew the pseudocode needed the most time and energy, and that's exactly where we started. After that stage, the rest went smoothly, and we were all in a meeting whenever code was worked on, which made this project feel the most collaborative for me since barely any work was done asynchronously. Overall, it went really well, and I am happy with the work we produced.

## Other member
##Marcos

##Sneha

# Generative AI Appendix
As per the syllabus
None was used
