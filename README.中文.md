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
https://github.com/hitbc/HitSV_call_results/HG002/HG002-Hybrid/HG002*.vcf.gz

## HGSVC 数据集 HitSV 检测结果

HGSVC（Human Genome Structural Variation Consortium）数据集包含五个个体（HG00096、HG00268、HG00358、HG00512、HG00731）的长读长测序数据。所有变异检测均基于 GRCh38 参考基因组。所有数据均为 30× 覆盖度，结果均经过局部定相。

数据的原始来源：
https://github.com/human-pangenomics/HG002_Data_Freeze_v1.0

HitSV LRS 变异检测结果（分别为 HiFi 和 ONT）：
https://github.com/hitbc/HitSV_call_results/HGSVC/HGSVC-LRS/*_HiFi30X_asm5.vcf.gz
https://github.com/hitbc/HitSV_call_results/HGSVC/HGSVC-LRS/*_ONT30X_asm5.vcf.gz

## 多物种数据集 HitSV 检测结果

HitSV 被应用于多种模式生物，涵盖不同测序平台（仅 LRS、仅 SRS，以及混合平台），以展示跨物种的适用性。涉及的物种包括：拟南芥（Arabidopsis thaliana）、斑马鱼（Danio rerio）、黑腹果蝇（Drosophila melanogaster）、食蟹猴（Macaca fascicularis）和小鼠（Mus musculus）。

### 原始数据来源

下表汇总了每个物种所使用的参考基因组、T2T 组装以及测序 reads：

| 物种 | 参考基因组 | T2T 组装 | 测序 Reads |
|------|-----------|----------|-----------|
| 食蟹猴 *Macaca fascicularis* | [GCA_011100615.1](https://www.ncbi.nlm.nih.gov/datasets/genome/GCA_011100615.1/) | [GCF_037993035.2](https://www.ncbi.nlm.nih.gov/datasets/genome/GCF_037993035.2/) | PacBio HiFi / Nanopore / Illumina — [BioProject 1037719](https://www.ncbi.nlm.nih.gov/sra?linkname=bioproject_sra_all&from_uid=1037719) |
| 小鼠 *Mus musculus* | [GCF_000001635.27](https://www.ncbi.nlm.nih.gov/datasets/genome/GCF_000001635.27/) | [mhaESC\_genome v1.1.0](https://github.com/yulab-ql/mhaESC_genome/releases/download/upd_rmvector/mouse.241018.v1.1.0.combined.fasta.gz) | PacBio HiFi / Nanopore / Illumina — [SAMN40876533](https://www.ncbi.nlm.nih.gov/Traces/study/?acc=SAMN40876533&o=acc_s%3Aa) |
| 黑腹果蝇 *Drosophila melanogaster* | [GCF_000001215.4](https://www.ncbi.nlm.nih.gov/datasets/genome/GCF_000001215.4/) | [PRJNA1237537](https://www.ncbi.nlm.nih.gov/datasets/genome/?bioproject=PRJNA1237537) | PacBio HiFi / Nanopore / DNBSEQ — [BioProject 1237537](https://www.ncbi.nlm.nih.gov/sra?linkname=bioproject_sra_all&from_uid=1237537) |
| 斑马鱼 *Danio rerio* | [GCF_049306965.1](https://www.ncbi.nlm.nih.gov/datasets/genome/GCF_049306965.1/) | [GCA_052040795.1](https://www.ncbi.nlm.nih.gov/datasets/genome/GCA_052040795.1/) | PacBio HiFi / Nanopore — [BioProject 1299309](https://www.ncbi.nlm.nih.gov/sra?linkname=bioproject_sra_all&from_uid=1299309) |
| 拟南芥 *Arabidopsis thaliana* | [GCF_000001735.4](https://www.ncbi.nlm.nih.gov/datasets/genome/GCF_000001735.4/) | [32 生态型泛基因组](https://figshare.com/articles/dataset/32_ecotypes_Arabidopsis_thaliana_genomes_gene_annotation_pan-TE_library_graph_pan-genome_gene_family_and_gene_presence_absence_matrices_files_/21673895) | Nanopore: [ERR11436642](ftp://ftp.sra.ebi.ac.uk/vol1/run/ERR114/ERR11436642/Nanopore_Kz-9.fastq.gz) · PacBio HiFi: [CRR591671](https://ngdc.cncb.ac.cn/gsa/browse/CRA008584/CRR591671) · Illumina: [ERR11436063](ftp://ftp.sra.ebi.ac.uk/vol1/run/ERR114/ERR11436063/Illumina_Kz-9_R1.fastq.gz) |

### LRS（长读长测序）

HitSV 变异检测结果（每个物种分别为 HiFi 和 ONT）：
https://github.com/hitbc/HitSV_call_results/Multi_species/*-LRS/*_HiFi_asm10.vcf.gz
https://github.com/hitbc/HitSV_call_results/Multi_species/*-LRS/*_ONT_asm10.vcf.gz

### SRS（短读长测序）

HitSV 变异检测结果：
https://github.com/hitbc/HitSV_call_results/Multi_species/*-SRS/*_SRS_asm10.vcf.gz

### 混合（LRS + SRS）

HitSV 变异检测结果（每个物种分别为 HiFi+Illumina 混合 和 ONT+Illumina 混合）：
https://github.com/hitbc/HitSV_call_results/Multi_species/*-Hybrid/*_HiFi4X_SRS30X_asm10.vcf.gz
https://github.com/hitbc/HitSV_call_results/Multi_species/*-Hybrid/*_ONT4X_SRS30X_asm10.vcf.gz

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