# Alien Cancer Cures - DATA

Under this directory we keep all the data generated during the experiments of our project. 

## Directory Structure
- Under [metadata directory](./metadata/), we have the different versions of the metadata file we have generated based on the requirements for certain analyses.
- Under [denoising directory](./denoising/), we have the output files produced denoising experiments.
- Under [taxonomy directory](./taxonomy/), we have the output files produced taxonomy experiments.
- Under [phylogeny directory](./phylogeny/), we have the output files produced phylogeny experiments.
- Under [alpha_diversity directory](./alpha_diversity/), we have the output files produced alpha diversity analysis experiments.
- Under [beta_diversity directory](./beta_diversity/), we have the output files produced beta diversity analysis experiments.
- Under [differential_abundance directory](./differential_abundance/), we have the output files produced differential abundance analysis experiments.
- Under [functional_prediction directory](./functional_prediction/), we have the output files produced by functional prediction analysis experiments. The figures of pathways generated during this analysis stored under [plots/functional_prediction directory](../plots/functional_prediction/).

## Missing Files
Since the size of some files are huge, we did not upload a couple of files from our analysis to GitHub. We explicitly mention them here, as well as how to generate them so that the users can reproduce our analyses.

### sequences.qza

This file is the input file for our project which can be downloaded using the following command:

```bash
$ wget -nv -O ./sequences.qza https://polybox.ethz.ch/index.php/s/PCQspFMocVCKjZ3/download
```

### denoising/primer-trimmed-seqs.qza

This file is the trimmed sequences of the input file which can be generated using the following command:

```bash
$ qiime cutadapt trim-paired \
$  --i-demultiplexed-sequences sequences.qza \
$  --p-front-f AYTGGGYDTAAAGNG \
$  --p-front-r CCGTCAATTYHTTTRAGT \
$  --p-error-rate 0 \
$  --o-trimmed-sequences denoising/primer-trimmed-seqs.qza
```

### taxonomy/gg-13-8-99-nb-classifier.qza

This file is the pretrained classifier used for taxonomy classification which can be downloaded using the following command:

```bash
$ wget -nv -O taxonomy/gg-13-8-99-nb-classifier.qza 'https://data.qiime2.org/2022.8/common/gg-13-8-99-nb-classifier.qza'
```

### phylogeny/sepp-refs-gg-13-8.qza

This file is the reference database used for fragment insert tree of phylogeny analysis which can be downloaded using the following command:

```bash
$ wget -nv -O phylogeny/sepp-refs-gg-13-8.qza https://data.qiime2.org/2021.4/common/sepp-refs-gg-13-8.qza
```
