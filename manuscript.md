---
author-meta:
- Jackie Purdue
- Jocelyn McDonald
- Dayna Mikkelsen
- Finlay Maguire
- Robert G. Beiko
date-meta: '2020-10-06'
keywords:
- metagenome
- antimicrobial resistance
lang: en-CA
title: Incorporation of metagenome-assembled genome data into antimicrobial resistance
  surveillance identifies inconsistencies in carbapenemase and colistin resistance
  gene nomenclature
...






<small><em>
This manuscript
([permalink](https://jackiepurdue.github.io/phylogenetic-amr-survey-manuscript/v/159d9742aa8ac96a488d8fb62444384175592aa9/))
was automatically generated
from [jackiepurdue/phylogenetic-amr-survey-manuscript@159d974](https://github.com/jackiepurdue/phylogenetic-amr-survey-manuscript/tree/159d9742aa8ac96a488d8fb62444384175592aa9)
on October 6, 2020.
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

The increase and spread of antimicrobial resistance (AMR) poses a global threat to human and animal health.
The emergence of mobilised genes conferring resistance to last-line antibiotics such as carbapenems and polymyxins are a particular cause for alarm.
Given their ability to be laterally transferred between unrelated bacteria, surveillance of the evolution and transmission of these genes is vital to mitigating their impact.
However, the poor characterisation of many important non-clinical environments and bacteria as well as failings in the existing classification and nomenclature of AMR genes pose a major barrier to this work.
Metagenome assembled genome (MAG) methods, in which genomes are recovered from untargeted metagenomic sequencing, have been used to greatly increase the diversity of sampled bacterial genomes.
Therefore, by profiling AMR genes detectable in MAG datasets we can greatly expand surveillance of these undersampled environments and organisms.
Through this, we can also identify inconsistencies and potential refinements of the existing nomenclature.

In this study, the phylogenetic neighborhoods of several mobilised AMR gene families, of public-health importance, were examined for diversity, spread, and classification consistency.
These gene families include: mobile colistin resistance (MCR), New Delhi beta-lactamase (NDM), _Klebsiella pneumoniae_ carbapenemase (KPC), and the OXA-48-like beta-lactamase family.
Canonical genes in the Comprehensive Antibiotic Resistance Database (CARD) for these families were used to identify putative homologues within CARD:Resistomes & Variants data, NCBI non-redundant databases, and draft quality MAGs from a large set of uncultivated bacterial and archeal sources (UBA).

Although limited novel diversity in NDM, KPC, and OXA-48-like carbapenemases was identified, several possibly new clades of MCR genes were discovered.
In general, the carbapenemase families were found to be more tightly defined, with most added diversity being either extremely close, or phylogenetically distant.
The MCR family showed many new clades of diversity, even within well defined "canonical" clades.
A large number of existing gene names within all 4 families were identified to be inconsistent with phylogeny or inconsequential in relation to the diversity they encompass.
Additionally, there was a huge variability in the diversity encompassed by individual allele names across the AMR gene families analysed.
These results highlight the need to incorporate MAG data into AMR surveillance work and to develop consistent, robust, phylogenetically defined nomenclature for AMR genes.


## Introduction

Antimicrobials, substances which can kill or inhibit the growth of microbes [@Zvf1VhKR], are key effectors in the ecology of microorganisms.
The evolution of resistance to these substances, known as antimicrobial resistance (AMR), is an important and ancient process [@2xaXclNM].
In the last century we have adopted and used antimicrobials to great effect in clinical medicine and agriculture.
However, the use and abuse of antimicrobials has led to increasing levels of observed AMR [@1ByMfX8Y1].
AMR poses a growing global health risk by undermining our ability to treat infectious diseases and perform surgeries [@kDtOJsGI].
Infections by resistant microbes have greater associated mortality and morbidity [@kDtOJsGI], with the European Centre for Disease Prevention and Control estimating that 25,000 people per year die due to resistant infections [@OLzrpsK4].

To mitigate the spread of AMR, the World Health Organization (WHO) (and national government bodies e.g., [@10jnMhzRm]) have identified that strengthening surveillance of AMR, especially transmission of AMR between environmental and clinical samples [@3pJyRnMt], is vital.
The WHO's priority list of antibiotic resistant bacteria [@Pb5xYOu4] highlights the multi-drug resistant pathogens upon which these efforts should be focused.
This includes the ESKAPE pathogens: _Enterococcus faecium_, _Staphylococcus aureus_, _Klebsiella pneumoniae_, _Acinetobacter baumannii_, _Pseudomonas aeruginosa_, and _Enterobacter_ spp. [@bODq6dmJ,@b2c0QSMI,@aMfsvHsj].
These pathogens have become resistant to many common classes of antimicrobials including penicillins, all generations of cephalosporins, gylcopeptides, quinolones, and peptide antibiotics [@bODq6dmJ].
Concerningly, this also includes resistance to last-line carbapenem and colistin antibiotics related to mobilised AMR genes i.e., laterally transferable between unrelated lineages [@oR3fXrzb].

Carbapenems are broad spectrum beta-lactam antibiotics that cannot be degraded by most beta-lactamases, as such they are used to treat life threatening, high risk, and multi-drug resistant bacterial infections [@OLzrpsK4].
The number of observed carbapenem resistant _K. pneumoniae_, _E. coli_, _E. cloacae_, and _A. baumanii_ hospital-acquired infections have increased in Canada since 2013 [@hbKzfUrw], presenting a new threat to public-health.
Resistance to carbapenems is largely mediated by acquisition of one of several families of carbapenemase genes [@OLzrpsK4].
Due to their mobility and host-range, 3 of the carbapenemase gene families of most pressing public-health concern are _Klebsiella pneumoniae_ carbapenamase (KPC), New Delhi metallo-beta-lactamase (NDM), and OXA-48-like beta-lactamases [@OLzrpsK4].
These are, respectively, the most prevalent carbapenemase families within the A, B, and D beta-lactamase classes [@OLzrpsK4].

For carbapenem resistant infections, polymyxin E (colistin) and B antibiotics are frequently the only remaining option.
Polymyxins act by disrupting membrane permeability [@17k3PVuIy] and have had limited use in humans due to their neurotoxic and nephrotoxic effects [@17k3PVuIy].
Despite this, mobilized colistin resistance (MCR) has emerged in clinical pathogens [@vQTzfitx] likely due to transmission from agricultural usage of colistin [@11oxu50eO].
This underscores the vital importance of a "One-Health" based comprehensive surveillance program of AMR genes and their movement across environmental, agricultural, and clinical contexts.

This kind of AMR surveillance requires large-scale phylogenetic analyses which characterise the total diversity, context, and spread of these key resistance determinants.
In order to perform these types of analyses we need two resources: a clear consolidated definition of what constitutes an AMR-related gene and a large number of sequenced microbial genomes.
However, naming and defining AMR genes is difficult due to a complex legacy of historical nomenclature (prior to widespread DNA sequencing), and a huge quantity of active AMR research from a broad-range of stakeholders including academia, government organizations, human health, animal health, and agri-food industries [@10jnMhzRm].

AMR determinants are typically classified into families [@nvbyXyPe], some of which are based on phenotypic properties, and others on sequence homology.
These families are usually named according to a specific unifying characteristic, such as the resistance conferred (e.g., OXA-48-like, MCR), the geographic (e.g., "New Delhi" portion of NDM) or taxonomic (KPC) source of first observed examples, or the molecular structure ("metalloenzyme" portion of NDM).
These are reduced to a short acronym or abbreviated version (i.e., a gene symbol) and assigned a numerical suffix to distinguish variants.
Each allele, determined to be novel by some (ideally evolutionary) criterion, is assigned a new suffix number in this scheme.
For example, the MCR phosphoethanolamine transferase gene family inhibits the binding of colistin to the cell membrane.
The MCR-3 gene has a sequence identity which has been deemed to be significantly different from that of the other MCR genes in the family.
MCR-3.1, in turn has been deemed to be a variant of the MCR-3 gene, with only slight variation from other MCR-3 genes [@x2VQlvOO].
Alternatively, members of the NDM beta-lactamase gene family are named using a different set of criteria.
Specifically, genes that differ by only a single amino acid substitution are assigned a distinct suffix e.g., NDM-1 and NDM-2.
Consequently, the amount of diversity encompassed within different gene names and alleles is hugely variable across AMR families.
This problem is further exacerbated by the existence of AMR families such as the OXA-beta lactamases which are not defined on sequence identity but phenotypically.
Within this "family", there are numerous homologous sets of genes unified only by an ability to hydrolyse oxacillin.
OXA-20 has less than 20% amino acid sequence identity when compared with to other OXA-48-like family beta-lactamases [@1AFSAuSwx].
This highly variable complex system of classification has the potential to be misleading when conducting AMR research across the breadth of known AMR determinants.

High-quality manually curated AMR databases such as the Comprehensive Antibiotic Resistance Database (CARD) [@nvbyXyPe] provide a unified resource for the definition, nomenclature and classification of AMR genes.
CARD organizes this information through the Antibiotic Resistance Ontology (ARO), a controlled vocabulary with defined relationships.
There are two datasets within CARD, CARD:Canonical and CARD:Resistomes & Variants (R&V).
Canonical is a conservative set of AMR genes and mutations that have been experimentally verified as being associated with resistance in a peer-reviewed publication.
As a consequence, most of the entries in CARD:Canonical are derived from the most intensively studied organisms, such as the ESKAPE pathogens.
On the other hand, CARD:R&V contains AMR sequences that have been detected by searching a set of 88 WHO priority organism genomes from central repositories of publicly available sequencing data such as National Center for Biotechnology Information (NCBI) for genes similar to corresponding Canonical sequences.
This _in silico_ search is performed using CARD's BLAST/DIAMOND-based Resistance Gene Identifier (RGI) tool and greatly increases the sequence diversity in CARD [@nvbyXyPe].

However, this survey is still limited to a subset of all genomes currently available in central International Nucleotide Sequence Database Collaboration (INSDC) repositories like NCBI.
If we want to thoroughly understand the evolution and spread of AMR genes we need to as much genomic diversity as possible.
Unfortunately, the genomes in databases are largely sequenced from microbes that can be easily cultured. 
As only a subset of microbial diversity can be cultured, this means many of our existing genomes aren't necessarily representative of the environment from which they were sampled [@wapKbEHA].
Recently, techniques have been developed that allow the recovery of genomes from metagenomic data e.g., [@DTtDOvle,@DfIRBmdF].
As metagenomic sequencing, the direct sequencing of all DNA in a sample, doesn't require this bias inducing culturing step these metagenome-assembled genomes (MAGs) represent a huge source of previously unseen microbial diversity.
Parks et. al. [@wapKbEHA], generated new 7,903 bacterial and archaeal (Uncultured Bacteria and Archaea; UBA) MAGs representing >30% increase in the sampled phylogenetic diversity of the bacteria and archaea.

By combining this MAG dataset with CARD:R&V, and other NCBI non-redundant data, we are able to greatly increase the breadth of data available for surveillance beyond clinical samples.
Phylogenetic analyses of this data was then be used to characterise the evolution and novel diversity of these critical public-health priority carbapenemase (KPC, NDM, and OXA-48) and colistin (MCR) AMR gene families.
These analyses also highlight inconsistencies and possible refinements in the classification and nomenclature of these genes and their variant alleles.
Therefore, in this work we present an in-depth investigation of the classification and phylogeny of KPC, NDM, OXA-48, and MCR gene families across all currently available sequenced genomes and MAGs.


## Methods

All code used for this project is available at [github.com/jackiepurdue/amr_uba](github.com/jackiepurdue/amr_uba).

### Data

We surveyed four separate databases to assess the diversity of known and candidate AMR genes.
These sources include CARD:Canonical and CARD:R&V (version 3.0.5) sequences for the KPC, NDM, OXA-48-like, and MCR gene families, and associated homologs from NCBI non-redundant data and UBA MAG data.
The 32 canonical MCR sequence variants (Table {@tbl:mcr-variants}), 18 canonical KPC sequence variants (Table {@tbl:kpc-variants}), 14 canonical NDM sequence variants (Table {@tbl:ndm-variants}), and 6 canonical OXA-48-like sequence variants (Table {@tbl:oxa-variants}), as labeled in the CARD database, were obtained as a reference. 
The NCBI non-redundant data consisted of all non-redundant GenBank, Protein Data Bank (PDB), SwissProt, Protein information resource (PIR), Protein research foundation (PRF) data as of May 17, 2019.
The MAG data was derived from a data-set of 7,903 draft quality MAGs generated from Sequence Read Archive data by Parks et. al [@wrBRBdFb]. 
The SRA metagenomic data from which these MAGs were derived were chosen to represent lineages which were under-sampled (e.g., environmental and non-human gastrointestinal samples).

### Querying the data

The CARD canonical sequences from each family were used to perform a multiple query BLASTP (version 2.5.0 [@s9ycaHcq]) against the prevalence BLAST database with an e-value threshold and query coverages shown in Table 1. 
Many of the sequences are nearly identical, thus they were further processed by clustering with CD-HIT version 4.8.1 at a minimum sequence identity as per Table 1.

The reference CARD canonical sequences were also used to perform a multiple query BLASTP against the NCBI non-redundant database with an e-value and query coverage threshold indicated in Table 1
There are many highly sampled taxa and genes in the non-redundant database. 
To balance the distribution, and reduce the size of the non-redundant sequence set, CD-HIT version 4.8.1 was also used to cluster the data for each family as per Table 1.

For the metagenomic data, RGI version 5.0 with CARD database version 3.02 [@1ByMfX8Y1] was run on the contigs of the 7903 MAGs with the inclusion of loose, perfect, and strict hits.
The search strings in Table S1 were used to extract results from the RGI output.
The CARD canonical sequences were used to perform a multiple query BLASTP against this UBA blast database with an e-value threshold and query coverage from Table 1.
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
    <td class="tg-llyw">UBA<br></td>
    <td class="tg-llyw">CARD<br></td>
    <td class="tg-llyw">NCBI<br></td>
    <td class="tg-llyw">UBA<br></td>
    <td class="tg-llyw">CARD<br></td>
    <td class="tg-llyw">NCBI<br></td>
    <td class="tg-llyw">UBA<br></td>
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
    <td class="tg-0lax" colspan="10"><b>Table 1</b>: Parameters used with BLAST and CD-HIT to obtain sequences for the phylogenies<br>of MCR phosphoethanolamine transferase, and KPC, NDM, and OXA-48 beta-lactamases.<br>For each determinant, the minimum BLAST e-values, minimum query coverages, and CD-HIT Sequence Identity <br>threshold for clustering sequences are displayed for each database.<br>CARD represents the RGI-CARD prevalence sequence data, NCBI represents the NCBI non-redundant sequence<br>data, and UBA represents the MAG data source.<br><br>After filtering, OXA did not have an overabundance of close sequences and was not clustered (marked as N/A)<br></td>
  </tr>
</tbody>
</table>
![Table 1: Names of the canonical MCR phosphoethanolamine transferase variants from CARD database](){#tbl:params}

### Sequence Alignment

Two alignments were created for each AMR determinant under study.
The first alignment was created to compare the phylogenetic relationship of the canonical and R&V (putative) sequences.
The second alignment was created for a comparison of sequences from all four databases.

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

A phylogeny with only CARD:Canonical and CARD:R&V MCR gene family sequences was created, showing the relationships without diversity from NCBI or the MAGs, including an out-group, 32 CARD:Canonical sequences, and 54 CARD:R&V sequences.
The resulting tree in Figure {@fig:canon-prev-tree} shows MCR family members 1 through 9 forming distinct sub-clades in the tree.
MCR-1, MCR-2, and MCR-6 form a closely related clade.
This clade is closely related to ICR-Mc [@JT9eRkR8], another phosphoethanolamine transferase which confers colistin resistance.
MCR-3 and MCR-7, also form a closely related clade.

![Phylogenetic relationship of 32 canonical (labels prefixed with 'lcl_canon' in yellow), 54 CARD:R&V (labels prefixed with 'lcl_prev' in tan) MCR family sequences, and an outgroup from Betaproteobacteria ('lcl_outgroup' in grey). Each MCR variant is coloured based on its allele number.](images/mcr_canon_prev_full.mintax.svg){#fig:canon-prev-tree}

The tree visualisation was further condensed to only a single representative for each MCR allele (figure {@fig:canon-prev-tree-collapsed}).
Regions of the tree vary in their potential to accept additional diversity.
Some clades are tightly related, while others have more distance between them.
Newly discovered genes could some day be found to be sister to these more distantly related clades.
Regions containing more evolutionary distance are accommodating to additional diversity, while closely related regions are not.

![Phylogenetic relationship of 9 representative MCR family sequences, and an outgroup from Betaproteobacteria. (labels prefixed with 'lcl_canon' in yellow are canonical, labels prefixed with 'lcl_prev' in tan are CARD:R&V, and an outgroup from Betaproteobacteria is prefixed with 'lcl_outgroup' in grey)](images/mcr_canon_prev_collapsed.mintax.svg){#fig:canon-prev-tree-collapsed}

The phylogenies represented by Figures {@fig:mcr-3-9}, {@fig:mcr-5-icr}, and {@fig:canon-prev-nrdb-uba-tree} were created with additional diversity by querying the NCBI non-redundant database, and the MAGs from the Parks _et. al._ UBA data [@wrBRBdFb].
The filtering criteria in Table 1 were applied to these data sets.

After filtering, 409 NCBI sequence hits, labeled as phosphoethanolamine lipid A transferase, and 104 NCBI sequence hits, labeled as MCR family, were selected for addition to the phylogeny.
The 7903 draft quality MAGs were queried for AMR genes with RGI.
RGI produced 1457246 loose hits, 7171 strict hits, and 310 perfect hits.
After applying the filters from Table 1, only 63 MAG derived genes were retained for the phylogeny.
Due to the large size, the phylogeny displayed in Figure {@fig:canon-prev-nrdb-uba-tree} was subdivided into Figures {@fig:mcr-3-9}, and {@fig:mcr-5-icr}.
The subdivisions were chosen based on a pruning at the point of the most recent common ancestor of sets of canonical MCR labeled leaves.
The set including MCR-3, MCR-7, and MCR-9, and the set including MCR-1, MCR-2, MCR-5, MCR-6, and ICR-Mc, contained several clades sister to some of the canonical and CARD:R&V leaves.
Other choices for leaf sets contained added diversity that was distant from canonical sequences, and were not chosen as a focused figures.

Sister to the canonical MCR-3 sequences, and the most recent common ancestor of MCR-3 and MCR-7 clades (figure {@fig:mcr-3-9}), there is a clade of sequences from NCBI which have been reported as MCR-3.
Present within this clade is a single result from the Parks _et. al._ UBA dataset [@wrBRBdFb], UBA705.
This leaf is labelled as *Aeromonas hydrophila*, and is associated with rice paddy field-soil microbial fuel cells.
This is present within the clade alone with several other canonical and non-redundant *Aeromonas*.
*A. hydrophila* is a species which has been found to have an MCR-3 gene.

Sister to the clade containing MCR 7, and the most recent common ancestor of MCR 3 and MCR 7 clades, is a clade of NCBI sourced phosphoethanolamine lipid A transferase.
This clade consists of the genus of Gram-negative bacteria, *Aeromonas*, [@16EwPCiJT] which is sometimes involved in human infection.
This clade also includes an *A. veronii* hit from epidermal mucus of *Anguilla anguilla* in the UBA data.
Sister to the MCR 9 clade and the most recent common ancestor of MCR 3 and 9, a clade of *Aeromonas* associated phosphoethanolamine lipid A transferases appear.
The MCR 9 containing clade contains 8 UBAs and several NCBI non-redundant hits not reported as MCR family genes.
5 Loose hits for MCR in a *Leclercia adecarboxylata* branch within this clade.
These *Leclercia* branch as a sister to the common ancestor of MCR-9 and MCR-3 which are well supported.
The *Leclercia* UBAs were all sampled from New York City MTA subway.
*Acinetobacter* is another opportunistic pathogen [@8uz5m0fP] which is becoming resistant to many antimicrobials.

![Clade containing putative MCR3 and MCR 9 clades pruned from phylogenetic relationship of 32 canonical (labels prefixed with 'lcl_canon'_ in yellow), and 54 CARD:R&V (labels prefixed with 'lcl_prev' in tan) MCR family sequences, 595 NCBI non-redundant sequences (labels prefixed with 'lcl_nrdb' in blue), and 91 UBA sourced sequences (labels prefixed with 'lcl_uba' in green). Each MCR variant is coloured based on its allele number. If the sequence is not reported to be MCR family it is coloured in grey.](images/mcr3_mcr9_diversity.mintax.svg){#fig:mcr-3-9}

Sister to the MCR 5 and ICR-Mc clades (figure {#fig:mcr-5mayb-icr}), there appear clades of diversity in the genus *Psychrobacter*.
A descendant to this ancestor, is a clade of *Psycrobacter* species bacteria.

This clade includes several hits from the non-redundant database, and two hits from the UBA data.
According to the UBA [@wrBRBdFb] data, the identity of these samples are,
UBA3068, A *Psychrobacter sp.*, sampled from Oil polluted marine microbial communities and, UBA4193, a *Psychrobacter sp.*, sampled from the New York City subway.
The quality information for these sequences, shown in table ?? [TODO: do we need a table with quality information], shows that UBA3068 is near complete, while UBA4193 is only partial.
It is encouraging to see that even with the quality difference, these two sequences branch in the expected clade.
*Psychrobacter* [@BjoH1Vii] is a widespread genus and includes many cold adapted bacteria, it is an opportunistic pathogen, and has been found to sometimes be a cause of infections in humans, animals, and fish. Many new species of *Psychrobacter* have been discovered in cold climates [@WLzELTTa].
Some of the species have been shown to be resistant to colistin, like *P. vallis ps. nov.* and *P. aquaticus ps. nov.* [@2NZAmp2H] and is sister to [TODO: display new tree such that *Acinetobacter* is shown]
Another clade sister to hese two variants contains phosphoethanolamine transferases from the genus *Stenotrophomonas*, including *S. maltophilia* and *S. acidaminiphila* which is a multidrug-resistant opportunistic pathogen [@Ovca71PG].
Several UBA hits for *S. maltophilia* show up as shotgun sequencing of environmental samples. [TODO: quality information]

![Clade containing putative MCR 5 and ICR-Mc clades pruned from phylogenetic relationship of 32 canonical labels (prefixed with 'lcl_canon'_ in yellow), and 54 CARD:R&V(labels prefixed with 'lcl_prev' in tan) MCR family sequences, 595 NCBI non-redundant sequences (labels prefixed with 'lcl_nrdb' in blue), and 91 UBA sourced sequences (labels prefixed with 'lcl_uba' in green). Each MCR variant is coloured based on its allele number. If the sequence is not reported to be MCR family it is coloured in grey.](images/mcr5_icrmc_diversity.mintax.svg){#fig:mcr-5-icr}

### Phylogenetic analysis of KPC

Using the 18 canonical sequences from Table {@tbl:kpc-variants} as query sequences, 25 CARD:R&V sequences, 376 non-redundant sequences, and 6 UBA sequences were recovered from the various databases. The result was 
combined in the phylogeny displayed in figure {@fig:kpc-tree}.
This phylogeny shows that many of the resulting sequences are distant from the canonical sequences. The main clade in figure {@fig:kpc-main-tree} shows that many of the AMR determinants are named as distinct sequences, while not having much phylogenetic distance between them.
The most closely related clade is a clade containing IMI and SME-type beta-lactamases.
The remaining sequences are in a clade containing a large amount of class A beta-lactamases from the non-redundant data. All of the UBA sequences were present in this portion of the tree.

![A clade pruned from the phylogeny in figure {#fig:kpc-tree} which represents the most closely related genes to the KPC family genes. 18 canonical labels (prefixed with 'lcl_canon'_ in yellow), and 25 CARD:R&V (labels prefixed with 'lcl_prev' in tan), and 28 NCBI non-redundant sequences (labels prefixed with 'lcl_nrdb' in blue). Each KPC variant is coloured based on its allele number. If the sequence is not reported to be KPC family it is coloured in grey.](images/kpc_main_clade.mintax.svg){#fig:kpc-main-tree}


### Phylogenetic analysis of NDM

14 canonical sequences were used to query the data for NDM beta-lactamase.
The genes retained for the phylogeny were 14 canonical sequences, 8 CARD:R&V sequences, 12 non-redundant sequences, 1 UBA sequence, and an out-group.
This resulted in the phylogenetic relationship in Figure {@fig:ndm-tree}.

![Phylogenetic relationship of The NDM genes with 14 canonical (labels prefixed with 'lcl_canon' in yellow), 8 CARD:R&V (labels prefixed with 'lcl_prev' in tan), 12 NCBI non-redundant database sequences (labeled as 'lcl_nrdb' in blue), 1 UBA sequence (labeled as 'lcl_uba' in green), and an outgroup from Betaproteobacteria (labeled as 'lcl_outgroup' in grey). Each NDM variant is coloured based on its allele number.](images/ndm_full.mintax.svg){#fig:ndm-tree-all}

The 12 sequences resulting from the NCBI data included 3 genes reported to be NDM-1, NDM-3, and NDM-5, while the other 4 genes were reported to be general beta-lactamase/carbapenemase hits.
As in the KPC phylogeny (figure {@fig:kpc-main-tree}), there is very little phylogenetic difference between the named variants of NDM.
The only phylogenetically distinct genes in this clade were the CARD:R&V hit for NDM-1, and the NCBI hits labeled as NDM-1 and NDM-5.
The naming of these sequences seem not to be congruent with the phylogenetic relationships present in the tree.
Some of the NDM-1 and NDM-5 genes are more closely related to the other NDM variants than themselves.
One BLAST result from the UBA data branches far from the clade containing the canonical sequences.
This indicates that under the coverage queried, there are no reasonably detectable NDM homologues in the UBA data.
The alignment of this UBA under this relaxed query coverage of 60% (see Table 1) is questionable.
Reducing query coverage further could produce more sequences from the UBA data, but the resulting alignment would produce a meaningless phylogeny.

### Phylogenetic analysis of OXA-48

In querying for the OXA-48 portion of the analysis, multiple BLAST results for UBA sequences were found, but the hits were too phylogenetically dissimilar to draw a conjecture about their relationship to the OXA family. 6 canonical sequences, and the 14 CARD:R&V sequences, and 20 non-redundant sequences are combined in the phylogeny in Figure {@fig:oxa-tree}

![The main phylogenetic relationship pruned from the tree inferred from OXA-48-like sequences from figure {#fig:oxa-tree}. 6 canonical (labels prefixed with 'lcl_canon'_ in yellow), and 14 CARD:R&V (labels prefixed with 'lcl_prev' in tan), 20 NCBI non-redundant sequences (labels prefixed with 'lcl_nrdb' in blue). Each OXA-48 variant is coloured based on its allele number. If the sequence is not reported to be OXA-48 family it is coloured in grey.](images/oxa_main_clade.mintax.svg){#fig:oxa-main-tree}

The OXA-48 CARD:R&V hits added further diversity to the reference OXA-48-like sequences. OXA-436 [@KEhNzdys] was found, clustered with no other gene, in the CARD:R&V data, and OXA-514 and OXA-515 were found in the non-redundant data. The named variants are too similar to produce significant phylogenetic resolution.


## Discussion

### An expanded set of candidate resistance genes

Homologous sequences from NCBI, CARD:R&V data, and a large set of MAGs, were queried, filtered, and added to phylogenies.
The filtering criteria were chosen to ignore small changes between sequences (99-100% sequence identity threshold), and to produce meaningful alignments in the final phylogenies (90-99% query coverage).

NCBI and CARD:R&V added new homologues to the phylogenies, however, these conservative filtering criteria contributed obvious novel homologues from only the MCR MAG analysis, and not in the three beta lactamase MAG analyses.
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
In contrast, the added diversity in phylogenies from OXA-48, KPC is distant from the canonical and CARD:R&V sequences.
The matches which are close, are nearly identical to the canonical and CARD:R&V sequences.
The beta-lactamase phylogenies are low in gene diversity, and are more tightly defined than the MCR phylogenies.

### Phylogenetic relationships vs. nomenclature

In assessing the value of the relationships present in these more tightly related phylogenies, it is surprising that the literature has produced so many named variants.
In the tree for NDM, we have named variants numbered from NDM 1 to NDM 14, yet most of the tree would be more appropriately displayed with multifurcating nodes.
There are fifteen named variants, but there are only three weakly distinct clades, and little bootstrap support (TODO: look at SNPs put this in results?).
The most divergent NDM sequence is a CARD:R&V sequence which is labelled as NDM-1, yet is more distant from other homologs named NDM-1 than other NDM-1 genes.
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
