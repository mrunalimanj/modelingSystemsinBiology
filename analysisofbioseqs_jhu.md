from http://www.biostat.jhsph.edu/bstcourse/bio638/homeworkmain.html:
Homework 1, due November 12
Show all work to get credit.


1. If you are looking at two 100bp sequences with p(A) = 0.3, p(T) = 0.3, p(C) = 0.2, p(G) = 0.2, what is the probability that the nucleotides at position #25 in the sequences are the same? (5 points). What is the same probability if the composition is p(A) = 0.05, p(T) = 0.05, p(C) = 0.45, and p(G) = 0.45? (5 points)
Given the sequence, AACTT (a 5mer), what is the probability of finding this sequence at a given position in a 3 billion bp genome (use p(A/T)=0.3, p(C/G)=0.2)? (2 points) What is the probability of NOT finding this sequence at all, in the entire genome? (5 points) 

2. Do a global alignment of the two sequences ACAGGT and AACAGT, using these scoring rules: match = 2, mismatch = -1, gap = -2. Show the matrix with pointers as well as the traceback, with the final alignment(s) and score(s). (25 points)

3. Create a BLOSUM matrix from these five sequences, assuming that they are found as a motif in aligned proteins: TASLC, TTTLC, SATTC, LLTTC, SSTTC. You can't create a matrix, actually. Why not? (10 points) What approach could you take, if you wanted to create a BLOSUM scoring matrix for these sequences? (5 points) Leave the last amino acid off of each sequence, and create a matrix from those sequences. (20 points)

4. Construct the optimal tree from these four sequences using parsimony: TCGA, AAAT, TCGC, ACAT. (10 points)

