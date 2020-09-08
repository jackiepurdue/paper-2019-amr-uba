---
author-meta:
- Jackie Purdue
- Jocelyn McDonald
- Dayna Mikkelsen
- Finlay Maguire
- Robert G. Beiko
date-meta: '2020-09-08'
keywords:
- metagenome
- antimicrobial resistance
lang: en-CA
title: Reviewing the phylogenetic relationships and nomenclature of common antimicrobial
  resistance genes
...






<small><em>
This manuscript
([permalink](https://jackiepurdue.github.io/phylogenetic-amr-survey-manuscript/v/0dc9fd5b3b312be66e6979bccaffea72024082e0/))
was automatically generated
from [jackiepurdue/phylogenetic-amr-survey-manuscript@0dc9fd5](https://github.com/jackiepurdue/phylogenetic-amr-survey-manuscript/tree/0dc9fd5b3b312be66e6979bccaffea72024082e0)
on September 8, 2020.
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
Phylogenetic investigations of the evolution and transmission of antimicrobial resistance determinants can be used to guide and prioritize experimental molecular studies.
A systematic way of classifying AMR gene variants is important in comparing these phylogenetic relationships.
In this study, the phylogenetic neighborhoods of several named AMR genes are examined for diversity, spread, and consistency in classification.
Canonical genes which are associated with mobilizable, last-line antibiotics were chosen from the Comprehensive Antibiotic Resistance Database (CARD) to query CARD prevalence data, NCBI sequence data, and draft quality metagenome assembled genomes (MAGs) from various uncultivated bacterial and archeal sources (UBAs).
These genes included mobile colistin resistance (MCR), New Delhi beta-lactamase (NDM), Klebsiella pneumoniae carbapenemase (KPC), and OXA-48 beta-lactamase lactamase family.
A phylogeny of this expanded set of candidate resistance genes was produced with a limited amount of new diversity in the beta-lactamase analyses, and several possibly novel clades of diversity in MCR.
The beta-lactamase families were found to be more tightly defined, with most added diversity being either extremely close, or phylogenetically distant.
The MCR family showed many new clades of diversity within canonical clades.
In this phylogenetic context, some of the names of the genes were found to be inconsistent or inconsequential.


## Introduction

Antimicrobials, substances which can kill or inhibit the growth of microbes [@Zvf1VhKR], are key effectors in the ecology of microorganisms.
The evolution of resistance to these substances, known as antimicrobial resistance (AMR), is an important and ancient process [@2xaXclNM].
In the last century we have adopted and used antimicrobials to great effect in clinical medicine and agriculture.
However, the use and abuse of antimicrobials has led to increasing levels of observed AMR [@1ByMfX8Y1].
This poses a growing global health risk by undermining our ability to treat infectious diseases and perform surgeries [@kDtOJsGI].
Infections by resistant microbes have greater associated mortality and morbidity [@kDtOJsGI] with the European Centre for Disease Prevention and Control estimating that 25,000 people per year die due to AMR [@OLzrpsK4].

AMR can be intrinsic, or can arise through mutation and lateral gene transfer [@2xaXclNM, @17atLROlI].
These mechanisms allow for the constant change of the resistome, making determining the scope of AMR within both pathogenic and non-pathogenic bacteria difficult [@1ByMfX8Y1].
Pathogens have acquired the ability to inactivate antibiotics, such as beta-lactamase prodution[@10gL2CtXW], but have also acquired the ability to modify target sites of antibiotics, and to regulate outer membrane proteins which would cause susceptibility to antibiotics[@bODq6dmJ].
To mitigate the spread of AMR the World Health Organization (WHO) created an action plan which emphasizes the need to strengthen our understanding and surveillance of AMR. 
An important aspect of this research is to examine the spread of AMR between environmental and clinical samples (https://www.who.int/antimicrobial-resistance/global-action-plan/en/).
One way to try to understand the evolution and spread of AMR is to perform large-scale evolutionary analyses with samples from lots of different environments/contexts. Phylogenetic and phylodynamics are the key component of a lot of this work.
Some of the most critical pathogens are the multi-drug resistant "ESKAPE" pathogens: _Enterococcus faecium_, _Staphylococcus aureus_, _Klebsiella pneumoniae_, _Acinetobacter baumannii_, _Pseudomonas aeruginosa_, and _Enterobacter_ spp. [@bODq6dmJ,@b2c0QSMI].
These pathogens are also a subset of the WHO's priority list of organisms, (https://www.who.int/medicines/publications/global-priority-list-antibiotic-resistant-bacteria/en/), and deemed to be high priority pathogens [@aMfsvHsj]  [https://www.who.int/medicines/publications/WHO-PPL-Short_Summary_25Feb-ET_NM_WHO.pdf?ua=1]. They have become resistant to several antibiotics, including carbapenems, several of which are last line defense antibiotics [@oR3fXrzb].
Treatment of these resistant pathogens is constrained to relatively few drugs.
Vancomycin, non-carbapenem beta-lactams, beta-lactamase inhibitors, and cephalosporins are all used heavily for treating many of these infections (https://library.nshealth.ca/ld.php?content_id=34828434, https://library.nshealth.ca/ld.php?content_id=34879080)
Carbapenems are broad spectrum beta-lactam antibiotics typically used to treat life threatening, high risk, and multi-drug resistant bacterial infections. 
Beta-lactamase producing bacteria have difficulty degrading carbapenems when combined with beta-lactamase inhibitors making them effective treatments against pathogens with multi-drug resistance [@OLzrpsK4].
The Canadian Nosocomial Infection Surveillance Program has shown that there has has been a recent emergence of resistance to carbapenamases in a subset of these ESKAPE pathogens, presenting a new threat to public health (https://www.canada.ca/en/public-health/services/publications/science-research-data/summary-report-healthcare-associated-infection-antimicrobial-resistance-antimicrobial-use-surveillance-data-2013-2017.html).
One way microbes can develop carbapenem resistance is through the acquisition of carbapenamase genes. [@OLzrpsK4].
Three common carbapenamase gene families of concern, each belonging to a class of carbapenemases, are _Klebsiella pneumoniae_ carbapenamase (KPC), New Delhi metallo-beta-lactamase (NDM), and OXA-48 type beta-lactamases [@OLzrpsK4], and each belong to a class of carbapenamases.

Carbapenamases are assigned to one of four classes (A-D) based on their molecular structure [@16ZzmUN7q].
Class A, C, and D use a serine residue to hydrolyze beta-lactam antibiotics [@2p1n2mr5].
KPC genes are a part of class A, and are the most prevalent in that class [@OLzrpsK4]. 
Many variants of KPC are spreading and being discovered, however carbapenamases within this class are more rare than those within classes B, C, and D [@OLzrpsK4].
Class B beta-lactamases are metallo-enzymes that use a zinc active site to hydrolyze beta-lactam antibiotics. 
The NDM gene is classified as a class B beta-lactamase [@OLzrpsK4], and is the most prevalent in that class [@OLzrpsK4].
When pathogens become resistant to carbapenems, a common last line of defense is the polymyxin E (colistin) and B antibiotics.
Polymyxins act via disrupting membrane permeability [@17k3PVuIy].
Colistin happens to be effective against many, but not all, priority and "ESKAPE" pathogens.
Colistin is limited to a last line defense against carbapenem resistant infections due to its neurotoxic and nephrotoxic effects [@17k3PVuIy].
Despite its limited use to date, mobilized colistin resistance (MCR) has already been discovered [@vQTzfitx].

Class D contains the OXA-48 beta-lactamases which are the most prevalent in that class [@OLzrpsK4]. 
Unlike KPC and NDM, the OXA family is characterized by phenotype rather than genotype. 
This family is characterized by specific hydrolases that can hydrolyze oxacillin and cloxacillin, with the enzyme being poorly inhibited by clavulanic acid (https://card.mcmaster.ca/ontology/36026).
This results in relatively few homology relationships within the family.
A subset of this family, OXA-48 possesses carbapenem hydrolyzing activity [@UV1QqTS8].
The OXA-48 subfamily consists of five variants: OXA-48, OXA-162, OXA-163, OXA-181, OXA-204, and OXA-232 [@FqGNAObZ].

Due to the emergence of resistance to many last-line antibiotics, it is important to characterize the total diversity and spread of these key resistance determinants. However, to perform these types of analyses we need two resources: a clear consolidated definition of what constitutes an AMR-related gene and a large amount of sequenced microbial genomes.

Naming and defining AMR genes is difficult due to the legacy names, pre-DNA sequencing technology, and the large number of different researchers and stakeholders involved in AMR such as government organizations, human health, animal health, and agri-food industries [https://www.canada.ca/en/health-canada/services/publications/drugs-health-products/federal-action-plan-antimicrobial-resistance-canada.html].
AMR determinants are typically classified into families [@nvbyXyPe], some of which are based on phenotypic properties, and some based on sequence variation.
The nomenclature is usually an acronym with varying representations, such as the mechanism of resistance, the organism it is associated with, or the molecular structre.
Each acronym is assigned a numerical value to distinguish variants.
Each sequence, determined to be novel by some criterion, is assigned a new number.
For example, the MCR phosphoethanolamine transferase gene family inhibits the binding of colistin to the cell membrane.
The MCR-3 gene has a sequence identity which has been deemed to be significantly different than that of the other MCR genes in the family.
MCR-3.1, has been deemed to be a variant of the MCR-3 gene, which has a slight variation in gene sequence from other MCR-3 genes[@x2VQlvOO].
Members of the NDM beta-lactamase gene family are named using a different set of criteria
In this case, NDM-1, and NDM-2 differ only by a single amino acid substitution.
This system for classification has the potential to be misleading when conducting AMR research.
The amount of diversity encompassed within different names and alleles is hugely variable across AMR genes.
For example, NDM has little diversity, while MCR has a large amount of  sequenced microbial genomes.
Some AMR families are not even defined on the basis of sequence space but phenotypically.
An example of this is the OXA beta-lactamase family, which is is a phenotypically characterized family, with several different homologous sets of genes.
OXA-20 has less than 20% amino acid sequence identity when compared with several other OXA-48 family beta-lactamases [@1AFSAuSwx].
This is a problem when attempting to characterize the AMR determinants by sequence similarity.

High-quality manually curated AMR databases such as the Comprehensive Antibiotic Resistance Database (CARD) [@nvbyXyPe] provide a unified resource for the definition, nomenclature and classification of AMR genes.
CARD organizes this information through the Antibiotic Resistance Ontology (ARO), a controlled vocabulary with defined relationships.
There are two datasets within CARD, CARD:*Canonical* and CARD:*Prevalence*.
*Canonical* is a conservative set of AMR genes and mutations that have been experimentally verified as being associated with resistance in a peer-reviewed publication.
As a consequence, most of the entries in CARD:*Canonical* are derived from the most intensively studied organisms, such as the *"ESKAPE"* pathogens.
On the other hand, CARD:*Prevalence* contains AMR sequences that have been detected by searching a broader set of WHO priority organism genomes from repositories such as National Center for Biotechnology Information (NCBI) for sequences similar to *canonical* sequences.
This database is meant to represent the diversity of all current sequence data available to the public.
This _in silico_ search is performed using CARD's BLAST-based Resistance Gene Identifier (RGI) tool and greatly increases the sequence diversity in CARD [@nvbyXyPe].

However, this is still limited to a subset of all genomes currently available in central repositories like NCBI.
If we want to thoroughly understand the evolution and spread of AMR genes we need to analyse as many genomes as possible.
Unfortunately, the genomes in databases are largely sequenced from microbes that can be easily cultured. 
As only a subset of microbial diversity can be cultured, this means many of our existing genomes aren't necessarily representative of the environment from which they were sampled  [@wapKbEHA].
Recently, techniques have been developed that allow the recovery of genomes from metagenomic data e.g. [@DTtDOvle,@DfIRBmdF].
As metagenomic sequencing, the direct sequencing of all DNA in a sample, doesn't require culturing these metagenome-assembled genomes (MAGs) represent a huge source of novel microbial diversity.
Parks et. al. [@wapKbEHA], generated new 7,903 bacterial and archaeal (Uncultured Bacteria and Archaea; UBA) MAGs representing >30% increase in the sampled phylogenetic diversity of the bacteria and archaea.

Identifying and phylogenetically analysing key carbapenem and colistin resistance genes in this dataset, CARD:*Prevalence* and NCBI non-redundant data, could greatly improve AMR surveillance of these genes.
We would characterize previously unseen diversity in genomes not yet analyzed for AMR, and provide insights into the diversity of AMR across non-clinical samples. This could inform our understanding of the transmission of these mobile critical AMR genes and help refine the nomenclature of this ever-expanding dataset. Therefore, in this work we present a critical investigation of the classification consistency and novelty of genomes and MAGs of KPC, NDM, OXA-48, and MCR across all currently sequenced genomes.


## Methods

### Data

We surveyed four separate databases to assess the diversity of known and candidate AMR genes.
These sources include CARD canonical and prevalence (version 3.0.5) sequences for the AMR genes under study, and associated homologs from NCBI non-redundant data and metagenomic data.
The 32 canonical MCR sequence variants (table {@tbl:mcr-variants}), 18 canonical KPC sequence variants (table {@tbl:kpc-variants}), 14 canonical NDM sequence variants (table {@tbl:ndm-variants}), and 6 canonical OXA-48-like sequence variants(table {@tbl:oxa-variants}), as labeled in the CARD database, were obtained as a reference. The AMR prevalence data was derived from CARD Prevalence 3.0.5. 
The NCBI non-redundant data consisted of all non-redundant GenBank, Protein Data Bank (PDB), SwissProt, Protein information resource (PIR), Protein research foundation (PRF) data from May 17, 2019.
The metagenomic data came from a data-set of 7903 draft quality MAGs which were recovered from the Sequence Read Archive by Parks [@wrBRBdFb]. These genomes were chosen specifically because they were likely to be from lineages which were under-sampled, environmental and non-human gastrointestinal samples being the main focus.

### Querying the data

The CARD canonical sequences from each family were used to perform a multiple query BLASTP (version 2.5.0 [@s9ycaHcq]) against the prevalence BLAST database with an e-value threshold and query coverages shown in table 1. 
Many of the sequences are nearly identical, thus they were further processed by clustering with CD-HIT version 4.8.1 at a minimum sequence identity as per table 1.

The reference CARD canonical sequences were also used to perform a multiple query BLASTP against the NCBI non-redundant database with an e-value and query coverage threshold indicated in table 1
There are many highly sampled taxa and genes in the non-redundant database. 
To balance the distribution, and reduce the size of the non-redundant sequence set, CD-HIT version 4.8.1 was also used to cluster the data as per table 1.

For the metagenomic data, RGI version 5.0 with CARD database version 3.02 [@1ByMfX8Y1] was run on the contigs of the 7903 MAGs with the inclusion of loose, perfect, and strict hits.
The search strings in table s1 were used to extract results from the RGI output.
The CARD canonical sequences were used to perform a multiple query BLASTP against this UBA blast database with a e-value threshold and query coverage from table 1.
The minimum BLAST query coverages were chosen to produce meaningful alignments.

For all sequence variants obtained from each data source, redundant results for the prevalence, NCBI, and UBA queries were filtered from these BLASTP results by retrieving only the longest sequence for each unique Subject Taxonomy ID. 

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
    <th class="tg-yj5y" colspan="3">Maximum BLAST<br>e-value<br></th>
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
    <td class="tg-0lax" colspan="10"><b>table 1</b>: Parameters used with BLAST and CD-HIT to obtain sequences for the phylogenies<br>of MCR phosphoethanolamine transferase, and KPC, NDM, and OXA beta-lactamases.<br>For each determinant, the minimum BLAST e-values, minimum query coverages, and CD-HIT Sequence Identity <br>threshold for clustering sequences are displayed for each database.<br>CARD represents the RGI-CARD prevalence sequence data, NCBI represents the NCBI non-redundant sequence<br>data, and Parks represents the MAG data source.<br><br>After filtering, OXA did not have an overabundance of close sequences and was not clustered (marked as N/A)<br></td>
  </tr>
</tbody>
</table>
Table: Names of the canonical MCR phosphoethanolamine transferase variants from CARD database {#tbl:params}

### Sequence Alignment

Two alignments were created for each AMR determinant under study.
The first alignment was created to compare the phylogenetic relationship of the canonical and prevalence (putaive) sequences.
The second alignment was created for an comparison of sequences from all four databases.

The putative AMR alignment was made up of the sequences from the CARD prevalence data were combined in one multi-FASTA format file with the canonical sequences and an outgroup chosen for each AMR family as per table ?? [TODO: make a table of outgroups in supplemental]. 
In the second, more diverse alignment, The filtered sequences from NCBI non-redundant data, CARD prevalence data, UBA data were all combined into one multi-FASTA format file with the canonical sequences with the same outgroup sequences (table ??).

This set of combined amino acid sequences were aligned with MAFFT-LINSI [@1DMuBNrog] version 7.40 and trimmed by trimal [@GCsU1nyf] version 1.4.rev22 using the automated1 option.

### Creation of phylogenies

For each alignment under each AMR family under study, IQ-TREE multicore version 1.6.9 [@JOWSuu8G] was used to build a bootstrapped tree with -bb 1000 with the G+I+G4 model of substitution. 
Tree visualizations were created with ETE Toolkit [@5F7ii9Ji] version 3.
The trees were annotated with taxonomic information for each rank by using ETE’s NCBI taxonomy module to translate the names result set from the various databases to taxonomic identifiers.
The taxonomic identifier was used to query NCBI's taxonomy database from May 17, 2019, for the taxonomy information.
In cases where there were multiple hits for genes, the most recent common ancestor was used to query the taxonomic information, therefore some leaves in the trees were annotated with only partial taxonomic information.



## Results

### Phylogenetic analysis of MCR sequences

A phylogeny with only CARD:Canonical and CARD:Prevalence MCR gene family sequences was created, showing the relationships without diversity from NCBI or the MAGs, including an out-group, 32 canonical sequences, and 54 prevalence sequences.
The resulting tree in Figure {@fig:canon-prev-tree} shows MCR family members 1 through 9 forming distinct sub-clades in the tree.
MCR-1, MCR-2, and MCR-6 form a closely related clade.
This clade is closely related to ICR-Mc [@JT9eRkR8], another phosphoethanolamine transferase which confers colistin resistance.
MCR-3 and MCR-7, also form a closely related clade.

![Phylogenetic relationship of 32 canonical (labels prefixed with 'lcl_canon' in yellow), 54 prevalence (labels prefixed with 'lcl_prev' in tan) MCR family sequences, and an outgroup from Betaproteobacteria ('lcl_outgroup' in grey). Each MCR variant is coloured based on its allele number.](images/mcr_canon_prev_full.mintax.svg){#fig:canon-prev-tree}
The tree visualisation was further condensed to only a single representative for each MCR allele (figure {@fig:canon-prev-tree-collapsed}).
Regions of the tree vary in their potential to accept additional diversity.
Some clades are tightly related, while others have more distance between them.
Newly discovered genes could some day be found to be sister to these more distantly related clades.
Regions containing more evolutionary distance are accommodating to additional diversity, while closely related regions are not.

![Phylogenetic relationship of 9 representative MCR family sequences, and an outgroup from Betaproteobacteria. (labels prefixed with 'lcl_canon' in yellow are canonical, labels prefixed with 'lcl_prev' in tan are prevalence, and an outgroup from Betaproteobacteria is prefixed with 'lcl_outgroup' in grey)](images/mcr_canon_prev_collapsed.mintax.svg){#fig:canon-prev-tree-collapsed}

The phylogenies represented by Figures {@fig:mcr-3-9}, {@fig:mcr-5-icr}, and {@fig:canon-prev-nrdb-uba-tree} were created with additional diversity by querying the NCBI non-redundant database, and the MAGs from the Parks data [@wrBRBdFb].
The filtering criteria in Table 1 were applied to these data sets.

After filtering, 409 NCBI sequence hits, labeled as phosphoethanolamine lipid A transferase, and 104 NCBI sequence hits, labeled as MCR family, were selected for addition to the phylogeny.
The 7903 draft quality MAGs were queried for AMR genes with RGI.
RGI produced 1457246 loose hits, 7171 strict hits, and 310 perfect hits.
After applying the filters from Table 1, only 63 MAG derived genes were retained for the phylogeny.
Due to the large size, the phylogeny displayed in Figure {@fig:canon-prev-nrdb-uba-tree} was subdivided into Figures {@fig:mcr-3-9}, and {@fig:mcr-5-icr}.
The subdivisions were chosen based on a pruning at the point of the most recent common ancestor of sets of canonical MCR labeled leaves.
The set including MCR-3, MCR-7, and MCR-9, and the set including MCR-1, MCR-2, MCR-5, MCR-6, and ICR-Mc, contained several clades sister to some of the canonical and prevalence leaves.
Other choices for leaf sets contained added diversity that was distant from canonical sequences, and were not chosen as a focused figures.

Sister to the canonical MCR-3 sequences, and the most recent common ancestor of MCR-3 and MCR-7 clades (figure {@fig:mcr-3-9}), there is a clade of sequences from NCBI which have been reported as MCR-3.
Present within this clade is a single result from the Parks dataset [@wrBRBdFb], UBA705.
This leaf is labelled as *Aeromonas hydrophila*, and is associated with rice paddy field-soil microbial fuel cells.
This is present within the clade alone with several other canonical and non-redundant *Aeromonas*.
*A. hydrophila* is a species which has been found to have an MCR-3 gene.

Sister to the clade containing MCR 7, and the most recent common ancestor of MCR 3 and MCR 7 clades, is a clade of NCBI sourced phosphoethanolamine lipid A transferase.
This clade consists of the genus of Gram-negative bacteria, *Aeromonas*, [@16EwPCiJT] which is sometimes involved in human infection.
This clade also includes an *A. veronii* hit from epidermal mucus of *Anguilla anguilla* in the Parks data.
Sister to the MCR 9 clade and the most recent common ancestor of MCR 3 and 9, a clade of *Aeromonas* associated phosphoethanolamine lipid A transferases appear.
The MCR 9 containing clade contains 8 UBAs and several NCBI non-redundant hits not reported as MCR family genes.
5 Loose hits for MCR in a *Leclercia adecarboxylata* branch within this clade.
These *Leclercia* branch as a sister to the common ancestor of MCR-9 and MCR-3 which are well supported.
The *Leclercia* UBAs were all sampled from New York City MTA subway.
*Acinetobacter* is another opportunistic pathogen [@8uz5m0fP] which is becoming resistant to many antimicrobials.

![Clade containing putative MCR3 and MCR 9 clades pruned from phylogenetic relationship of 32 canonical (labels prefixed with 'lcl_canon'_ in yellow), and 54 prevalence (labels prefixed with 'lcl_prev' in tan) MCR family sequences, 595 NCBI non-redundant sequences (labels prefixed with 'lcl_nrdb' in blue), and 91 UBA sourced sequences (labels prefixed with 'lcl_uba' in green). Each MCR variant is coloured based on its allele number. If the sequence is not reported to be MCR family it is coloured in grey.](images/mcr3_mcr9_diversity.mintax.svg){#fig:mcr-3-9}

Sister to the MCR 5 and ICR-Mc clades (figure {#fig:mcr-5mayb-icr}), there appear clades of diversity in the genus *Psychrobacter*.
A descendant to this ancestor, is a clade of *Psycrobacter* species bacteria.

This clade includes several hits from the non-redundant database, and two hits from the UBA data.
According to the Parks [@wrBRBdFb] data, the identity of these samples are,
UBA3068, A *Psychrobacter sp.*, sampled from Oil polluted marine microbial communities and, UBA4193, a *Psychrobacter sp.*, sampled from the New York City subway.
The quality information for these sequences, shown in table ?? [TODO: do we need a table with quality information], shows that UBA3068 is near complete, while UBA4193 is only partial.
It is encouraging to see that even with the quality difference, these two sequences branch in the expected clade.
*Psychrobacter* [@BjoH1Vii] is a widespread genus and includes many cold adapted bacteria, it is an opportunistic pathogen, and has been found to sometimes be a cause of infections in humans, animals, and fish. Many new species of *Psychrobacter* have been discovered in cold climates [@WLzELTTa].
Some of the species have been shown to be resistant to colistin, like *P. vallis ps. nov.* and *P. aquaticus ps. nov.* [@2NZAmp2H] and is sister to [TODO: display new tree such that *Acinetobacter* is shown]
Another clade sister to hese two variants contains phosphoethanolamine transferases from the genus *Stenotrophomonas*, including *S. maltophilia* and *S. acidaminiphila* which is a multidrug-resistant opportunistic pathogen [@Ovca71PG].
Several UBA hits for *S. maltophilia* show up as shotgun sequencing of environmental samples. [TODO: quality information]

![Clade containing putative MCR 5 and ICR-Mc clades pruned from phylogenetic relationship of 32 canonical labels (prefixed with 'lcl_canon'_ in yellow), and 54 prevalence (labels prefixed with 'lcl_prev' in tan) MCR family sequences, 595 NCBI non-redundant sequences (labels prefixed with 'lcl_nrdb' in blue), and 91 UBA sourced sequences (labels prefixed with 'lcl_uba' in green). Each MCR variant is coloured based on its allele number. If the sequence is not reported to be MCR family it is coloured in grey.](images/mcr5_icrmc_diversity.mintax.svg){#fig:mcr-5-icr}

### Phylogenetic analysis of KPC

Using the 18 canonical sequences from Table {@tbl:kpc-variants} as query sequences, 25 prevalence sequences, 376 non-redundant sequences, and 6 UBA sequences were recovered from the various databases. The result was 
combined in the phylogeny displayed in figure {@fig:kpc-tree}.
This phylogeny shows that many of the resulting sequences are distant from the canonical sequences. The main clade in figure {@fig:kpc-main-tree} shows that many of the AMR determinants are named as distinct sequences, while not having much phylogenetic distance between them.
The most closely related clade is a clade containing IMI and SME-type beta-lactamases.
The remaining sequences are in a clade containing a large amount of class A beta-lactamases from the non-redundant data. All of the UBA sequences were present in this portion of the tree.

![A clade pruned from the phylogeny in figure {#fig:kpc-tree} which represents the most closely related genes to the KPC family genes. 18 canonical labels (prefixed with 'lcl_canon'_ in yellow), and 25 prevalence (labels prefixed with 'lcl_prev' in tan), and 28 NCBI non-redundant sequences (labels prefixed with 'lcl_nrdb' in blue). Each KPC variant is coloured based on its allele number. If the sequence is not reported to be KPC family it is coloured in grey.](images/kpc_main_clade.mintax.svg){#fig:kpc-main-tree}


### Phylogenetic analysis of NDM

14 canonical sequences were used to query the data for NDM beta-lactamase.
The genes retained for the phylogeny were 14 canonical sequences, 8 prevalence sequences, 12 non-redundant sequences, 1 UBA sequence, and an out-group.
This resulted in the phylogenetic relationship in Figure {@fig:ndm-tree}.

![Phylogenetic relationship of The NDM genes with 14 canonical (labels prefixed with 'lcl_canon' in yellow), 8 prevalence (labels prefixed with 'lcl_prev' in tan), 12 NCBI non-redundant database sequences (labeled as 'lcl_nrdb' in blue), 1 UBA sequence (labeled as 'lcl_uba' in green), and an outgroup from Betaproteobacteria (labeled as 'lcl_outgroup' in grey). Each NDM variant is coloured based on its allele number.](images/ndm_full.mintax.svg){#fig:ndm-tree-all}

The 12 sequences resulting from the NCBI data included 3 genes reported to be NDM-1, NDM-3, and NDM-5, while the other 4 genes were reported to be general beta-lactamase/carbapenemase hits.
As in the KPC phylogeny (figure {@fig:kpc-main-tree}), there is very little phylogenetic difference between the named variants of NDM.
The only phylogenetically distinct genes in this clade were the prevalence hit for NDM-1, and the NCBI hits labeled as NDM-1 and NDM-5.
The naming of these sequences seem not to be congruent with the phylogenetic relationships present in the tree.
Some of the NDM-1 and NDM-5 genes are more closely related to the other NDM variants than themselves.
One BLAST result from the Parks data branches far from the clade containing the canonical sequences.
This indicates that under the coverage queried, there are no reasonably detectable NDM homologues in the UBA data.
The alignment of this UBA under this relaxed query coverage of 60% (see Table 1) is questionable.
Reducing query coverage further could produce more sequences from the Parks data, but the resulting alignment would produce a meaningless phylogeny.

### Phylogenetic analysis of OXA-48

In querying for the OXA-48 portion of the analysis, multiple BLAST results for UBA sequences were found, but the hits were too phylogenetically dissimilar to draw a conjecture about their relationship to the OXA family. 6 canonical sequences, and the 14 prevalence sequences, and 20 non-redundant sequences are combined in the phylogeny in Figure {@fig:oxa-tree}

![The main phylogenetic relationship pruned from the tree inferred from OXA-48-like sequences from figure {#fig:oxa-tree}. 6 canonical (labels prefixed with 'lcl_canon'_ in yellow), and 14 prevalence (labels prefixed with 'lcl_prev' in tan), 20 NCBI non-redundant sequences (labels prefixed with 'lcl_nrdb' in blue). Each OXA-48 variant is coloured based on its allele number. If the sequence is not reported to be OXA-48 family it is coloured in grey.](images/oxa_main_clade.mintax.svg){#fig:oxa-main-tree}

The OXA-48 prevalence hits added further diversity to the reference OXA-48-like sequences. OXA-436 [@KEhNzdys] was found, clustered with no other gene, in the prevalence data, and OXA-514 and OXA-515 were found in the non-redundant data. The named variants are too similar to produce significant phylogenetic resolution.


## Discussion

### An expanded set of candidate resistance genes

Homologous sequences from NCBI, CARD prevalence data, and a large set of MAGs, were queried, filtered, and added to phylogenies.
The filtering criteria were chosen to ignore small changes between sequences (99-100% sequence identity threshold), and to produce meaningful alignments in the final phylogenies (90-99% query coverage).

NCBI and CARD prevalence added new homologues to the phylogenies, however, these conservative filtering criteria contributed obvious novel homologues from only the MCR MAG analysis, and not in the three beta lactamase MAG analyses.
This difference could be explained by plasmid distributions.
Plasmids could have been poorly recovered in the assembly phase of the SRA experiments, many of which produce short reads (Illumina HiSeq 2000 and 2500).
TODO: Look at The number/percentages of completely sequenced genomes, completely sequenced plasmids analyzed for each pathogen, and see if there is any concrete evidence that the above is actually happening.
This seems to be problematic with bias in sampling, so other ideas/sources that may be promising are welcome.
Plasmids from short reads are known to be difficult to assemble[@12zFifp5x] [@12zFifp5x] [@DTtDOvle].

### Phylogenetic positioning of AMR genes from NCBI and MAGs

Another way in which the analyses of MCR and the beta lactamases differ is in the spread and diversity of the relationships.
In addition to MAG sources, which are completely absent from the beta lactamase trees, the MCR tree contains several sequences from NCBI’s non-redundant database which land close to canonical clades.
Some of the added NCBI and MAG sourced sequences are not so close, but share ancestors with canonical sequences nonetheless.
This suggests that there could be more diversity to be found within the MCR class.
In contrast, the added diversity in phylogenies from OXA-48, KPC is distant from the canonical and prevalence sequences.
The matches which are close, are nearly identical to the canonical and prevalence sequences.
The beta-lactamase phylogenies are low in gene diversity, and are more tightly defined than the MCR phylogenies.

### Phylogenetic relationships vs. nomenclature

In assessing the value of the relationships present in these more tightly related phylogenies, it is surprising that the literature has produced so many named variants.
In the tree for NDM, we have named variants numbered from NDM 1 to NDM 14, yet most of the tree would be more appropriately displayed with multifurcating nodes.
There are fifteen named variants, but there are only three weakly distinct clades, and little bootstrap support (TODO: look at SNPs put this in results?).
The most divergent NDM sequence is a prevalence sequence which is labelled as NDM-1, yet is more distant from other homologs named NDM-1 than other NDM-1 genes.
The criteria for naming these genes are seemingly arbitrary.
It is also possible that incentive to find new names for producing publication contributes to many of the more redundant variants.
Similarly, KPC is very tightly related and some of the same arguments could be made for classification of these sequences.
In the tree for OXA-48 like genes, we see more diversity, with branches of more support.
The tree forms few tightly related clades, and allows some diversity from NCBI to be added to the tree.
The OXA group, as a whole, is very diverse, but only because they are classified phenotypically.
If the OXA were more thoroughly separated into actual homologous groups, perhaps we would see more diversity added to the group, and perhaps even from metagenomic data.
These groups of OXA could behave very differently and some could have data recovery similar to that of MCR, but we are missing out on this because of the phenotypic naming scheme over a rigorous scheme which takes into account the genetic similarity. In MCR, the naming situation is less arbitrary. The closely related variants are classified under the same primary number.
Several versions of MCR-1 exist, for example, and all form a clade.

### Should naming reflect phylogenetic relationships?

Finding an ideal nomenclature scheme which within, or generalizing across AMR families is problematic.
Nomenclature which has been shown to be phylogenetically consistent, such as that of MCR, is nonetheless subject to ambiguity.
Researchers have suggested, for example for MCR [@x2VQlvOO], using amino acid sequence identity differences rather than possibly trivial nucleotide differences, but this still subject to ambiguity in cutoff of percent identity.
Fixed cutoffs of 2% have been suggested by some researchers[@eGJmNg9p], but depending on the mechanism of resistance, the level of diversity required to induce differences in substrate specificity will change between AMR genes.
One could argue that the genomic and evolutionary context should be also considered in the nomenclature [@EhIOtkvv].
It has been suggested, for example that mobilized, and chromosomal genes differ in their evolutionary variance [@EhIOtkvv].
In addition, the current study demonstrates that the diversity and spread varies between gene families.
This could be explained by the way MCR works by modifying the target of polymyxin, unlike the beta-lactamases, which work by destroying the beta-lactams.
Justifying naming of a new NDM gene, when all genes available to the public are essentially identical, seems to be problematic, however, further investigations into certain patterns of changes in the amino acid sequences may further granularize our classification.
Ultimately, many interesting questions about the nomenclature of these genes are rooted in ontology.
Classifying these genes is of utmost importance for communication between scientists, and a naming scheme which seeks a balance between practicality, evolutionary relationships, function, and context, must be found.


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
