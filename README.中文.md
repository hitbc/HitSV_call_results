# HitSV: Maximizing discovery of structural variants across sequencing technologies

## 项目说明
该项目存储了HitSV工具的在HG002/3/4/5/6/7与千人基因组上的变异检测结果。

工具所在的github位置
https://github.com/hitbc/HitSV
所有变异检测都基于grch38参考基因组
算法别名：gcSV

## HitSV LRS SV 检测信息

所有 数据都是30X
结果都经过局部phase（pseudo-phased），结果包含了原始的contig序列以及每个SV周围的小变异信息。

### HG002 CCS数据集

该数据被重新比对到grch38参考基因组上

数据的原始来源：
https://ftp-trace.ncbi.nlm.nih.gov/ReferenceSamples/giab/data/AshkenazimTrio/HG002_NA24385_son/PacBio_CCS_15kb/alignment/HG002.Sequel.15kb.pbmm2.hs37d5.whatshap.haplotag.RTG.10x.trio.bam

HitSV的变异检测结果：
[/home/fenghe/vscode/HitSV_call_results](https://github.com/hitbc/HitSV_call_results)/HG002-LRS/ccs.30X.vcf.gz

### HG002 ONT数据集：
数据的原始来源：
s3://ont-open-data/giab_2025.01/basecalling/sup/HG002/PAW70337/calls.sorted.bam

HitSV的变异检测结果：
[/home/fenghe/vscode/HitSV_call_results](https://github.com/hitbc/HitSV_call_results)/HG002-LRS/ont.30X.vcf.gz

### 家系 ONT 数据集：HG002/HG003/HG004 HG005/HG006/HG007
数据的原始来源：
s3://ont-open-data/giab_2025.01/basecalling/sup/HG002/PAW70337/calls.sorted.bam (download by aws s3 cps)
s3://ont-open-data/giab_2025.01/basecalling/sup/HG003/PAY87794/calls.sorted.bam
s3://ont-open-data/giab_2025.01/basecalling/sup/HG004/PAY87778/calls.sorted.bam
s3://ont-open-data/giab_2025.01/basecalling/sup/HG005/PAW87816/calls.sorted.bam
s3://ont-open-data/giab_2025.01/basecalling/sup/HG006/PAY77227/calls.sorted.bam
s3://ont-open-data/giab_2025.01/basecalling/sup/HG007/PAY12990/calls.sorted.bam

HitSV的变异检测结果：
[/home/fenghe/vscode/HitSV_call_results](https://github.com/hitbc/HitSV_call_results)/LRS-TRIO/sup_HG00*.vcf.gz

## HitSV SRS SV 检测信息

### HG002 SRS 60x 数据集：
数据的原始来源：
https://ftp-trace.ncbi.nlm.nih.gov/ReferenceSamples/giab/data/AshkenazimTrio/HG002_NA24385_son/NIST_HiSeq_HG002_Homogeneity-10953946/NHGRI_Illumina300X_AJtrio_novoalign_bams/HG002.hs37d5.60x.1.bam
HitSV的变异检测结果：
[/home/fenghe/vscode/HitSV_call_results](https://github.com/hitbc/HitSV_call_results)/HG002-SRS/ILL_60X.vcf.gz

### HG002 SRS 35x 数据集：
数据的原始来源：
https://opendata.nist.gov/pdrsrv/mds2-2336/input_fastqs/HG002.novaseq.pcr-free.35x.R1.fastq.gz

HitSV的变异检测结果：
[/home/fenghe/vscode/HitSV_call_results](https://github.com/hitbc/HitSV_call_results)/HG002-SRS/ILL_35X.vcf.gz

## HitSV Hybrid SV 检测信息

数据的原始来源：
参阅上文。

HitSV的变异检测结果【分别是 ONT与Illumina的混合以及CCS与Illumina的混合】：

[/home/fenghe/vscode/HitSV_call_results](https://github.com/hitbc/HitSV_call_results)/HG002-Hybrid/HYBRID_ILL.30X.ont.4X.vcf.gz
[/home/fenghe/vscode/HitSV_call_results](https://github.com/hitbc/HitSV_call_results)/HG002-Hybrid/HYBRID_ILL.30X.ccs.4X.vcf.gz

## 1000 Genomes Project 3,202 HitSV-call

### 单样本变异检测数据

数据的原始来源：
https://ftp.1000genomes.ebi.ac.uk/vol1/ftp/data_collections/1000_genomes_project/data/
变异检测结果：【提供了随机10个样本的结果】
[/home/fenghe/vscode/HitSV_call_results](https://github.com/hitbc/HitSV_call_results)/HG002-Hybrid/HYBRID_ILL.30X.ccs.4X.vcf.gz
https://github.com/hitbc/HitSV_call_results/tree/main/1KGP-single%20sample/*.vcf.gz

### 群体变异检测数据

数据的原始来源：同上

变异检测结果：【不同染色体分开存储】
https://github.com/hitbc/HitSV_call_results/blob/main/1KGP_3202_samples_gcSV_v1.0_grch38_SURVIVOR_merge/1KGP_3202_samples_gcSV_v1.0_grch38_SURVIVOR_merge_sort_chr*.vcf.gz

### 千人基因组 VNTR 分析: 简单重复区间的SV

说明：
以 `VNTR_REGION` 开头的行：每行描述一个基于 Repeat Masker 的简单重复区域。列代表：染色体 ID（0-based）、区域的起始和结束位置、注释类型以及重复单元。
不以 `VNTR_REGION` 开头的行：每行描述一个位于特定简单重复区域内的结构变异（SV）。列代表：染色体 ID（0-based）、变异的起始位置、变异长度、REF、ALT 以及不同超人群中的等位基因计数（AC）。
结果：
https://github.com/hitbc/HitSV_call_results/blob/main/1KGP_3202_samples_gcSV_v1.0_grch38_VNTR_ANALYSIS.txt.gz

