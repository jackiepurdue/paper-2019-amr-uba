---
author-meta:
- Jackie Purdue
- Jocelyn McDonald
- Dayna Mikkelsen
- Finlay Maguire
- Robert G. Beiko
date-meta: '2020-05-31'
keywords:
- metagenome
- antimicrobial resistance
lang: en-CA
title: Reviewing the phylogenetic relationships and nomenclature of common antimicrobial
  resistance genes
...






<small><em>
This manuscript
([permalink](https://jackiepurdue.github.io/phylogenetic-amr-survey-manuscript/v/26150239cac7ced88d0ee258dda43b2f25d890a6/))
was automatically generated
from [jackiepurdue/phylogenetic-amr-survey-manuscript@2615023](https://github.com/jackiepurdue/phylogenetic-amr-survey-manuscript/tree/26150239cac7ced88d0ee258dda43b2f25d890a6)
on May 31, 2020.
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
In this study, the phylogenetic neighborhoods of several named AMR genes are examined for diversity, spread, and consistency in classification.
Canonical sequence data from the Comprehensive Antibiotic Resistance Database (CARD) for mobile colistin resistance (MCR), New Delhi beta-lactamase (NDM), Klebsiella pneumoniae carbapenemase (KPC), and OXA beta-lactamase were used to query CARD prevalence data, NCBI sequence data, and draft quality metagenome assembled genomes (MAGs) from various uncultivated bacterial and archeal sources (UBAs).
A phylogeny of this expanded set of candidate resistance genes was produced with a limited amount of new diversity, most notably with genes which were potentially associated with MCR.
In this phylogenetic context, some of the names of the genes were found to be inconsistent or inconsequential.


## Introduction

Antimicrobials, substances which can kill or inhibit the growth of microbes [@Zvf1VhKR], are key effectors in the ecology of microorganisms.
The evolution of resistance to these substances, known as antimicrobial resistance (AMR), is an important and ancient adaptive process [@2xaXclNM].
In the last century we have adopted and used antimicrobials to great effect in clinical medicine and agriculture.
However, the use and abuse of antimicrobials has led to increasing levels of observed AMR [@1ByMfX8Y1].
This poses a growing global health risk by undermining our ability to treat infectious diseases and perform surgeries [@kDtOJsGI].
Infections by resistant microbes have greater mortality and morbidity [@kDtOJsGI] with the European Centre for Disease Prevention and Control estimating that 25,000 people per year die due to AMR [@OLzrpsK4].

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
For example, the MCR phosphoethanolamine transferase gene family is a family of genes which code for a hinderance of the ability of colistin to bind to the cell membrane.
The MCR-3 gene has a sequence identity which has been deemed to be significantly different than that of the other MCR genes in the family.
MCR-3.1, is has been deemed to be a variant of the MCR-3 gene, which has a slight variation in gene sequence from other MCR-3 genes.
In looking at another AMR gene family, NDM beta-lactamase, a different set of criteria are used to name variants.
NDM betalactamases are classified as such by their ability to confer resistance to carbapenems and some other antibiotics.
In this case, NDM-1, and NDM-2 are only different by a single amino acid substitution.
This system for classification has the potential to be misleading when conducting AMR research.
As in the examples, AMR families could appear to have a large amount of diversity, when in reality, sequences are closely related, and only a small number are actually distinct.
Additionally, sequences which are not homologues, could potentially be classified in the same family, simply based on their function. 
An example of this is the OXA betalactamase family, which is is a phenotypically characterized family, and there are examples of determinants which have a low amount of sequence homology.
OXA-20 has less than 20% amino acid sequence identity when compared with several other OXA family betalactamases [@1AFSAuSwx].
This is a problem when attempting to characterize the AMR determinants by sequence similarity.

High-quality manually curated AMR databases such as the Comprehensive Antibiotic Resistance Database (CARD) [@nvbyXyPe] provide a unified resource for the definition, nomenclature and classification of AMR genes.
CARD organizes this information CARD through the antibiotic resistance ontology (ARO), a controlled vocabulary with defined relationships.
There are two data-sets within CARD, canonical and prevalence.
Canonical is a conservative set of AMR genes and mutations that have been experimentally verified as being associated with resistance in a peer-reviewed publication.
This is therefore slightly biased towards the organisms that have been most heavily studied.
On the other hand, prevalence contains AMR sequences that have been detected by searching a broader set of WHO priority organism genomes from repositories such as National Center for Biotechnology Information (NCBI) for sequences similar to canonical sequences.
This database is meant to represent the diversity of all current sequence data available to the public.
This _in silico_ search is performed using CARD's BLAST-based Resistance Gene Identifier (RGI) tool and greatly increases the sequence diversity in CARD [@nvbyXyPe].

However, this is still limited to a subset of all genomes currently available in central repositories like NCBI.
If we want to thoroughly understand the evolution and spread of AMR genes we need to analyses as many genomes as possible.
Unfortunately, the genomes in databases are largely sequenced from microbes that can be easily . 
As only a subset of microbial diversity can be cultured, this means many of our existing genomes aren't necessarily representative of the environment from which they were sampled.
Recently, techniques have been developed that allow the recovery of genomes from metagenomic data e.g. [@DTtDOvle,@DfIRBmdF].
As metagenomic sequencing, the direct sequencing of all DNA in a sample, doesn't require culturing these metagenome-assembled genomes (MAGs) represent a huge source of novel microbial diversity.
Parks et. al. [@wapKbEHA], generated new 7,903 bacterial and archaeal (Uncultured Bacteria and Archaea; UBA) MAGs representing >30% increase in the sampled phylogenetic diversity of the bacteria and archaea.

Identifying and phylogenetically analyzing key carbapenemase and colistin resistance genes in this dataset, CARD, CARD-prevalence and NCBI genomes, could greatly improve AMR surveillance of these genes.
We would characterize previously unseen diversity in genomes not yet analyzed for AMR, and provide insights into the diversity of AMR across non-clinical samples. This could inform our understanding of the transmission of these mobile critical AMR genes and help refine the nomenclature of this ever-expanding dataset. Therefore, in this work we present a comprehensive phylogenetic survey and analysis of KPC, NDM, OXA-48, and MCR across all currently sequenced genomes.


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

The CARD canonical sequences from each family were used to perform a multiple query BLASTP (version 2.5.0 @s9ycaHcq) against the prevalence BLAST database with a e-value threshold and query coverages shown in Table 1. 
Many of the sequences are nearly identical, thus they were further processed by clustering with CD-HIT version 4.8.1 at a minimum sequence identities as per table {@tbl:exp-params}

The reference CARD canonical sequences were also used to perform a multiple query BLASTP against the NCBI non-redundant database with a e-value threshold, and query coverage, also indicated in Table 1
There are many highly sampled taxa and genes in the non-redundant database. 
To balance the distribution, and reduce the size of the non-redundant sequence set, CD-HIT version 4.8.1 was also used to cluster the data as per table {@tbl:exp-params}.

For the metagenomic data, RGI version 5.0 with CARD database version 3.02  @1ByMfX8Y1 was run on the contigs of the 7903 MAGS with the inclusion of loose, perfect, and strict hits.
Sequences possibly containing AMR gene prediction data for each gene family was produced by filtering RGI output based on the its association with the search strings for each determinant in Table 1
The filtered data were translated to a blast database.
The CARD canonical sequences were used to perform a multiple query BLASTP against this UBA blast database with a e-value threshold and  query coverage in Table 1. The E-values were chosen such that a tractable or sufficient
number of sequences resulted from their respective database query. The minimum BLAST query coverages were chosen as to reduce noise in the final alignment, thus reducing the possibility of attempting to align non-homologous sequences.

For all sequence variants obtained from each data source, redundant results for the prevalence, NCBI, and UBA queries were filtered from these BLASTP results by retrieving only the longest sequence for each uniquely labeled result. 

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-yj5y{background-color:#efefef;border-color:inherit;text-align:center;vertical-align:top}
.tg .tg-j4pq{background-color:#efefef;border-color:#000000;text-align:center;vertical-align:top}
.tg .tg-llyw{background-color:#c0c0c0;border-color:inherit;text-align:left;vertical-align:top}
.tg .tg-0pky{border-color:inherit;text-align:left;vertical-align:top}
.tg .tg-0lax{text-align:left;vertical-align:top}
</style>
<table class="tg">
<thead>
  <tr>
    <th class="tg-yj5y" rowspan="2">AMR<br>Determinant</th>
    <th class="tg-yj5y" colspan="3">Minimum BLAST<br>E-value<br></th>
    <th class="tg-yj5y" colspan="3">Minimum BLAST <br>Query Coverage</th>
    <th class="tg-j4pq" colspan="3">CD-HIT Sequence <br>Identity Threshold</th>
  </tr>
  <tr>
    <td class="tg-llyw">CARD<br></td>
    <td class="tg-llyw">NCBI<br></td>
    <td class="tg-llyw">Parks<br></td>
    <td class="tg-llyw">CARD<br></td>
    <td class="tg-llyw">NCBI<br></td>
    <td class="tg-llyw">Parks<br></td>
    <td class="tg-llyw">CARD<br></td>
    <td class="tg-llyw">NCBI<br></td>
    <td class="tg-llyw">Parks<br></td>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0pky">MCR<br></td>
    <td class="tg-0pky">1e-160</td>
    <td class="tg-0pky">1e-160</td>
    <td class="tg-0pky">1e-160</td>
    <td class="tg-0pky">98</td>
    <td class="tg-0pky">98</td>
    <td class="tg-0pky">98</td>
    <td class="tg-0pky">100</td>
    <td class="tg-0pky">100</td>
    <td class="tg-0pky">100</td>
  </tr>
  <tr>
    <td class="tg-0pky">KPC</td>
    <td class="tg-0pky">1e-100</td>
    <td class="tg-0pky">1e-40</td>
    <td class="tg-0pky">1e-10</td>
    <td class="tg-0pky">99</td>
    <td class="tg-0pky">99</td>
    <td class="tg-0pky">60</td>
    <td class="tg-0pky">99</td>
    <td class="tg-0pky">70</td>
    <td class="tg-0pky">100</td>
  </tr>
  <tr>
    <td class="tg-0pky">NDM</td>
    <td class="tg-0pky">1e-160</td>
    <td class="tg-0pky">1e-160</td>
    <td class="tg-0pky">1e-10</td>
    <td class="tg-0pky">98</td>
    <td class="tg-0pky">98</td>
    <td class="tg-0pky">60</td>
    <td class="tg-0pky">100</td>
    <td class="tg-0pky">100 </td>
    <td class="tg-0pky">100</td>
  </tr>
  <tr>
    <td class="tg-0pky">OXA</td>
    <td class="tg-0pky">1e-100</td>
    <td class="tg-0pky">1e-100</td>
    <td class="tg-0pky">1e-10</td>
    <td class="tg-0pky">90</td>
    <td class="tg-0pky">99</td>
    <td class="tg-0pky">95</td>
    <td class="tg-0pky">N/A</td>
    <td class="tg-0pky">N/A</td>
    <td class="tg-0pky">N/A</td>
  </tr>
  <tr>
    <td class="tg-0lax" colspan="10"><b>Table 1</b>: Parameters used with BLAST and CD-HIT to obtain sequences for the phylogenies<br>of MCR phosphoethanolamine transferase, and KPC, NDM, and OXA beta-lactamases.<br>For each determinant, the minimum BLAST E-values, minimum query coverages, and CD-HIT Sequence Identity <br>threshold for clustering sequences are displayed for each database.<br>CARD represents the RGI-CARD prevalence sequence data, NCBI represents the NCBI non-redundant sequence<br>data, and Parks represents the MAG data source.<br></td>
  </tr>
</tbody>
</table>


### Sequence Alignment

Two alignments were created for each AMR determinant under study.
The first alignment was created to compare the phylogenetic relationship of only the putative sequences.
The second alignment was created for an overall comparison of sequences. 

The putative AMR alignment was made up of the sequences from the CARD prevalence data were concatenated in one multi-FASTA format file with the canonical sequences and an outgroup chosen for each AMR family as per table {@tbl:outgroups}. 
In the second, more diverse alignment, The filtered sequences from NCBI non-redundant data, CARD prevalence data, UBA data were all concatenated to one multi-FASTA format file with the canonical sequences with the same outgroup sequences (table {@tbl:outgroups}).

This set of concatenated amino acid sequences were aligned with MAFFT-LINSI version 7.40 and trimmed by trimal version 1.4.rev22 using the automated1 option.

### Creation of phylogenies

For each alignment under each AMR family under study, IQ-TREE multicore version 1.6.9 @JOWSuu8G was used to build a bootstrapped tree with -bb 1000 with the G+I+G4 model of substitution. 
Tree visualizations were created with ETE Toolkit version 3.
The trees were annotated with taxonomic information for each rank by using ETE’s NCBI taxonomy module to translate the names result set from the various databases to taxonomic identifiers.
The taxonomic identifier was used to query NCBI's taxonomy database for the taxonomy information.
In cases where there were multiple hits for genes, the most recent common ancestor was used to query the taxonomic information, therefore some leaves in the trees were annotated with only partial taxonomic information.



## Results

### Phylogenetic analysis of MCR sequences

A phylogeny with only putative MCR gene family sequences was created, showing the relationships without additional diversity.
An out-group, 32 canonical sequences, and 54 prevalence sequences were selected for this phylogeny.
The resulting tree in Figure {@fig:canon-prev-tree} shows MCR family members 1 through 9 forming distinct sub-clades in the tree.
MCR-1, MCR-2, and MCR-6 form a closely related clade.
This clade is also closely related to the ICR-Mc clade.
ICR-Mc @JT9eRkR8 is another phosphoethanolamine transferase which confers colistin resistance.
MCR-3, and MCR-7, also form a closely related clade.
![Phylogenetic relationship of 32 canonical (labels prefixed with 'lcl_canon' in yellow), 54 prevalence (labels prefixed with 'lcl_prev' in tan) MCR family sequences, and an outgroup from Betaproteobacteria ('lcl_outgroup' in grey). Each MCR variant is coloured based on its primary numerical value.](images/mcr_canon_prev_full.mintax.svg){#fig:canon-prev-tree}

The relationships were further condensed with a representative for each MCR family member (figure {@fig:canon-prev-tree-collapsed}).
The overall diversity gradient becomes more apparent in this tree.
Regions of the tree vary in their potential to accommodate additional diversity.
Regions containing more evolutionary distance are accommodating to additional diversity, while closely related regions would are not.

![Phylogenetic relationship of 9 representative MCR family sequences, and an outgroup from Betaproteobacteria. (labels prefixed with 'lcl_canon' in yellow are canonical, labels prefixed with 'lcl_prev' in tan are prevalence, and an outgroup from Betaproteobacteria is prefixed with 'lcl_outgroup' in grey)](images/mcr_canon_prev_collapsed.mintax.svg){#fig:canon-prev-tree-collapsed}

The phylogenies represented by Figures {@fig:mcr-3-9}, {@fig:mcr-5-icr}, and {@fig:canon-prev-nrdb-uba-tree} were created with additional diversity by querying the NCBI non-redundant database, and the MAGs from the Parks data @wrBRBdFb.
The filtering criteria in Table 1 were applied to these data sets.

After filtering, 409 NCBI sequence hits, labeled as phosphoethanolamine lipid A transferase, and 104 NCBI sequence hits, labeled as MCR family, were selected for addition to the phylogeny.
The 7903 draft quality MAGs were queried for AMR genes with RGI.
RGI produced 1457246 loose hits, 7171 strict hits, and 310 perfect hits.
After applying filters, only 63 MAG sourced genes were retained for the phylogeny.
Due to the large size, the phylogeny displayed in Figure {@fig:canon-prev-nrdb-uba-tree} was subdivided into Figures {@fig:mcr-3-9}, and {@fig:mcr-5-icr}.
The subdivisions were chosen based on a pruning at the point of the most recent common ancestor of sets of canonical MCR labeled leaves.
The set including MCR-3, MCR-7, and MCR-9, and the set including MCR-1, MCR-2, MCR-5, MCR-6, and ICR-Mc, contained several clades of diversity between some of the canonical and prevalence leaves.
Other choices for leaf sets contained added diversity that was distant from canonical sequences, and were not chosen as a focused figures.



Between the clade containing MCR-3, and the most recent common ancestor of MCR-3 and MCR-7 clades (figure {@fig:mcr-3-9}), there is a clade of sequences from NCBI which have been reported as MCR-3.
Present within this clade is a single result from the Parks dataset @wrBRBdFb, UBA705.
This leaf is labelled as *Aeromonas hydrophilia*, and is associated with rice paddy field-soil microbial fuel cells.
This is present within the clade alone with several other canonical and non-redundant Aeromonadalacea.
*Aeromonas hydrophilia* is a species which has been found to have an MCR-3 gene.

Present between the clade containing MCR 7, and the most recent common ancestor of MCR 3 and MCR 7 clades, is a clade of NCBI sourced phosphoethanolamine lipid A transferase.
This clade consists of the genus of gram negative bacteria, *Aeromonas*, @16EwPCiJT which is sometimes involved in human infection.
This clade also includes an *Aeromonas veronii* hit from epidermal mucus of *Anguilla anguilla* in the Parks data.
Between MCR 9 and the most recent common ancestor of MCR 3 and 9, a clade of Aeromonas associated phosphoethanolamine lipid A transferases appear.
The MCR 9 containing clade contains 8 UBAs and several NCBI non-redundant hits not reported as MCR family genes.
5 Loose hits for MCR in a Leclercia adecarboxylata branch within this clade.
These *Leclercia* branch below the common ancestor of MCR-9 and MCR-3 which are well supported.
The *Leclercia* UBAs were all sampled from New York City MTA subway samples Metagenome.
*Acinetobacter* is another opportunistic pathogen @8uz5m0fP which is becoming resistant to many antimicrobials.

![Clade containing putative MCR3 and MCR 9 clades pruned from Phylogenetic relationship of 32 canonical (labels prefixed with 'lcl_canon'_ in yellow), and 54 prevalence (labels prefixed with 'lcl_prev' in tan) MCR family sequences, 595 NCBI non-redundant sequences (labels prefixed with 'lcl_nrdb' in blue), and 91 UBA sourced sequences (labels prefixed with 'lcl_uba' in green). Each MCR variant is coloured based on its primary numerical value. If the sequence is not reported to be MCR family it is coloured in grey.](images/mcr3_mcr9_diversity.mintax.svg){#fig:mcr-3-9}

Between MCR 5 and ICR-Mc (figure {#fig:mcr-5-icr}), there appear clades of diversity in the genus *Psychrobacter*.
Branching between these two clades, as a descendant to this ancestor, is a clade of *Psycrobacter* species bacteria.
This clade includes several hits from the non-redundant database, and two hits from the UBA data.
According to the Parks @wrBRBdFb data, the identity of these samples are,
UBA3068, A *Psychrobacter sp.*, sampled from Oil polluted marine microbial communities and, UBA4193, a *Psychrobacter sp.*, sampled from the New York City subway.
The quality information for these sequences, shown in Table ??, shows that UBA3068 is near complete, while UBA4193 is only partial.
It is encouraging to see that even with the quality difference, these two sequences branch in the expected clade.
*Psychrobacter* @BjoH1Vii is a Genus is widespread and includes many cold adapted bacteria, it is an opportunistic pathogen, and has been found to sometimes be a cause of infections in humans, animals, and fish. Many new species of *Psychrobacter* have been discovered in cold climates @WLzELTTa. Some of the species have been shown to be resistant to colistin, like *Psychrobacter vallis ps. nov.* and *Psychrobacter aquaticus ps. nov.* @2NZAmp2H and is sister to [TODO: display new tree such that *Acinetobacter* is shown]
Another clade between these two variants contains phosphoethanolamine transferases from the genus *Stenotrophomonas*, including *Stenotrophomonas maltophilia* and *Stenotrophomonas acidaminiphila* which is a multidrug-resistant opportunistic pathogen @Ovca71PG.
Several UBA hits for *Stenotrophomonas maltophilia* show up as shotgun sequencing of environmental samples. [TODO: quality information]


![Clade containing putative MCR 5 and ICR-Mc clades pruned from Phylogenetic relationship of 32 canonical labels (prefixed with 'lcl_canon'_ in yellow), and 54 prevalence (labels prefixed with 'lcl_prev' in tan) MCR family sequences, 595 NCBI non-redundant sequences (labels prefixed with 'lcl_nrdb' in blue), and 91 UBA sourced sequences (labels prefixed with 'lcl_uba' in green). Each MCR variant is coloured based on its primary numerical value. If the sequence is not reported to be MCR family it is coloured in grey.](images/mcr5_icrmc_diversity.mintax.svg){#fig:mcr-5-icr}


[TODO: visualization with plasmid distribution ]


### Phylogenetic analysis of KPC

Using the 18 canonical sequences from Table {@tbl:kpc-variants} as query sequences, 25 prevalence sequences, 376 non-redundant sequences, and 6 UBA sequences were recovered from the various databases. The result was 
combined in the phylogeny displayed in figure {@fig:kpc-tree}.
This phylogeny shows that many of the resulting sequences are distant from the canonical sequences. The main clade in figure {@fig:kpc-main-tree} shows that many of the amr determinants are named as distinct sequences, while not having much phylogenetic distance between them.
The most closely related clade is a clade containing IMI and SME-type beta lactamases.
The remaining sequences are in a clade containing a large amount of class A beta-lactamases from the non-redundant data. All of the UBA sequences were present in this portion of the tree.

![A clade pruned from the phylogeny in figure {#fig:kpc-tree} which represents the most closely related genes to the KPC family genes. 18 canonical labels (prefixed with 'lcl_canon'_ in yellow), and 25 prevalence (labels prefixed with 'lcl_prev' in tan), and 28 NCBI non-redundant sequences (labels prefixed with 'lcl_nrdb' in blue). Each KPC variant is coloured based on its primary numerical value. If the sequence is not reported to be KPC family it is coloured in grey.](images/kpc_main_clade.mintax.svg){#fig:kpc-main-tree}


### Phylogenetic analysis of NDM

14 canonical sequences were used to query the data for NDM beta-lactamase.
The genes retained for the phylogeny were 14 canonical sequences, 8 prevalence sequences, 12 non-redundant sequences, 1 UBA sequence, and an out-group.
This resulted in the phylogenetic relationship in Figure {@fig:ndm-tree}.

![Phylogenetic relationship of 14 canonical (labels prefixed with 'lcl_canon' in yellow), 8 prevalence (labels prefixed with 'lcl_prev' in tan), 12 NCBI non-redundant database sequences (labeled as 'lcl_nrdb' in blue), 1 UBA sequence (labeled as 'lcl_uba' in green), and an outgroup from Betaproteobacteria (labeled as 'lcl_outgroup' in grey). Each NDM variant is coloured based on its primary numerical value.](images/ndm_full.mintax.svg){#fig:ndm-tree-all}

The 12 sequences resulting from the NCBI data included 3 genes reported to be NDM-1, NDM-3, and NDM-5, while the other 4 genes were reported to be general beta lactamase/carbapenemase hits.
As in the KPC phylogeny (figure {@fig:kpc-main-tree}), there is very little phylogenetic difference between the named variants of NDM.
The only phylogenetically distinct genes in this clade were the prevalence hit for NDM-1, and the ncbi hits labeled as NDM-1 and NDM-5.
The naming of these sequences seem not to be congruent with the phylogenetic relationships present in the tree.
Some of the NDM-1 and NDM-5 genes are more closely related to the other NDM variants than themselves.
One BLAST result from the Parks data branches far from the clade containing the canonical sequences.
This indicates that under the coverage queried, there are no reasonably detectable NDM homologues in the UBA data.
The alignment of this UBA under this relaxed query coverage of 60% (see Table 1) is questionable.
Reducing query coverage further could produce more sequences from the Parks data, but the resulting alignment would produce a meaningless phylogeny.

### Phylogenetic analysis of OXA-48

In querying for the OXA-48 portion of the analysis, multiple BLAST results for UBA sequences were found, but the hits were too phylogenetically dissimilar to draw a conjecture about their relationship to the OXA family. 6 canonical sequences, and the 14 prevalence sequences, and 20 non-redundant sequences are combined in the phylogeny in Figure {@fig:oxa-tree}

![The main phylogenetic relationship pruned from the tree inferred from OXA-48-like sequences from figure {#fig:oxa-tree}. 6 canonical (labels prefixed with 'lcl_canon'_ in yellow), and 14 prevalence (labels prefixed with 'lcl_prev' in tan), 20 NCBI non-redundant sequences (labels prefixed with 'lcl_nrdb' in blue). Each OXA-48 variant is coloured based on its primary numerical value. If the sequence is not reported to be OXA-48 family it is coloured in grey.](images/oxa_main_clade.mintax.svg){#fig:oxa-main-tree}

The OXA-48 prevalence hits added further diversity to the reference OXA-48-like sequences. OXA-436 @KEhNzdys was found, clustered with no other gene, in the prevalence data, and OXA-514 and OXA-515 were found in the non-redundant data. Much like in NDM, this diversity seems only to be diversity in name. The various named variants are too similar to produce significant phylogenetic resolution.


## Discussion

### Part 1: An expanded set of candidate resistance genes

The aim of this study was to use the phylogenetic relationships of AMR genes to expand on current AMR surveillance efforts of CARD.
Homologous sequences from NCBI, CARD prevalence data, and a large set of MAGs, were queried, filtered, and added to phylogenies.
Most hits for these queries were not worth retaining.
One reason for this is that many sequences were closley related to each other, clustering into a single representative sequence.
Investigating, for example, a single change in amino acid, would not be condicive to this sort of overview.
The other reason many sequences were not retained is that they lacked sufficient query coverage to produce a good sequence alignment.
This was most evident in the UBA data. Many of the UBA sequences were filtered out becasuse they were only partial matches.

One further problem with the UBA data is that hits that did pass the filtering criteria did not seem to be homologous to the canonical sequences.
Loose RGI matches in the MAGs for MCR, NDM, KPC, and OXA-48 were examined, but after applying conservative filtering criteria, only the MCR survey produced matches which would be worthy of further consideration for resistance testing.
This contradistinction between the MCR analysis and the beta lactamase analyses could be explained by plasmid distributions.
Plasmids could have been poorly recovered in the assembly phase of the SRA experiments.
These experiments were performed with high-throughput sequencing, many using Illumina HiSeq 2000 and 2500, which produce short reads.
Plasmids from short reads are known to be difficult to assemble due to sequence characteristics [@12zFifp5x] [@12zFifp5x] [@DTtDOvle].

### Part 2: Phylogenetic poositioning of AMR genes from NCBI and MAGs

Another way in which the analyses of MCR and the beta lactamases differ is in the spread and diversity of the relationships.
In addition to MAG sources, which are completely lacking in the beta lactamase trees, the MCR tree contains several sequences from NCBI’s non-redundant database which land close to canonical clades.
There are several clades made up of canonical and prevalence sequence genes separated by swathes of diversity from both NCBI and the MAGs.
This suggests that there could be more diversity to be found within the MCR class.
In contrast, the added diversity in phylogenies from OXA-48, KPC is distant from the canonical and prevalence sequences.
The matches which are close, are nearly identical to the canonical and prevalence sequences.The beta-lactamase phylogenies are low in gene diversity, and thus form very tight, closely related clades.
This displays that this study is very sensitive to the diversity of the gene being studied, whether it be from bias in sampling, or high amount of genetic conservation in the gene pool.

### Part 3: Phylogenetic relationships vs. nomenclature

In assessing the value of the relationships present in these more tightly related phylogenies, it is surprising that the literature has produced so many named variants.
In the tree for NDM, we have named variants numbered from NDM 1 to NDM 14, yet most of the tree would be more appropriately displayed with multifurcating nodes.
There are fifteen named variants, but there are only three weakly distinct clades, and little bootstrap support (TODO: look at SNPs put this in results?).
The most divergent NDM sequence is a prevalence sequence which is labelled as NDM-1, yet is more distant from other homologs named NDM-1 than other NDM-1 genes.
The criteria for naming these genes seem to be completely arbitrary. Similarly, KPC is very tightly related and some of the same arguments could be made for classification of these sequences.
In the tree for OXA-48 like genes, we see more diversity, with branches of more support.
The tree forms few tightly related clades, and allows some diversity from NCBI to be added to the tree.
The OXA group, as a whole, is very diverse, but only because they are classified phenotypically.
If the OXA were more thoroughly separated into actual homologous groups, perhaps we would see more diversity added to the group, and perhaps even from metagenomic data.
These groups of OXA could behave very differently and some could have data recovery similar to that of MCR, but we are missing out on this because of the phenotypic naming scheme over a rigorous scheme which takes into account the genetic similarity. In MCR, the naming situation is less arbitrary. The closely related variants are classified under the same primary number.
Several versions of MCR-1 exist, for example, and all form a clade.

### Part 4: Should naming reflext phylogenetic relationships?

Finding an ideal nomenclature scheme which within, or generalizing across AMR families is problematic.
Nomenclature which has been shown to be phylogenetically consistent, such as that of MCR, is nonetheless subject to ambiguity.
Researchers have suggested, for example for MCR [@x2VQlvOO], using amino acid sequence identity differences rather than possibly trivial nucleotide differences, but this still subject to ambiguity in cutoff of percent identity.
Fixed cutoffs of 2% have been suggested by some researchers[@eGJmNg9p], but an ideal cutoff for one gene family, may not be ideal for the next.
One could argue that the genomic and evolutionary context should be also considered in the nomenclature [@EhIOtkvv].
It has been suggested, for example that mobilized, and chromosomal genes differ in their evolutionary variance [@EhIOtkvv].
In addition, the current study demonstrates that the diversity and spread varies between gene families.
It can be seen that it would be more likely that one may discover, for example, a new MCR family member than a new NDM family member.
Justifying naming of a new NDM gene, when all genes available to the public are essentially identical, seems to be problematic, however, further investigations into certain patterns of changes in the amino acid sequences may further granularize our classification.
Ultimately, many interesting questions about the nomenclature of these genes are rooted in ontology.
Classifying these genes is of utmost importance for communication between scientists, and a naming scheme which seeks a balance between practicality, evolutionary relationships, function, and context, must be found.


## Conclusion

* The data for three of the four phylogenetic analyses were not ideal for expanding on the known diversity of AMR homologs. These beta lactamase phylogenies did, however show the importance of unambiguous naming schemes, and care when it comes to presenting data honestly. 
* The study also showed that it is important to take the type of data into consideration, and metagenomic sequencing must come a long way before these studies can produce quality information.
* MCR is a good candidate for this type of study because it has the right balance of homology and diversity in the group, and is an example of a better naming scheme.


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