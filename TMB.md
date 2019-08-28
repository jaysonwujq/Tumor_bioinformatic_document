#   关于TMB的一些相关信息你需要知道：

    TMB的定义如下：TMB was defined as the number of somatic, coding, base substitution, and indel mutations per megabase of genome examined. 可参考文献[1]

a.  
    
    panel size的问题对于TMB的计算很重要，不能太小，最小0.5吧，也有建议0.8以上，不过总的结论是不能太小,越大越接近外显子的结果.
    
    panel的设计初衷有时候不仅仅是call变异，也有SV、基因融合等等，这些区域在计算TMB的时候不应该考虑在内,对于变异位点，建议将同义突变也考虑进去。
    
    在测序深度上一般的panel是500X，为了较准确的发现低频突变，最低也不要低于200X。
    
    在call变异过程中VAFFoundationOne CDx and Oncomine assays (https://www.accessdata.fda.gov/cdrh_docs/pdf17/P170019B.pdf)与MSK-IMPACT都是大于等于5%，但是热点突变是2%[2-4]

b.  

    关于热点突变（文献里也指驱动突变）建议还是要去掉的，貌似不是去掉整个驱动基因而是驱动突变或者热点突变,关于热点突变有的文献粗略的定义cosmic数据库中CNT>=50的位点，这些位点你可以通过下载cosmic数据库的VCF获得[5]

c.  

    无论是正常样本还是肿瘤样本，germline位点一般VAF都集中在50%与100%附近，一般情况下在肿瘤样本中46%的germline位点的VAF位于40%-60%之间，35%的germline位点的VAF大于95%，约有19%的后选位点不在这个范围内（依据AMP/ASCO/CAP guidelines）[6]
    另外变异位点也是考虑体细胞突变，如何区分体细胞和遗传性突变，要么你就是配对样本，如果你是tumor only那么可以参考Foundation Medicine’s FoundationOne panel 开发的SGZ（https://github.com/jsunfmi/SGZ），不过是需要一定的样本作为训练集合的[5,7]

d.  
 
    TMB有明确证据证明在 non-small cell lung carcinoma (NSCLC)是biomarker，但并不是在所有癌种中都适用,泛癌种的TMB表现可以参考[8-9]

#   关于panel测序数据质控

a.  
    
    关于对panel测序数据对质控非常重要，其中一些关键指标可以参考在线文档：http://netdocs.roche.com/DDM/Effective/07187009001_RNG_SeqCap-EZ_TchNote_Eval-data_v2.1.pdf
    
    此外FOLD_80_BASE_PENALTY这个指标是评价panel性能又一关键指标，对于外显子测序该指标为2-4之间[10]
    
    对该指标对解释说明可以参见：https://twistbioscience.com/sites/default/files/resources/2018-10/Twist_NGS_WhitePaper_UniformityonTarget_18Sep18.pdf

b.

    关于panel测序数据质控的代码：https://github.com/fanyucai1/sample_qc/blob/master/sample_qc.py
    
    使用说明：
    sample_qc.py

    This script will given a metrix of bam file stat.

    Usage:python3 sample_qc.py target_bed probe_bed bamfile outdir prefix

    target_bed and probe_be maybe a same file

    the bamfile must remove or mark PCR duplicates

    Email:fanyucai1@126.com
    输出示例：
    The result output as follows::

    Counts-On-Target_Reads	626001
    mean_depth	303.485387
    median_depth	287
    FOLD_80_BASE_PENALTY	2.009837
    %_bases_above_1	98.6
    %_bases_above_5	97.3
    %_bases_above_10	96.9
    %_bases_above_50	93.6
    %_bases_above_100	88.3
    %_bases_above_250	58.6
    %_bases_above_500	14.2
    %_bases_above_1000	14.2
    %_bases_above_10000	14.2


##  参考文献

    1.  Chalmers Z R, Connelly C F, Fabrizio D, et al. Analysis of 100,000 human cancer genomes reveals the landscape of tumor mutational burden[J]. Genome medicine, 2017, 9(1): 34.
    
    2.  Buchhalter I, Rempel E, Endris V, et al. Size matters: Dissecting key parameters for panel‐based tumor mutational burden analysis[J]. International journal of cancer, 2019, 144(4): 848-858.

    3.  Büttner R, Longshore J W, López-Ríos F, et al. Implementing TMB measurement in clinical practice: considerations on assay requirements[J]. ESMO open, 2019, 4(1): e000442.
    
    4.  Zehir A, Benayed R, Shah R H, et al. Mutational landscape of metastatic cancer revealed from prospective clinical sequencing of 10,000 patients[J]. Nature medicine, 2017, 23(6): 703.
    
    5.  Wood D E, White J R, Georgiadis A, et al. A machine learning approach for somatic mutation discovery[J]. Science translational medicine, 2018, 10(457): eaar7939.

    6.  Montgomery N D, Selitsky S R, Patel N M, et al. Identification of Germline Variants in Tumor Genomic Sequencing Analysis[J]. The Journal of molecular diagnostics: JMD, 2018, 20(1): 123-125.
    
    7.  Sun J X, He Y, Sanford E, et al. A computational approach to distinguish somatic vs. germline origin of genomic alterations from deep sequencing of cancer specimens without a matched normal[J]. PLoS computational biology, 2018, 14(2): e1005965.

    8.  Fancello L, Gandini S, Pelicci P G, et al. Tumor mutational burden quantification from targeted gene panels: major advancements and challenges[J]. Journal for immunotherapy of cancer, 2019, 7(1): 183.
    
    9.  Samstein R M, Lee C H, Shoushtari A N, et al. Tumor mutational load predicts survival after immunotherapy across multiple cancer types[J]. Nature genetics, 2019, 51(2): 202-206.
    
    10.  So A P, Vilborg A, Bouhlal Y, et al. A robust targeted sequencing approach for low input and variable quality DNA from clinical samples[J]. NPJ genomic medicine, 2018, 3(1): 2.