5. Using these four sequences: TTTAACT, TTAATTT, AAAACTT, CCTACAC, define the distance between two sequences as the total number of mutations (mismatches) in their gapless alignment. Calculate a distance matrix. (3 points) Correct the distance matrix for nonuniform evolutionary rates (you don't have to create the tree). (10 points) 

6. Having proposed a tree and calculated its likelihood, you would like to use the Metropolis algorithm to improve your model. Why don't you just keep whichever tree is better (the original vs the one created by sampling)? That is, why is the new tree sometimes accepted even when it has lower probability? (5 points)


1. Explain why multiple alignments are directional; that is, why do you get different alignments (and trees) when the sequences are simply reversed? (5 points) Design an approach to multiple alignment that circumvents this problem. The approach can be heuristic or algorithmic but must be well explained ("align in both directions and compare" is completely inadequate). 10 points for a sensible approach, 15 points for explaining how it might help achieve a better alignment, in either a biological or statistical sense. It will be easiest to do this if you find or describe sequences to use as a test or training set. 

2. Invent a HMM to describe any process that interests you. Include at least 3 hidden states and at least 3 observations. Write out the transition and emission matrices, using reasonable probabilities that you may also invent. (20 points) Write or draw out both a very likely and a very unlikely sequence of observations from your model (make the sequences just long enough to illustrate your point). Don't go through the calculations but briefly explain why these observations are likely/unlikely. Here you'll need to explain both the probability of the observed states and the probability of the hidden states. (10 points)

3. In starting a Baum-Welch EM program, you want be somewhat unbiased, unless you have special knowledge about the underlying states. Why can't you just set all the emission and transition probabilities to the same number? (10 points) What's one way to come up with these probabilities? (5 points) 

4. The Viterbi algorithm is used to find the best state sequence underlying an observed sequence. It finds the sequence Q of states for which P(Q|X) is highest, where X is the sequence of observations. Why don't you want to find the sequence Q that maximizes P(X|Q) instead, since that Q would be the sequence of hidden states that has the highest probability of producing X? Hint: explain how the hidden state sequence that maximizes the probability of the observed sequence might not even be possible; that is, the probability of that hidden sequence happening at all is zero. (Come up with an example.) (10 points) Write out Bayes' Theorem for P(X|Q) and P(Q|X) to see the simple arithmetic underlying this problem.

5. The MACS algorithm relies on the offset observed between the peaks of negative strand and positive strand alignments, to find ChIP peaks. Explain the source of the offset and how it can be used to find the position of the bound protein (5 points).

6. What is the entropy of the sequence AAACTCGACC, if it's a nucleotide sequence? (5 points) if it's a protein sequence? (5 points) Why is entropy calculated in windows when used as a proxy for sequence complexity? (10 points)




1. Why do variant callers behave so differently from each other? (10 points) In fact, the question of whether a person has a variant with respect to the reference genome might not be meaningful in a generalized context. However, there are many situations in which you might use sequencing to ask a much more focused question about genetic variation, and the algorithm(s) chosen for use in analysis can be tailored to the question. Describe a focused question that you could ask about genetic variation in the biological system of your choice, and outline an algorithm that is tuned for finding that variation. (30 points) For example, I am interested in repetitive element polymorphisms, so I need to find reads that align partly to the genome and partly to a repetitive element sequence, requiring split alignments and lots of parsing, or possibly a good HMM to recognize the boundary. (I also need to give quite a bit more detail if I want credit for that)

2. Why can't you use a traditional short read aligner in its usual mode for RNAseq alignment? (5 points) What are two approaches that RNAseq alignment tools take, to handle this problem? (5 points) 

3. Alignment-free sequence comparison is a valuable tool even if we can do lightning-fast and accurate alignments. What features can alignment-free comparisons capture, that more traditional alignments cannot? or, to put it another way, give two reasons why two sequences that are functionally and evolutionarily related might not align well? (10 points) 

4. Exome library preparation involves a capture step, in which DNA that is complementary to annotated exons is enriched. After sequencing, the reads could be aligned to the whole genome sequence, or they could be aligned only to the annotated exons. Pick either of these strategies and defend why you would want to use it to find variation in a genome. (10 points)

5. Why is the 16S rRNA gene used so often in metagenomics studies? (5 points) In a metagenomics analysis, having a reliable reference database can be critical. Why? (5 points) What could you do to validate a particularly controversial finding (e.g. anthrax in the NY subway)? (5 points)



Your main job is to propose a followup experiment. The experiment itself can be partly laboratory or completely computational but it must have a substantial computational component and must use at least two methods we've learned in class. 

In your writeup, outline the background, hypothesis, methods, and results of the paper you're looking at, paying particular attention to any computational methods they used and whether they were appropriate for the task. If they developed new methods, what problem were they addressing, and were they successful?

Then, formulate your own hypothesis, describe how you would test it (methods), outline your anticipated results and potential pitfalls, and propose an alternative approach in case something doesn't work.

This shouldn't require more than 3-5 pages.

Suggested publications:
Immunology
Robust estimates of overall immune-repertoire diversity from high-throughput measurements on samples. Kaplinsky et al 2016. Link
Single-cell TCRseq: paired recovery of entire T-cell alpha and beta chain transcripts in T-cell receptors from single-cell RNAseq. Redmond et al 2016. Link

Chromosomal rearrangements
Recovering rearranged cancer chromosomes from karyotype graphs. Aganezov et al. 2019. Link
Massive genomic rearrangement acquired in a single catastrophic event during cancer development. Stephens et al. 2011. Link
Detection of chromosomal alterations in the circulation of cancer patients with whole-genome sequencing. Leary et al 2012. Link
Single-molecule analysis of genome rearrangements in cancer. Pole et al 2011. Link
A computational index derived from whole-genome copy number analysis is a novel tool for prognosis in early stage lung squamous cell carcinoma. Belvedere et al 2011. Link

Looking for signals in DNA
Systematic chromatin state comparison of epigenomes associated with diverse properties including sex and tissue type. Nature Communications 2015 Yen & Kellis Link
Five-vertebrate ChIP-seq reveals the evolutionary dynamics of transcription factor binding. Schmidt et al 2010.Link
Evidence for widespread association of mammalian splicing and conserved long-range RNA structures. Pervouchinne et al 2011. Link
Prediction of regulatory elements in mammalian genomes using chromatin signatures. Won et al. 2008. Link
Regulation of alternative splicing by histone modifications. Luco et al 2010. Link
Clustered ChIP-Seq-defined transcription factor binding sites and histone modifications map distinct classes of regulatory elements. Rye et al 2011. Link

Phylogeny and functional genomics
Six reference-quality genomes reveal evolution of bat adaptations. Jebb et al. 2020. Link
Multi-locus Analyses Reveal Four Giraffe Species Instead of One. Fennessy et al. 2016. Link
Evidence for extensive horizontal gene transfer from the draft genome of a tardigrade. Boothby et al PNAS 2015. Link
Three crocodilian genomes reveal ancestral patterns of evolution among archosaurs. Green et al 2014. Link
Confirming the Phylogeny of Mammals by Use of Large Comparative Sequence Data Sets. Prasad et al 2008. Link
Immunogenicity and cross-reactivity of a representative ancestral sequence in hepatitis C virus infection. Burke et al. 2012 Link

Modeling
A Hidden Markov Model for identifying essential and growth-defect regions in bacterial genomes from transposon insertion sequencing data. Dejesus and Ioerger 2013. Link
A study on the distribution of 37 well conserved families of C2H2 zinc finger genes in eukaryotes. Seetharam and Stuart 2013. Link
Alignment-free supervised classification of metagenomes by recursive SVM. Cui and Zhang, 2013. Link

Metagenomics
Extensive Unexplored Human Microbiome Diversity Revealed by Over 150,000 Genomes from Metagenomes Spanning Age, Geography, and Lifestyle. Pasolli et al. 2019. Link
Temporal Stability of the Human Skin Microbiome. Oh et al. 2016. Link
Culturing of 'unculturable' human microbiota reveals novel taxa and extensive sporulation. Browne et al. 2016. Link
Expanding the marine virosphere using metagenomics. Mizuno et al. 2013. Link
Insights into the phylogeny and coding potential of microbial dark matter. Rinke et al. 2013. Link