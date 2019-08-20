# TMB

a.  panel size的问题对于TMB的计算很重要，不能太小，最小0.5吧[1]，也有建议0.8M的[2]，不过总的结论是不能太小,越大越接近外显的结果

b.  panel的设计初衷有时候不仅仅是call变异，也有SV、基因融合等等，这些区域在计算TMB的时候不应该考虑在内[1]

c.  对于变异位点，建议将同义突变也考虑进去[1]

d.  关于热点突变（文献里也指驱动突变）建议还是要去掉的，貌似不是去掉整个驱动基因而是驱动突变或者热点突变,关于热点突变有的文献粗略的定义cosmic数据库中CNT>=50的位点，这些位点你可以通过下载cosmic数据库的VCF获得

e.  另外变异位点也是考虑体细胞突变，如何区分体细胞和遗传性突变，要么你就是配对样本，如果你是tumor only那么可以参考Foundation Medicine’s FoundationOne panel 开发的SGZ（https://github.com/jsunfmi/SGZ），不过是需要一定的样本作为训练集合的[3]

g.  在测序深度上一般的panel是500X，为了较准确的发现低频突变，最低也不要低于200X[2]

f.  在call变异过程中VAFFoundationOne CDx and Oncomine assays 与MSK-IMPACT都是大于等于5%，但是热点突变是2%[2]

h.  TMB有明确证据证明在 non-small cell lung carcinoma (NSCLC)是biomarker，但并不是在所有癌种中都适用[4]



##  参考文献

    1.  Buchhalter I, Rempel E, Endris V, et al. Size matters: Dissecting key parameters for panel‐based tumor mutational burden analysis[J]. International journal of cancer, 2019, 144(4): 848-858.

    2.  Büttner R, Longshore J W, López-Ríos F, et al. Implementing TMB measurement in clinical practice: considerations on assay requirements[J]. ESMO open, 2019, 4(1): e000442.

    3.  Sun J X, He Y, Sanford E, et al. A computational approach to distinguish somatic vs. germline origin of genomic alterations from deep sequencing of cancer specimens without a matched normal[J]. PLoS computational biology, 2018, 14(2): e1005965.

    4.  Fancello L, Gandini S, Pelicci P G, et al. Tumor mutational burden quantification from targeted gene panels: major advancements and challenges[J]. Journal for immunotherapy of cancer, 2019, 7(1): 183.
    