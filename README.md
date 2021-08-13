# CdeCMx2021 Club 7: Atacando genes asociados con la obesidad

This repository contains the Jupyter notebooks, networks, and other files for the CdeCMx 2021 "Club 7: Atacando genes asociados con la obesidad".

Current content is:

- Google Colab Jupyter notebooks. used during the club. They use NetworkX (https://networkx.github.io/) to import a network, visualize it, and calculate some basic network measures. They also use pandas (https://pandas.pydata.org/) to import genes from genome-wide-association studies (GWAS) of diseases such as type 2 diabetes and obesity. Using these GWAS genes, NetworkX, and protein-protein interaction (PPI) networks, we create and visualize gene-disease networks, and the neighborhood of these genes in the PPI networks. 

- Protein-protein interaction (PPI) or drug-protein interaction networks. We propose to use these networks to infer drugs that could be repurposed to target proteins/genes related to obesity.
  * Human PPI network. Luck et al., Nature 2020. (https://www.nature.com/articles/s41586-020-2188-x).
  * Drug - Human protein target network. DrugBank (https://www.drugbank.ca/).

Note: These networks were obtained from NDEx (http://ndexbio.org/). You need to register to copy these networks and export them in the GraphML format (which can be read by NetworkX and most network libraries and software.
  
Can we do a similar approach (as in the papers below) to infer drug repurposing targets for obesity-related genes based on the proximity of a drug's protein targets to the obesity-related proteins/genes?
  * Zhou et al., Cell Discovery 2020 (https://www.nature.com/articles/s41421-020-0153-3).
  * Gysi et al., PNAS 2021 (https://www.pnas.org/content/118/19/e2025581118.short).
  

## The Project
  
1. Use NetworkX (Python) to calculate network theory measures on each of the interaction networks (protein-protein, drug-protein). What is the distribution of these network measures? What are the nodes or node pairs with the highest value for these measures in each network?
2. Combine the protein-protein and drug-protein interaction networks. Do the same as in part 1 but for this combined network.
3. Choose a group of genes from a GWAS study on obesity. It could be the genes from the [Akbari et al. 2021](https://doi.org/10.1126/science.abf8683) study (the list of genes is [here](https://github.com/jgtz/CdeCMx2021-NetworkBiology_ObesityGenes/tree/main/Google%20Colabs/Files%20used)). It could also be one of the 12 reported traits of the [obesity studies](https://www.ebi.ac.uk/gwas/efotraits/EFO_0001073) from the GWAS catalog. Where do these obesity genes of interest sit in the distribution of the network measures of the combined network from point 2?
4. Using the group of genes you chose, create a subgraph of the combined protein-protein and drug-protein network that contains only these genes, their neighbors, and the drugs that target them. Could any of these drugs be reasonable repurposing candidates to target obesity? Do they target any of the genes with the highest significance in the GWAS? 
5. Find the distance from each drug to each of the protein/genes in the group you selected. Could any of these drugs be reasonable repurposing candidates to target obesity? Which ones?
6. Visualize the results from each these parts.
7. Create a website, Google Colab notebook, and video with your results

Extra points:

1. For each drug, compare the distance of each drug-protein pair to the distance of each drug-protein pair restricted to the proteins in your group of genes. Are there any drugs that have a much shorter distance to the proteins in your group of genes compared to all other proteins?
2. Apply the proximity-based methods "Pipeline P1" and/or "Pipeline P2" from Gysi et al. paper using these the combined PPI network. What are the top drugs you find? Visualize this result.


## Notes and Hints

- Certain network measures can take a long time to calculate in large networks (like the Human and Drug-Human PPI networks). In particular, distance and betweeness centrality can take some time. You can try calculating these measures for a subset of nodes or nodes pairs to get an idea of how long calculating all will take.
- The Human PPI and Drug-Human PPI networks are not going to be easy to visualize using NetworkX. There's dedicated network software for network visualization of these large networks, like Cytoscape (https://cytoscape.org/). For visualization of smaller networks you can use yEd (https://www.yworks.com/products/yed). It is possible that your computer might not be abble to load or be too slow if you load these large networks in Cytoscape, so keep that in mind.
