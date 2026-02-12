# HitSV: Maximizing discovery of structural variants across sequencing technologies

https://github.com/hitbc/HitSV

## HitSV LRS Structural Variant Detection Results

https://github.com/hitbc/HitSV_call_results/tree/main/LRS_HG002_single_sample




HG002 LRS dataset: down-sample to: 1x, 2x, 3x, 4x, 5x, 6x, 7x, 8x, 9x, 10x, 15x, 20x, 25x, 30x.
The results has been randomly pseudo-phased; and includes small variant data around SVs.

## HitSV Hybrid Structural Variant Detection Results

https://github.com/hitbc/HitSV_call_results/tree/main/Hybird_HG002_single_sample

HG002 LRS dataset: down-sample to 1x, 2x, 3x, 4x, 5x, 10x.
HG002 SRS dataset: down-sample to 30x, 60x.

## HitSV SRS Structural Variant Detection Results

https://github.com/hitbc/HitSV_call_results/tree/main/SRS_HG002_single_sample

HG002 SRS 60x dataset: down-sample to 15x, 30x, 60x.
HG002 SRS 35x dataset.

Note: The 35x data uses the grch38 reference genome, which is different from the other datasets(hs37d5).

## 1000 Genomes Project 3,202 HitSV-call merged File

https://github.com/hitbc/HitSV_call_results/blob/main/1KGP_3202_samples_HitSV_v1.0_grch38_SURVIVOR_merge/1KGP_3202_samples_HitSV_v1.0_grch38_SURVIVOR_merge_sort_chr*.vcf.gz

## VNTR analysis: SVs in simple repeat regions

https://github.com/hitbc/HitSV_call_results/blob/main/1KGP_3202_samples_HitSV_v1.0_grch38_VNTR_ANALYSIS.txt.gz

Lines starting with `VNTR_REGION`: 
Each line describes a simple repeat region based on Repeat Masker. 
The columns represent: chromosome ID (0-based), start and end positions of the region, annotation type, and repeat unit.

Lines not starting with `VNTR_REGION`: 
Each line describes a structural variant (SV) located within a specific simple repeat region. 
The columns represent: chromosome ID (0-based), start position of the variant, variant length, REF, ALT, and allele count (AC) in different superpopulations.

