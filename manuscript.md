---
author-meta:
- Jackie Purdue
- Jocelyn McDonald
- Dayna Mikkelsen
- Finlay Maguire
- Robert G. Beiko
date-meta: '2020-02-17'
keywords:
- metagenome
- antimicrobial resistance
lang: en-CA
title: Identifying possibly novel sources of antimicrobial resistance in uncultivated
  bacterial and archeal metagenome-assembled genomes
...






<small><em>
This manuscript
([permalink](https://jackiepurdue.github.io/phylogenetic-amr-survey-manuscript/v/78655b80e6e6e15c03411bd9eb21499d1e24ea02/))
was automatically generated
from [jackiepurdue/phylogenetic-amr-survey-manuscript@78655b8](https://github.com/jackiepurdue/phylogenetic-amr-survey-manuscript/tree/78655b80e6e6e15c03411bd9eb21499d1e24ea02)
on February 17, 2020.
</em></small>

## Authors



+ **Jackie Purdue**<br>
    ![ORCID icon](images/orcid.svg){.inline_icon}
    [0000-0003-3131-0688](https://orcid.org/0000-0003-3131-0688)
    · ![GitHub icon](images/github.svg){.inline_icon}
    [jackiepurdue](https://github.com/jackiepurdue)
    · ![Twitter icon](images/twitter.svg){.inline_icon}
    [jackiepurdue](https://twitter.com/jackiepurdue)<br>
  <small>
     Faculty of Computer Science, Dalhousie University
  </small>

+ **Jocelyn McDonald**<br><br>
  <small>
     Faculty of Computer Science, Dalhousie University
  </small>

+ **Dayna Mikkelsen**<br><br>
  <small>
     Faculty of Computer Science, Dalhousie University
  </small>

+ **Finlay Maguire**<br>
    ![ORCID icon](images/orcid.svg){.inline_icon}
    [0000-0002-1203-9514](https://orcid.org/0000-0002-1203-9514)
    · ![GitHub icon](images/github.svg){.inline_icon}
    [fmaguire](https://github.com/fmaguire)
    · ![Twitter icon](images/twitter.svg){.inline_icon}
    [finlaym](https://twitter.com/finlaym)<br>
  <small>
     Faculty of Computer Science, Dalhousie University
     · Funded by Donald Hill Family Fellowship in Computer Science
  </small>

+ **Robert G. Beiko**<br><br>
  <small>
     Faculty of Computer Science, Dalhousie University
  </small>



## Abstract {.page_break_before}

Antimicrobial resistance (AMR) is a global threat to human health.
Efforts to prevent the spread of AMR rely on surveillance of possible AMR determinants.
Using phylogenetics to highlight potential sources of AMR could guide researchers in choosing organisms for phenotypic resistance testing. 
A systematic way of classifying AMR gene variants is important in comparing these phylogenetic relationships.
In this study, the phylogenetic neighborhoods of several named AMR genes are characterized by their diversity, spread, and potential for discovering possibly novel AMR variants.
Canonical sequence data from the Comprehensive Antibiotic Resistance Database (CARD) was used to query CARD prevalence data, NCBI sequence data, and draft quality metagenome assembled genomes (MAGs) from various uncultivated bacterial and archeal sources (UBAs).
Genes which were potentially associated with mobile colistin resistance (MCR) were found in the UBA sources.
New Delhi beta-lactamases (NDM), *Klebsiella pneumoniae* carbapenemases (KPC), and OXA beta-lactamases were not found to be represented in the UBAs,
[TODO: "gradient of the AMR trees"]
[TODO: conclusion: lots of novelty that cannot be accommodated by existing nomenclature schemes?]


## Introduction

Antimicrobials, substances which can kill or inhibit the growth of microbes [@Zvf1VhKR], are key effectors in the ecology of microorganisms.
The evolution of resistance to these substances, known as antimicrobial resistance (AMR), is an important and ancient adaptive process [@2xaXclNM].
In the last century we have adopted and used antimicrobials to great effect in clinical medicine and agriculture.
However, the use and abuse of antimicrobials has led to increasing levels of observed AMR [@1ByMfX8Y1].
This poses a growing global health risk by undermining our ability to treat infectious diseases and perform surgeries [@kDtOJsGI].
Infections by resistant microbes have greater mortality and morbidity [@kDtOJsGI] with the European Centre for Disease Prevention and Controlling estimating that 25,000 people per year die due to AMR [@OLzrpsK4].

AMR can be due to intrinsic resistance within the organism or the acquisition of resistance via lateral gene transfer [@2xaXclNM].
These mechanisms allow for the constant change of the resistome, making determining the scope of AMR within both pathogenic and non-pathogenic bacteria difficult [@1ByMfX8Y1].
To mitigate the spread of AMR the World Health Organization (WHO) created an action plan which emphasizes the need to strengthen our understanding and surveillance of AMR. 
An important aspect of this research is to examine the spread of AMR between environmental and clinical samples (https://www.who.int/antimicrobial-resistance/global-action-plan/en/).
One way to try to understand the evolution and spread of AMR is to perform large-scale evolutionary analyses with samples from lots of different environments/contexts.

Some of the most critical pathogens are the multi-drug resistant "ESKAPE" pathogens: _Enterococcus faecium_, _Staphylococcus aureus_, _Klebsiella pneumoniae_, _Acinetobacter baumannii_, _Pseudomonas aeruginosa_, and _Enterobacter_ spp. [@b2c0QSMI].
These are the leading cause of hospital-acquired infections and are largely only treatable with carbapenem or polymyxin antibiotics [@OLzrpsK4].
Carbapenems are broad spectrum beta-lactam antibiotics typically used to treat life threatening, high risk, and multi-drug resistant bacterial infections. 
beta-lactamase producing bacteria have difficulty degrading carbapenems when combined with beta-lactamase inhibitors making them effective treatments against pathogens with multi-drug resistance [@OLzrpsK4].
However, there has been a recent emergence of resistance to these antimicrobials, presenting a new threat to public health. 
One way microbes can develop carbapenem resistance is through the acquisition of carbapenamase genes. [@OLzrpsK4].
Three main carbapenamase genes of concern are _Klebsiella pneumoniae_ carbapenamase (KPC), New Delhi metallo-beta-lactamase (NDM) and OXA beta-lactamases [@OLzrpsK4].

Carbapenamases are classified as one of four classes (A-D) based on their molecular structure [@16ZzmUN7q].
Class A, C, and D both use a serine residue to hydrolyze beta-lactam antibiotics [@2p1n2mr5].
KPC genes are a part of class A. 
Many variants of KPC are spreading and being discovered, however carbapenamases within this class are more rare than the other three classes [@OLzrpsK4].
Class D contains the OXA family of beta-lactamases. 
Unlike KPC and NDM, this family is characterized by phenotype rather than genotype. 
This family is characterized by specific hydrolases that can hydrolyze oxacillin and cloxacillin, with the enzyme being poorly inhibited by clavulanic acid (https://card.mcmaster.ca/ontology/36026).
This results in a low amount of sequence homology within the family. 
A subset of this family, OXA-48 possesses carbapenem hydrolyzing activity [@UV1QqTS8].
The OXA-48 subfamily consists of five variants: OXA-48, OXA-162, OXA-163, OXA-181, OXA-204, and OXA-232 [@FqGNAObZ].
Class B beta-lactamases are metallo-enzymes that use a zinc active site to hydrolyze beta-lactam antibiotics. 
The NDM gene is classified as a class B beta-lactamase [@OLzrpsK4].
When pathogens become resistant to carbapenems, the last line of defense is the polymyxin antibiotic colistin. 
Polymyxins act via disrupting membrane permeability @17k3PVuIy. 
Colistin is limited to a last line defense against carbapenem resistant infections due to its neurotoxic and nephrotoxic effects [@17k3PVuIy]. 
Despite its already limited use, mobilized colistin resistance (MCR) have been discovered [@vQTzfitx]. 
Due to the emergence of resistance to many last-line antibiotics, it is important to characterize the total diversity and spread of these key resistance determinants.
However, to perform these types of analyses we need two resources: a clear consolidated definition of what constitutes an AMR-related gene and a large amount of sequencing microbial genomes.

Naming and defining AMR genes is difficult due to the legacy of research pre-DNA sequencing technology and the large number of different researchers and stakeholders involved in AMR.
AMR determinants are typically classified into AMR families, some of which are based on phenotypic properties, and some based on sequence variation.
The nomenclature is usually an acronym representing the mechanism of resistance, along with a numerical value to distinguish variants. 
Each sequence, determined to be novel by some arbitrary criteria, is assigned a new number.
Sequences are further sub-categorized when the sequence similarity is high, and as much as a single amino acid difference has given rise to a newly named determinant.
This system for classification has the potential to be misleading when conducting AMR research.
AMR families could appear to have a large amount of diversity, when in reality, sequences are closely related, and only a small number are actually distinct.
Additionally, sequences which are not homologues, could potentially be classified in the same family, simply based on their function.
This is a problem when attempting to characterize the AMR determinants by sequence similarity.
[TODO: analogy to multi-locus sequence typing?]

High-quality manually curated AMR databases such as the Comprehensive Antibiotic Resistance Database (CARD) [@nvbyXyPe] provide a unified resource for the definition, nomenclature and classification of AMR genes.
CARD organises this information CARD through the antibiotic resistance ontology (ARO), a controlled vocabulary with defined relationships.
There are two data-sets within CARD, canonical and prevalence.
Canonical is a conservative set of AMR genes and mutations that have been experimentally verified as being associated with resistance in a peer-reviewed publication.
This is therefore slightly biased towards the organisms that have been most heavily studied.
On the other hand, prevalence contains AMR sequences that have been detected by searching a broader set of WHO priority organism genomes from repositories such as National Center for Biotechnology Information (NCBI) for sequences similar to canonical sequences.
This _in silico_ search is performed using CARD's BLAST-based Resistance Gene Identifier (RGI) tool and greatly increases the sequence diversity in CARD [@nvbyXyPe].

However, this is still limited to a subset of all genomes currently available in central repositories like NCBI.
If we want to thoroughly understand the evolution and spread of AMR genes we need to analyse as many genomes as possible.
Unfortunately, the genomes in databases are largely sequenced from microbes that can be easily cultured. 
As only a subset of microbial diversity can be cultured, this means many of our existing genomes aren't necessarily representative of the environment from which they were sampled.
Recently, techniques have been developed that allow the recovery of genomes from metagenomic data e.g. [@DTtDOvle,@DfIRBmdF].
As metagenomic sequencing, the direct sequencing of all DNA in a sample, doesn't require culturing these metagenome-assembled genomes (MAGs) represent a huge source of novel microbial diversity.
Parks et. al. [@wapKbEHA], generated new 7,903 bacterial and archael (Uncultured Bacteria and Archaea; UBA) MAGs representing >30% increase in the sampled phylogenetic diversity of the bacteria and archaea.

Identifying and phylogenetically analysing key carbapenemase and colistin resistance genes in this dataset, CARD, CARD-prevalence and NCBI genomes, could greatly improve AMR surveillance of these genes.
We would characterise previously unseen diversity in genomes not yet analyzed for AMR, and provide insights into the diversity of AMR across non-clinical samples.
This could inform our understanding of the transmission of these mobile critical AMR genes and help refine their current nomenclature.
Therefore, in this work we present a comprehensive phylogenetic survey and analysis of KPC, NDM, OXA-48, and MCR across all currently sequenced genomes and large sets of previously uncharacterised metagenome-assembled genomes.


## Methods

### Data

To sample diverse sources for AMR, various sequence databases were sampled for phylogenetic analyses.
These sources include CARD canonical and prevalence sequences for the AMR genes under study, and associated homologs from NCBI non-redundant data and metagenomic data.
The 32 canonical MCR sequence variants (table {@tbl:mcr-variants}), 14 canonical NDM sequence variants (table {@tbl:ndm-variants}), 6 canonical OXA-48-like sequence variants(table {@tbl:oxa-variants}), and 18 canonical KPC sequence variants (table {@tbl:kpc-variants}) as labeled in the CARD database, were obtained as a reference. The AMR prevalence data was queried from CARD Prevalence 3.0.5. 
The NCBI non-redundant data was queried from all non-redundant GenBank, PDB, SwissProt, PDB, PIR, and PRF on May 17, 2019.
The metagenomic data came from a data-set of 7903 draft quality MAGs which were recovered from the Sequence Read Archive by Parks @wrBRBdFb. These genomes were chosen specifically because they were likely to be from lineages which were under-sampled, environmental and non-human gastrointestinal samples being the main focus.

In the case of OXA beta-lactamase, only OXA-48-like genes were used for analysis. The OXA family is characterized by phenotype rather than genotype, and results in a low amount of sequence homology within the family. 
The phenotype of OXA-48 results from carbapenem hydrolyzing activity @UV1QqTS8.
This subfamily of OXA contains homologous sequences suitable for this study.
Incorporating other subfamilies of OXA proved to be too cumbersome.


### Querying the data

The CARD canonical sequences from each family were used to perform a multiple query BLASTP (version 2.5.0 @s9ycaHcq) against the prevalence BLAST database with a e-value threshold and query coverages shown in Table {@tbl:exp-params}. 
Many of the sequences are nearly identical, thus they were further processed by clustering with CD-HIT version 4.8.1 at a minimum sequence identities as per table {@tbl:exp-params}

The reference CARD canonical sequences were also used to perform a multiple query BLASTP against the NCBI non-redundant database with a e-value threshold, and query coverage, also indicated in Table  {@tbl:exp-params}
For simplicity in identifying the taxonomic history of the non-redundant hits, MULTISPECIES sequences were removed from the analyses.
There are many highly sampled taxa and genes in the non-redundant database. 
To balance the distribution, and reduce the size of the non-redundant sequence set, CD-HIT version 4.8.1 was also used to cluster the data as per table {@tbl:exp-params}.

For the metagenomic data, RGI version 5.0 with CARD database version 3.02  @1ByMfX8Y1 was run on the contigs of the 7903 MAGS with the inclusion of loose, perfect, and strict hits.
Sequences possibly containing AMR gene prediction data for each gene family was produced by filtering RGI output based on the its association with the search strings for each determinant in Table {@tbl:exp-params}
The filtered data were translated to a blast database.
The CARD canonical sequences were used to perform a multiple query BLASTP against this UBA blast database with a e-value threshold and  query coverage in Table {@tbl:exp-params}.

For all sequence variants obtained from each data source, redundant results for the prevalence, NCBI, and UBA queries were filtered from these BLASTP results by retrieving only the longest sequence for each uniquely labeled result. 

<table>
<td>
||
|-|
Table: [TODO: Make table more readable/better labels etc] e-value, query coverage, and cluster percentage used for each AMR family experiment for the prevalence, ncbi non-redundant, and UBA databases. {#tbl:exp-params}
</td>
<tr><th>(A) MCR phosphoethanolamine transferase </th>
<th>(B) KPC beta-lactamase</th>
<th>(C) NDM beta-lactamase</th>
<th>(D) OXA beta-lactamase</th></tr>

<tr><td>


| | |
|-----------------|-------------------------------------|
| Tree            | LG+I+G4                             |
| e-value_p       | 1e-160                              |
| e-value_n       | 1e-160                              |
| e-value_u       | 1e-160                              |
| coverage_p      | 98                                  |
| coverage_n      | 98                                  |
| coverage_u      | 98                                  |
| clustering_p    | 100                                 |
| clustering_n    | 100                                 |
| clustering_u    | 100                                 |

</td><td>

| | |
|-----------------|-------------------------------------|
| Tree            | LG+I+G4                             |
| e-value_p       | 1e-100                              |
| e-value_n       | 1e-40                              |
| e-value_u       | 1e-10                              |
| coverage_p      | 99                                  |
| coverage_n      | 99                                  |
| coverage_u      | 60                                  |
| clustering_p    | 99                                 |
| clustering_n    | 70                                 |
| clustering_u    | 100                                 |

</td><td>

| | |
|-----------------|-------------------------------------|
| Tree            | LG+I+G4                             |
| e-value_p       | 1e-160                              |
| e-value_n       | 1e-160                              |
| e-value_u       | 1e-10                              |
| coverage_p      | 98                                  |
| coverage_n      | 98                                  |
| coverage_u      | 60                                  |
| clustering_p    | 100                                 |
| clustering_n    | 100                                 |
| clustering_u    | 100                                 |

</td><td>

| |  |
|-----------------|-------------------------------------|
| Tree            | LG+I+G4                             |
| e-value_p       | 1e-100                              |
| e-value_n       | 1e-100                              |
| e-value_u       | 1e-10                              |
| coverage_p      | 90                                  |
| coverage_n      | 99                                  |
| coverage_u      | 95                                  |
| clustering_p    | N/A                                 |
| clustering_n    | N/A                                 |
| clustering_u    | N/A                                 |

</td></tr>
</table>


### Sequence Alignmnet

Two alignments were created for each AMR determinant under study.
The first alignment was created to compare the phylogenetic relationship of only the putative sequences.
The second alignment was created for an overall comparison of sequences. 

The putative AMR alignment was made up of the sequences from the CARD prevalence data were concatenated in one multi-FASTA format file with the canonical sequences and an outgroup chosen for each AMR family as per table {@tbl:outgroups}. 
In the second, more diverse alignment, The filtered sequences from NCBI non-redundant data, CARD prevalence data, UBA data were all concatenated to one multi-FASTA format file with the canonical sequences with the same outgroup sequences (table {@tbl:outgroups}).

This set of concatenated amino acid sequences were aligned with MAFFT-LINSI version 7.40 and trimmed by trimal version 1.4.rev22 using the automated1 option.

### Creation of phylogenies

For each alignment under each AMR family under study, IQ-TREE multicore version 1.6.9 @JOWSuu8G was used to build a bootstrapped tree with -bb 1000 with the G+I+G4 model of substitution. 
Tree visualizations were created with ETE Toolkit version 3, and annotated with taxonomic information for each rank, and environmental and AMR data, based on information from the various metadata. (See supplemental).


## Results

### Phylogenetic analysis of MCR sequences

The phylogenetic relationships of the CARD canonical sequences, and the CARD prevalence sequences involving the MCR family were investigated to show the pylogenetic relationship of only the putative MCR sequences without the noise of additional sequences.
A total of 87 genes, an out-group, the 32 canonical sequences, and the 54 prevalence sequences (clustered as per Table {@tbl:exp-params}), were selected for analyses.
The tree in Figure {@fig:canon-prev-tree} shows several distinct clades.
Each MCR variant forms a clade.
MCR-1, MCR-2, and MCR-6 form a clade, appearing to more closely related to one another than with the other MCR family members.
This clade is also closely related to the ICR-Mc clade.
ICR-Mc @JT9eRkR8 is another phosphoethanolamine transferase which confers colistin resistance.

![Phylogenetic relationship of 32 canonical (labels prefixed with lcl_canon_ in yellow), 54 prevalence (labels prefixed with lcl_prev_ in tan) MCR family sequences, and an outgroup from Betaproteobacteria (lcl_outgroup in grey). Each MCR variant is coloured based on its primary numerical value.](images/mcr191004_canon_prev.fasta.aln.trim.treefile.collapsed.svg){#fig:canon-prev-tree}

The relationships were then collapsed to representative sequences for each numbered MCR variant in figure {@fig:canon-prev-tree-collapsed} for a more condensed visualization of the overall MCR family relationships. 

From figure {@fig:canon-prev-tree-collapsed} the gradient of diversity between some variants is occupied, such as the relationship of MCR 1, 2, and 6 and ICR-Mc, and MCR 7, 3, and 9.
There are also relationships in which this diversity is missing, where unrepresented clades of MCR could exist.

![Phylogenetic relationship of 9 MCR family sequences, and an outgroup from Betaproteobacteria.](images/canon_prev.fasta.aln.trim.treefile.collapsed.svg){#fig:canon-prev-tree-collapsed}

In an attempt to discover these potential clades between these named MCR families, sequences from the NCBI non-redundant data were added to the analysis to be compared with the canonical and prevalence sequences.
This resulted in a total of 409 sequences for subsequent analysis, all labeled as phosphoethanolamine lipid A transferase genes, where 104 hits were labeled as MCR family genes.

In addition, the 7903 draft quality MAGs were queried for AMR genes with RGI.
RGI produced 1457246 results AMR determinants under the loose cutoff from the UBA data, 7171 for the strict cutoff,and 310 for the loose cutoff.
It was hoped that pyhlogenetic analysis could find AMR determinants would be found in under the loose criterion that may have been missed by RGI-CARD.
The UBA BLAST results were included in the phylogeny in Figure {@fig:canon-prev-nrdb-uba-tree} for the analysis.
The remainder of the analysis deals with relationships which are deemed to be interesting based on the locations of the UBAs between MCR family clades.


Between the clade containing MCR 3, and the most recent common ancestor of MCR 3 and MCR 7 clades (figure {@fig:mcr-3-9}), there is a clade of sequences from NCBI which have been reported as MCR 3 [TODO: look at linked literature].
Present within this clade is a single UBA result, UBA705, which the Parks data @wrBRBdFb reports as a Comparative metagenome analyses of anode-associated microbial communities developed in rice paddy field-soil microbial fuel cells, is reported to be *Aeromonas hydrophilia*.
This present within the clade alone with several other canonical and non-redundant Aeromonadalacea.
Aeromonas hydrophilia is a species which has been found to have an MCR-3 gene.
Even though qualities vary (Table ??), the sequences branch in the expected location.

Between the clade containing MCR 7, and the most recent common ancestor of MCR 3 and MCR 7 clades, a clade of phosphoethanolamine lipid A transferase clade appears.
This clade consists of the genus of gram negative bacteria, *Aeromonas*, @16EwPCiJT which is sometimes involved in human infection.
This clade also includes an *Aeromonas veroni* hit from  from epidermal mucus of *Anguilla anguilla* in the UBA data.
Between MCR 9 and the most recent common ancestor of MCR 3 and 9, a clade of *Aeromonas* associated phosphoethanolamine lipid A transferases appear.

The MCR 9 containing clade contains 8 UBAs and several NCBI non-redundant hits not reported as MCR family genes.
5 Loose hits for MCR in a *Leclercia adecarboxyla* branch within this clade. 
These *Leclercia* branch below the common ancestor of MCR-9 and MCR-3 which are well supported. The *Leclercia* UBAs were all sampled from New York City MTA subway samples Metagenome.
Acinetobacter is another opportunistic pathogen  @8uz5m0fP which is becoming resistant to many antimicrobials.


![Clade containing putative MCR3 and MCR 9 clades pruned from Phylogenetic relationship of 32 canonical (labels prefixed with lcl_canon_ in yellow), and 54 prevalence (labels prefixed with lcl_prev_ in tan) MCR family sequences, 595 NCBI non-redundant sequences (labels prefixed with lcl_prev_ in blue), and 91 UBA sourced sequences (labels prefixed with lcl_prev_ in green). Each MCR variant is coloured based on its primary numerical value. If the sequence is not reported to be MCR family it is coloured in grey.](images/mcr3_mcr9_diversity.svg){#fig:mcr-3-9}


Between MCR 5 and ICR-Mc (figure {#fig:mcr-5-icr}), there appear clades of diversity in the genus *Psychrobacter*.
Branching between these two clades, as a descendant to this ancestor, is a clade of *Psycrobacter* species bacteria.
This clade includes several hits from the non-redundant database, and two hits from the UBA data.
According to the Parks @wrBRBdFb data, the identity of these samples are,
UBA3068, A *Psychrobacter sp.*, sampled from Oil polluted marine microbial communities from Coal and Oil in Point Santa Barbara, California, USA
and, UBA4193, a *Psychrobacter sp.*, sampled from the New York City MTA subway samples.
The quality information for these sequences, shown in Table ??, shows that UBA3068 is near complete, while UBA4193 is only partial.
It is encouraging to see that even with the quality difference, these two sequences branch in the expected clade.
*Psychrobacter* @BjoH1Vii is a Genus is widespread and includes many cold adapted bacteria, it is an opportunistic pathogen, and has been found sometimes be a cause of infections in humans, animals, and fish. Many new species of *Psychrobacter* have been discovered in cold climates @WLzELTTa. Some of the species have been shown to be resistant to colistin, like *Psychrobacter vallis ps. nov.* and *Psychrobacter aquaticus ps. nov.* @2NZAmp2H and is sister to [TODO: display new tree such that *Acinetobacter* is shown]
Another clade between these two variants contains phosphoethanolamine transferases from the genus *Stenotrophomonas*, including *Stenotrophomonas maltophilia* and *Stenotrophomonas acidaminiphila* which multidrug-resistant opportunistic pathogen @Ovca71PG.
Several UBA hits for *Stenotrophomonas maltophilia* show up as shotgun sequencing of environmental samples. [TODO: quality information]


![Clade containing putative MCR 5 and ICR-Mc clades pruned from Phylogenetic relationship of 32 canonical (labels prefixed with lcl_canon_ in yellow), and 54 prevalence (labels prefixed with lcl_prev_ in tan) MCR family sequences, 595 NCBI non-redundant sequences (labels prefixed with lcl_prev_ in blue), and 91 UBA sourced sequences (labels prefixed with lcl_prev_ in green). Each MCR variant is coloured based on its primary numerical value. If the sequence is not reported to be MCR family it is coloured in grey.](images/mcr5_icrmc_diversity.svg){#fig:mcr-5-icr}


[TODO: visualization with plasmid distribution ]


### Phylogenetic analysis of KPC

Using the 18 canonical sequences from Table {@tbl:kpc-variants} as query sequences, 25 prevalence sequences, 376 non-redundant sequences, and 6 UBA sequences were recovered from the various databases. The result was 
combined in the phylogeny displayed in figure {@fig:kpc-tree}.
This phylogeny shows that many of the resulting sequences are distant from the canonical sequences. The main clade in figure {@fig:kpc-main-tree} shows that many of the amr determinants are named as distinct sequences, while not having much phylogenetic distance between them.
The most closely related clade is a clade containing IMI and SME-type beta lactamases.
The remaining sequences are in a clade containing a large amount of class A beta-lactamases from the non-redundant data. All of the UBA sequences were present in this portion of the tree.

![A clade pruned from the phylogeny in figure {#fig:kpc-tree} which represents the most closely related genes to the KPC family genes.](images/kpc_main_clade.svg){#fig:kpc-main-tree}


### Phylogenetic analysis of NDM

14 canonical sequences were used to query the same databases as in the former phylogenetic analyses. The genes retained for the phylogeny were the 14 canonical sequences, 8 prevalence sequences, 12 non-redundant sequences, 1 UBA sequence, and 1 out-group. This resulted in the phylogenetic relationship in Figure {@fig:ndm-tree}. 

![Phylogenetic relationship of 14 canonical (labels prefixed with lcl_canon_ in yellow), 8 prevalence (labels prefixed with lcl_prev_ in tan) MCR family sequences, 12 NCBI non-redundant database sequences (lcl_nrdb), 1 UBA sequence (lcl_uba) and an outgroup from Betaproteobacteria (lcl_outgroup in grey). Each MCR variant is coloured based on its primary numerical value.](images/ndm191128_canon_prev_nrdb_uba.fasta.aln.trim.treefile.expanded.svg){#fig:ndm-tree-all}

The 12 sequences resulting from the NCBI data included 3 genes reported to be NDM-1, NDM-3, and NDM-5, while the other 4 genes were reported to be general beta lactamase/carbapenemase hits.
As in the KPC phylogeny (figure {@fig:kpc-main-tree}), there is very little phylogenetic difference between the named variants of NDM.
The only significantly phylogenetically resolved genes in this clade were the prevalence hit for NDM-1 found in Shigella sonnei representing only itself in the cd-hit cluster, and the ncbi hits labeled as NDM-1 and NDM-5.
The naming of these sequences seem not to be congruent with the phylogenetic relationships present in the tree. Some of the NDM-1 and NDM-5 genes are more closely related to the other NDM variants than themselves.
The one  BA BLAST result branches far from the clade containing the canonical indicating that under the coverage queried, there are no reasonably detectable NDM homologues in the UBA data. The alignment of this UBA under this relaxed query coverage of 60% is already pushing the limits of a "good alignment", and reducing this further would produce meaningless results.

### Phylogenetic analysis of OXA-48

In investigating the phylogenetic relationship of OXA-48, the result was similar to that of NDM.
There were multiple BLAST results for UBA sequences, but the hits were too phylogenetically dissimilar to draw a conjecture about their relationship to the OXA family. 6 canonical sequences, and the 14 prevalence sequences, 20 non-redundant sequences, and 411 UBA sequences were combined in the phylogeny in Figure {@fig:oxa-tree}

![The main phylogenetic relationship pruned from the tree inferred from OXA-48-like sequences from figure {#fig:oxa-tree}](images/oxa_main_clade.svg){#fig:oxa-main-tree}


The OXA-48 prevalence hits added further diversity to the reference OXA-48-like sequences. OXA-436 @KEhNzdys was found, clustered with no other gene, in the prevalence data, and OXA-514 and OXA-515 were found in the non-redundant data. Much like in NDM, this diversity seems only to be diversity in name. The various named variants are too similar to produce significant phylogenetic resolution. This is most likely a symptom of the problematic way in which OXA family members are named.


## Discussion

* TODO: Discuss the following:
  * Messed up nomenclature
  * We found a lot of intermingled MCRs, not so much with the others (plasmids etc.)
  * Why were some UBAs not covered? (plasmids)
  * What should we do with naming, especially as new variants are discovered and fill in the tree?
  * Taxonomic anomalies and how they may be explained
  * There were many clinical samples represented that *did* yield MCRs, but the recovery could be bad
  



## Conclusion



# Supplemental


|MCR-9 MCR-1.8 MCR-1.11 MCR-3.4 MCR-3.11 MCR-6.1 MCR-3.3 MCR-2.2 MCR-1.5 MCR-3.6 MCR-3.10 MCR-3.5 MCR-1.10 MCR-1.9 MCR-3.9 MCR-3.8 MCR-3.7 MCR-3.2 MCR-1.6 MCR-1.2 MCR-1.3 MCR-1.4 MCR-8 MCR-7.1 MCR-1.7 MCR-1.12 MCR-1.13 MCR-3.12 MCR-4.2 MCR-4.3 MCR-4.4 MCR-4.5 MCR-5.2|
|-|
Table: Names of the canonical MCR phosphoethanolamine transferase variants from CARD database {#tbl:mcr-variants}


|KPC-1 KPC-3 KPC-4 KPC-5 KPC-6 KPC-7 KPC-8 KPC-9 KPC-10 KPC-11 KPC-12 KPC-13 KPC-14 KPC-15 KPC-16 KPC-17 KPC-19 KPC-22 KPC-24|
|-|
Table: Names of the canonical beta-lactamase variants from CARD database {#tbl:kpc-variants}


|NDM-1 NDM-2 NDM-5 NDM-3 NDM-4 NDM-6 NDM-7 NDM-8 NDM-9 NDM-10 NDM-11 NDM-12 NDM-13 NDM-14 NDM-17|
|-|
Table: Names of the canonical NDM beta-lactamase variants from CARD database {#tbl:ndm-variants}


|OXA-162 OXA-163 OXA-181 OXA-204 OXA-232 OXA-48|
|-|
Table: Names of the canonical OXA beta-lactamase variants from CARD database {#tbl:oxa-variants}

TODO: Quality/CHECKM information for UBAs

| Outgroup to AMR Family | Gene                                         | Species                | Class                |
|------------------------|----------------------------------------------|------------------------|----------------------|
| MCR                    | phosphoethanolamine--lipid A transferase     | Oxalobacter formigenes | Betaproteobacteria   |
| KPC                    | class A beta-lactamase                       | Mesorhizobium loti     | Alpha Proteobacteria |
| NDM                    | VIM-4 metallo-beta-lactamase                 | Alcaligenes faecalis   | Betaproteobacteria   |
| OXA-48                 | OXA-10 family class D beta-lactamase OXA-454 | Delftia acidovorans    | Betaproteobacteria   |
Table: Outgroups chosen in building the phylogenies of the 4 AMR families. {#tbl:outgroups}


#### MCR Alignment
[TODO: visualization with alignment/entropy]
![placeholder](images/aln_mcr.png){#fig:ndm-tree}

#### KPC Alignment
[TODO: visualization with alignment/entropy]
![placeholder](images/aln_kpc.png){#fig:ndm-tree}

#### NDM Alignment
[TODO: visualization with alignment/entropy]
![placeholder](images/aln_ndm.png){#fig:ndm-tree}

#### OXA-48 Alignment
[TODO: visualization with alignment/entropy]
![placeholder](images/aln_oxa.png){#fig:ndm-tree}


![Phylogenetic relationship of 32 canonical (labels prefixed with lcl_canon_ in yellow), and 54 prevalence (labels prefixed with lcl_prev_ in tan) MCR family sequences, 595 NCBI non-redundant sequences (labels prefixed with lcl_prev_ in blue), and 91 UBA sourced sequences (labels prefixed with lcl_prev_ in green). Each MCR variant is coloured based on its primary numerical value. If the sequence is not reported to be MCR family it is coloured in grey.](images/mcr191004_canon_prev_nrdb_uba.fasta.aln.trim.treefile.expanded.svg){#fig:canon-prev-nrdb-uba-tree}

![Phylogenetic relationship (lcl_canon) OXA-48 family sequences along with 14  prevalence (lcl_prev) sequences.](images/oxa191128.canon.svg){#fig:oxa-tree}

![Phylogenetic relationship (lcl_canon) OXA-48 family sequences along with 14  prevalence (lcl_prev) sequences.](images/oxa191128.expanded.svg){#fig:oxa-tree-all}

![Phylogenetic relationship (lcl_canon) NDM family sequences along with 14  prevalence (lcl_prev) sequences.](images/ndm191128.canon.svg){#fig:ndm-tree}

![Phylogenetic relationship (lcl_canon) KPC family sequences along with 14  prevalence (lcl_prev) sequences.](images/kpc191127.canon.svg){#fig:kpc-tree}


![Phylogenetic relationship (lcl_canon) KPC family sequences along with 14  prevalence (lcl_prev) sequences.](images/kpc191127_canon_prev_nrdb_uba.fasta.aln.trim.treefile.expanded.svg){#fig:kpc-tree-all}


## References {.page_break_before}

<!-- Explicitly insert bibliography here -->
<div id="refs"></div>
