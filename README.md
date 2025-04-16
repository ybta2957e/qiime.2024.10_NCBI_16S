The original 16S database was downloaded from NCBI RefSeq by qiime rescript.

```
qiime rescript get-ncbi-data     --p-query '33175[BioProject] OR 33317[BioProject]'     --o-sequences ncbi-refseqs-unfiltered.qza     --o-taxonomy ncbi-refseqs-taxonomy-unfiltered.qza
qiime rescript filter-seqs-length-by-taxon     --i-sequences ncbi-refseqs-unfiltered.qza     --i-taxonomy ncbi-refseqs-taxonomy-unfiltered.qza     --p-labels Archaea Bacteria     --p-min-lens 900 1200     --o-filtered-seqs ncbi-refseqs.qza     --o-discarded-seqs ncbi-refseqs-tooshort.qza
 qiime rescript filter-taxa     --i-taxonomy ncbi-refseqs-taxonomy-unfiltered.qza     --m-ids-to-keep-file ncbi-refseqs.qza     --o-filtered-taxonomy ncbi-refseqs-taxonomy.qza
```
