## WHAT IS PHYLOGENETICS?

It is the study of evolutionary relationship among biological entities often species, individuals or genes(which may be referred to as taxa)

### WHAT DOES PHYLOGENETICS AIM TO ANSWER?
- What are the evolutionary relationships or histories among my species/indviduals/genes of interest?
- How do sequences evolve?
- Can I better describe the process of evolution with a mathematical model

### WHY USE MOLECULAR DATA
- Because DNA is a heriditary material
- We can do sequencing easily and quickly
- Sequences are highly specific and information rich


  ### WHY IS PHYLOGENETICS IMPORTANT

  - We get to learn how genes, genomes, species evolve over a period of time

  ### APPLICATIONS OF PHYLOGENETICS

  - Classification
  - Identifying the origin of pathogens
  - Conservation
  - Bioinformatics and computing
 
  ### What is a phylogeny?
  
A phylogeny, also known as a tree, is an explanation of how sequences evolved, their genealogical relationships, and therefore how they came to be the way they are today.

#### Definition of terms

## Topology
The topology is the branching structure of the tree. It is of particular biological significance because it indicates patterns of relatedness among taxa, meaning that trees with the same topology and root have the same biological interpretation. 
![image](https://github.com/Natasha-Adongo/Bioinformatics-Training/assets/109069282/d1a23a63-19c0-4fba-a06f-48eb5ffb869f)

The three trees in the top box of Figure 5 have topologies in common. This is evident from the statement “A and B are more closely related to one another than they are to C”, which is true for all three trees. In the lower box, all three trees have different topologies from one other. For example, in the left-most tree, A and B are more closely related to one another than they are to C. However, in the middle tree, it is C and A who are each other’s closest relatives, and in the right hand tree it is B and C which are most closely related.

## Branches
Branches show the path of transmission of genetic information from one generation to the next. Branch lengths indicate genetic change i.e. the longer the branch, the more genetic change (or divergence) has occurred.

![image](https://github.com/Natasha-Adongo/Bioinformatics-Training/assets/109069282/6b66e369-e1ca-4d52-bc15-28151f99e917)

Informative branch lengths are typically drawn to scale and indicate the number of substitutions per site (Figure 7). Branch lengths are occasionally shown on the phylogeny (left), but it is far more common to see branch lengths represented by a scale bar (right). It can therefore be useful to keep a ruler close to hand for interpreting phylogenies that you see in the literature!

 _How do we estimate genetic change?_
Estimating the extent of genetic change is not a trivial task. A naïve method is to align pairs of sequences, count up the number of differences and divide by the sequence length.
![image](https://github.com/Natasha-Adongo/Bioinformatics-Training/assets/109069282/56a064d3-7efd-4806-9df3-4790d2782c5d)

## Nodes
Nodes are the points at the ends of branches which represent sequences or hypothetical sequences at various points in evolutionary history. 
The tips

The sequences that we sampled and used to construct our phylogeny occur on single terminal branches, known as the tips or external nodes.

## Internal nodes

Internal nodes occur at the points where more than one branch meet and represent the (usually inferred) ancestral sequences. For example, in Figure 9, the internal node indicated by a blue arrow is the hypothetical common ancestor of sequences A and B.  

## The root

The root is a very important internal node representing the most recent common ancestor of all sequences in the phylogeny.
It is therefore the oldest part of the tree and tells us the direction of evolution, with the flow of genetic information moving from the root, towards the tips with each successive generation. 

![image](https://github.com/Natasha-Adongo/Bioinformatics-Training/assets/109069282/ea7568ce-5c6a-48ad-98c1-bf7c10213a25)

_Rooting a tree affects its meaning_
Deciding upon an appropriate root position is critical for phylogenetic interpretation because the root tells us the direction of evolution and so affects statements that we make about patterns of relatedness. For example, in the unrooted tree above (Figure 10, left) we cannot make statements such as “A is more closely related to B than it is to C” because this would not be true if the root occurred anywhere on the branches that connect A and B. 

_Where to root a tree?_
There are two main approaches that we can use to root a tree:

*Outgroup rooting*: A preferred approach is generally to include one or more sequences in our analysis that we know are definitely more distantly related to our sequences of interest than they are to one another. These sequence are usually referred to as ‘outgroups’.

*Midpoint rooting*: This method requires you to make the assumption that all of your sequences are evolving at the same rate – you should do so cautiously because this assumption does not hold for many biological datasets. In this case, the root is positioned at the midpoint between the two longest branches. If you have taxa that were not sampled at the same time point then a slight modification of this method would be required to take into account the time elapsed between samples. 





