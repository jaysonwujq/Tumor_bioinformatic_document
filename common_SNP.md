*common snp in dbsnp*

    common SNP is one that has at least one 1000Genomes population with a MAF >= 1% and for which 2 or more founders contribute to that minor allele frequency 
    ftp://ftp.ncbi.nih.gov/snp/organisms/human_9606_b151_GRCh37p13/VCF/

*filter*

    filter:synonymous SNV,intronic,intergenic
    filter:(MAF>0.01):1000g2015aug_all','ExAC_ALL','esp6500siv2_all','genomeAD'
    
*non-synonymous variants annotation*

    'SIFT_pred','Polyphen2_HDIV_pred','CADD_phred','FATHMM_pred','MutationAssessor_pred'