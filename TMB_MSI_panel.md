# 学习笔记

## TMB

        Büttner R, Longshore J W, López-Ríos F, et al. Implementing TMB measurement in clinical practice: considerations on assay requirements[J]. ESMO open, 2019, 4(1): e000442.

## MSI

        

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

1.  life平台对于经典转录本的定义https://ionreporter.thermofisher.com/ionreporter/help/GUID-A5502535-2C81-46FD-93C2-50FCB1F02CFD.html

2.  ACMG 推荐的经典转录本，但是目前数量只涉及到1000多个基因http://www.lrg-sequence.org

3.  依据clinvar爬取基因对应频次较多的转录本并排序（脚本程序：knownCanonical.py 基因与转录本对应表：knownCanonical.final.tsv）


## Indel_realigner

1. ABRA (https://github.com/mozack/abra2)

        Mose L E, Wilkerson M D, Hayes D N, et al. ABRA: improved coding indel detection via assembly-based realignment[J]. Bioinformatics, 2014, 30(19): 2813-2815.

2. SRMA (https://github.com/nh13/SRMA)

        Homer N, Nelson S F. Improved variant discovery through local re-alignment of short-read next-generation sequencing data using SRMA[J]. Genome biology, 2010, 11(10): R99.

## ACMG

1.  2012年1月美国医学遗传学与基因组学学会（ACMG，American College of Medical Genetics and Genomics）委员会正式批准成立临床外显子和基因组测序工作小组，此小组的任务就是当病人进行外显子或基因组测序时发现的偶发突变给出推荐性的指导。2013年，ACMG发表了一篇关于临床的官方声明，明确强调了偶发变异可能对揭示患者病情、临床测试以及报告结果的重要性。

            Rehm H L, Bale S J, Bayrak-Toydemir P, et al. ACMG clinical laboratory standards for next-generation sequencing[J]. Genetics in medicine, 2013, 15(9): 733.

            Green R C, Berg J S, Grody W W, et al. ACMG recommendations for reporting of incidental findings in clinical exome and genome sequencing[J]. Genetics in Medicine, 2013, 15(7): 565.

2.  2016年，ACMG更新了附带发现（secondary findings）的基因列表，他们推荐实验室在临床外显子和基因组测序结果中报告这些基因的突变。附带发现是指这些基因的变异与检测的初始目的没有关系，但会导致严重的疾病，目前关于这些变异的知识可以指导临床实践。ACMG发布这些建议的原因是，临床外显子组和基因组测序检测开始激增，但却缺乏相应的标准。ACMG不断更新的建议可以帮助确定哪些附带发现可以反馈给患者，对成年人和儿童患者都适用。更新后的列表包括59个基因。
      
            Kalia S S, Adelman K, Bale S J, et al. Recommendations for reporting of secondary findings in clinical exome and genome sequencing, 2016 update (ACMG SF v2. 0): a policy statement of the American College of Medical Genetics and Genomics[J]. Genetics in medicine, 2017, 19(2): 249.

3.  早在2015年，美国医学遗传学和基因组学（ACMG）以及分子病理学协会（AMP）曾联合出版了变异位点解读指南，基于28个判断标准（criteria）将变异位点分为了Pathogenic、Likely pathogenic、Uncertain significance、Likely benign和Benign五个级别。同样，在2017年，AMP、ASCO和CAP也联合制定了体细胞突变变异位点解读指南，基于变异位点的临床意义将其分为Tier I、Tier II、Tier III、Tier IV四个级别。时隔两年，由中国遗传学会遗传咨询分会领衔的专家团队共同编译了《ACMG遗传变异分类标准与指南》中文版（以下简称“中文版”），并获得美国ACMG的官方授权。中文在线地址：http://acmg.cbgc.org.cn/doku.php?id=start

            Richards S, Aziz N, Bale S, et al. Standards and guidelines for the interpretation of sequence variants: a joint consensus recommendation of the American College of Medical Genetics and Genomics and the Association for Molecular Pathology[J]. Genetics in medicine, 2015, 17(5): 405.

            Li M M, Datto M, Duncavage E J, et al. Standards and guidelines for the interpretation and reporting of sequence variants in cancer: a joint consensus recommendation of the Association for Molecular Pathology, American Society of Clinical Oncology, and College of American Pathologists[J]. The Journal of molecular diagnostics, 2017, 19(1): 4-23.

4.  同时对区分somatic mutations 和germline variants 也作出了相关解释。

        Montgomery N D, Selitsky S R, Patel N M, et al. Identification of Germline Variants in Tumor Genomic Sequencing Analysis[J]. The Journal of molecular diagnostics: JMD, 2018, 20(1): 123-125.

5.  2019年ACMG又提供了关于拷贝数变异检测的临床指导意见，在分类上同样。

        Mikhail F M, Biegel J A, Cooley L D, et al. Technical laboratory standards for interpretation and reporting of acquired copy-number abnormalities and copy-neutral loss of heterozygosity in neoplastic disorders: a joint consensus recommendation from the American College of Medical Genetics and Genomics (ACMG) and the Cancer Genomics Consortium (CGC)[J]. Genetics in Medicine, 2019: 1.

6.  此外生物信息过程可以参考的一些很棒的文献在文末也推荐给大家：

        Sallevelt S C E H, De Koning B, Szklarczyk R, et al. A comprehensive strategy for exome-based preconception carrier screening[J]. Genetics in Medicine, 2017, 19(5): 583.

        Strom S P. Current practices and guidelines for clinical next-generation sequencing oncology testing[J]. Cancer biology & medicine, 2016, 13(1): 3.

## call_SNV

    1.  Xu C. A review of somatic single nucleotide variant calling algorithms for next-generation sequencing data[J]. Computational and structural biotechnology journal, 2018, 16: 15-24.
        
    2.  Dunn T, Berry G, Emig-Agius D, et al. Pisces: An accurate and versatile variant caller for somatic and germline next-generation sequencing data[J]. BioRxiv, 2018: 291641.

    3.  Strom S P. Current practices and guidelines for clinical next-generation sequencing oncology testing[J]. Cancer biology & medicine, 2016, 13(1): 3.

    4.  Sukhai M A, Misyura M, Thomas M, et al. Somatic Tumor Variant Filtration Strategies to Optimize Tumor-Only Molecular Profiling Using Targeted Next-Generation Sequencing Panels[J]. The Journal of Molecular Diagnostics, 2019, 21(2): 261-273.


## MSK

    Dataset:    http://www.cbioportal.org/study?id=msk_impact_2017
    Pipeline:   https://impact-pipeline.readthedocs.io/en/latest/index.html#
    Zehir A, Benayed R, Shah R H, et al. Mutational landscape of metastatic cancer revealed from prospective clinical sequencing of 10,000 patients[J]. Nature medicine, 2017, 23(6): 703.

## FoundationOne

    Chalmers Z R, Connelly C F, Fabrizio D, et al. Analysis of 100,000 human cancer genomes reveals the landscape of tumor mutational burden[J]. Genome medicine, 2017, 9(1): 34.
    FDA. FoundationOne CDx: Summary of Safety and Effectiveness Data (SSED)(https://www.accessdata.fda.gov/cdrh_docs/pdf17/P170019B.pdf)

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



        
  