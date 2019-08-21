# 学习笔记

## TMB

## MSI

        Luchini C, Bibeau F, Ligtenberg M J L, et al. ESMO recommendations on microsatellite instability testing for immunotherapy in cancer, and its relationship with PD-1/PD-L1 expression and tumour mutational burden: a systematic review-based approach[J]. Annals of Oncology, 2019.

## CNV

        Gusnanto A, Taylor C C, Nafisah I, et al. Estimating optimal window size for analysis of low-coverage next-generation sequence data[J]. Bioinformatics, 2014, 30(13): 1823-1829.

## hgvs

http://varnomen.hgvs.org/recommendations/general/

	    “c.” for a coding DNA reference sequence
	
        “g.” for a linear genomic reference sequence
    
        “m.” for a mitochondrial DNA reference sequence
    
        “n.” for a non-coding DNA reference sequence
    
        “o.” for a circular genomic reference sequence
    
        “p.” for a protein reference sequence
    
        “r.” for an RNA reference sequence (transcript)

## hg19

        ftp://gsapubftp-anonymous@ftp.broadinstitute.org/bundle/hg19/ucsc.hg19.fasta.gz

## cosmic_hotspot

    Variants listed in COSMIC were considered hotspot point mutations if they presented with >=5 mentions

    For mutations found in at least 50 samples according to the COSMIC database (“hotspots”)
    
    Analysis of Tumor Mutational Burden with TruSight® Tumor 170
        You could find this info from CosmicCodingMuts.vcf(Download from COSMIC).
        ##INFO=<ID=CNT,Number=1,Type=Integer,Description="How many samples have this mutation">

    Sukhai M A, Misyura M, Thomas M, et al. Somatic Tumor Variant Filtration Strategies to Optimize Tumor-Only Molecular Profiling Using Targeted Next-Generation Sequencing Panels[J]. The Journal of Molecular Diagnostics, 2019, 21(2): 261-273. 

## Distinguish somatic and germline
   
1.  VAF（20% for small insertions/deletions, 30% for SNVs)

        Mandelker D, Donoghue M T A, Talukdar S, et al. Germline-Focused Analysis of Tumour-Only Sequencing: Recommendations from the ESMO Precision Medicine Working Group[J]. Annals of Oncology, 2019.

2.  machine learning approach

        Wood D E, White J R, Georgiadis A, et al. A machine learning approach for somatic mutation discovery[J]. Science translational medicine, 2018, 10(457): eaar7939.
        
        Sun J X, He Y, Sanford E, et al. A computational approach to distinguish somatic vs. germline origin of genomic alterations from deep sequencing of cancer specimens without a matched normal[J]. PLoS computational biology, 2018, 14(2): e1005965.

## Canonical_transcript
## Indel_realigner
## ACMG
## call_SNV
## MSK
## FoundationOne

## convert GRch37 to hg19  
     
ftp://gsapubftp-anonymous@ftp.broadinstitute.org/Liftover_Chain_Files/b37tohg19.chain
     
     gatk  --java-options "-Djava.io.tmpdir=./ -Xmx60G"" LiftoverVcf -I query.vcf.gz -O query.hg19.vcf.gz -R ucsc.hg19.fasta --REJECT unmapped.vcf -C b37tohg19.chain
     
     bgzip -c query.hg19.vcf > query.hg19.vcf.gz
     
     tabix -p vcf query.hg19.vcf.gz
     
 http://hgdownload.cse.ucsc.edu/gbdb/hg19/liftOver/
 http://bioinfo5pilm46.mit.edu/software/GATK/resources/

## common snp

    common SNP is one that has at least one 1000Genomes population with a MAF >= 1% and for which 2 or more founders contribute to that minor allele frequency 
    ftp://ftp.ncbi.nih.gov/snp/organisms/human_9606_b151_GRCh37p13/VCF/



        
  