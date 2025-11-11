# Taxa_Collapse_Relativeabundance

This repository documents the workflow for taxonomy-level collapsing and relative abundance calculation using QIIME2 (v2023.9).

---

## Steps Overview
1. **Collapse feature table by taxonomic level (1–7)**
2. **Generate relative frequency tables**
3. **Export `.biom` files and convert to `.tsv` and `.csv`**
4. **Obtain level-wise relative abundance data for downstream analysis**

---

# Collapse level 1
time qiime taxa collapse \
  --i-table ./filtered-qza/filtered-table-dada.qza \
  --i-taxonomy ./filtered-qza/filtered-taxonomy.qza \
  --p-level 1 \
  --o-collapsed-table ./abundance-from-filtered/gut-table-l1.qza

# Collapse level 2
time qiime taxa collapse \
  --i-table ./filtered-qza/filtered-table-dada.qza \
  --i-taxonomy ./filtered-qza/filtered-taxonomy.qza \
  --p-level 2 \
  --o-collapsed-table ./abundance-from-filtered/gut-table-l2.qza

# level2 relative abundance download
time qiime feature-table relative-frequency \
  --i-table ./abundance-from-filtered/level-2/gut-table-l2.qza \
  --o-relative-frequency-table ./abundance-from-filtered/level-2/gut-table-l2-relative.qza

# level2 .biom "relative"
qiime tools export \
  --input-path ./abundance-from-filtered/level-2/gut-table-l2-relative.qza \
  --output-path ./abundance-from-filtered/level-2/gut-table-l2-relative/

# level2 - Convert .biom to tsv
time biom convert \
  --input-fp ./abundance-from-filtered/level-2/gut-table-l2-relative/feature-table.biom \
  --output-fp ./abundance-from-filtered/level-2/gut-table-l2-relative.tsv \
  --to-tsv

# Convert tsv to csv
csvformat -t ./abundance-from-filtered/level-2/gut-table-l2-relative/gut-table-l2-relative.tsv > ./abundance-from-filtered/level-2/gut-table-l2-relative.csv

# Collapse level 3
time qiime taxa collapse \
  --i-table ./filtered-qza/filtered-table-dada.qza \
  --i-taxonomy ./filtered-qza/filtered-taxonomy.qza \
  --p-level 3 \
  --o-collapsed-table ./abundance-from-filtered/gut-table-l3.qza

# level3 relative abundance download
time qiime feature-table relative-frequency \
  --i-table ./abundance-from-filtered/level-3/gut-table-l3.qza \
  --o-relative-frequency-table ./abundance-from-filtered/level-3/gut-table-l3-relative.qza

# level3 .biom "relative"
qiime tools export \
  --input-path ./abundance-from-filtered/level-3/gut-table-l3-relative.qza \
  --output-path ./abundance-from-filtered/level-3/gut-table-l3-relative/

# level3 - Convert .biom to tsv
time biom convert \
  --input-fp ./abundance-from-filtered/level-3/gut-table-l3-relative/feature-table.biom \
  --output-fp ./abundance-from-filtered/level-3/gut-table-l3-relative.tsv \
  --to-tsv

# Convert tsv to csv
csvformat -t ./abundance-from-filtered/level-3/gut-table-l3-relative/gut-table-l3-relative.tsv > ./abundance-from-filtered/level-3/gut-table-l3-relative.csv

# Collapse level 4
time qiime taxa collapse \
  --i-table ./filtered-qza/filtered-table-dada.qza \
  --i-taxonomy ./filtered-qza/filtered-taxonomy.qza \
  --p-level 4 \
  --o-collapsed-table ./abundance-from-filtered/gut-table-l4.qza

# level4 relative abundance download
time qiime feature-table relative-frequency \
  --i-table ./abundance-from-filtered/level-4/gut-table-l4.qza \
  --o-relative-frequency-table ./abundance-from-filtered/level-4/gut-table-l4-relative.qza

# level4 .biom "relative"
qiime tools export \
  --input-path ./abundance-from-filtered/level-4/gut-table-l4-relative.qza \
  --output-path ./abundance-from-filtered/level-4/gut-table-l4-relative/

# level4 - Convert .biom to tsv
time biom convert \
  --input-fp ./abundance-from-filtered/level-4/gut-table-l4-relative/feature-table.biom \
  --output-fp ./abundance-from-filtered/level-4/gut-table-l4-relative.tsv \
  --to-tsv

# Convert tsv to csv
csvformat -t ./abundance-from-filtered/level-4/gut-table-l4-relative/gut-table-l4-relative.tsv > ./abundance-from-filtered/level-4/gut-table-l4-relative.csv

# Collapse level 5
time qiime taxa collapse \
  --i-table ./filtered-qza/filtered-table-dada.qza \
  --i-taxonomy ./filtered-qza/filtered-taxonomy.qza \
  --p-level 5 \
  --o-collapsed-table ./abundance-from-filtered/gut-table-l5.qza

# level5 relative abundance download
time qiime feature-table relative-frequency \
  --i-table ./abundance-from-filtered/level-5/gut-table-l5.qza \
  --o-relative-frequency-table ./abundance-from-filtered/level-5/gut-table-l5-relative.qza

# level5 .biom "relative"
qiime tools export \
  --input-path ./abundance-from-filtered/level-5/gut-table-l5-relative.qza \
  --output-path ./abundance-from-filtered/level-5/gut-table-l5-relative/

# level5 - Convert .biom to tsv
time biom convert \
  --input-fp ./abundance-from-filtered/level-5/gut-table-l5-relative/feature-table.biom \
  --output-fp ./abundance-from-filtered/level-5/gut-table-l5-relative.tsv \
  --to-tsv

# Convert tsv to csv
csvformat -t ./abundance-from-filtered/level-5/gut-table-l5-relative/gut-table-l5-relative.tsv > ./abundance-from-filtered/level-5/gut-table-l5-relative.csv

# Collapse level 6
time qiime taxa collapse \
  --i-table ./filtered-qza/filtered-table-dada.qza \
  --i-taxonomy ./filtered-qza/filtered-taxonomy.qza \
  --p-level 6 \
  --o-collapsed-table ./abundance-from-filtered/gut-table-l6.qza

# level6 relative abundance download
time qiime feature-table relative-frequency \
  --i-table ./abundance-from-filtered/level-6/gut-table-l6.qza \
  --o-relative-frequency-table ./abundance-from-filtered/level-6/gut-table-l6-relative.qza

# level6 .biom "relative"
qiime tools export \
  --input-path ./abundance-from-filtered/level-6/gut-table-l6-relative.qza \
  --output-path ./abundance-from-filtered/level-6/gut-table-l6-relative/

# level6 - Convert .biom to tsv
time biom convert \
  --input-fp ./abundance-from-filtered/level-6/gut-table-l6-relative/feature-table.biom \
  --output-fp ./abundance-from-filtered/level-6/gut-table-l6-relative.tsv \
  --to-tsv

# Convert tsv to csv
csvformat -t ./abundance-from-filtered/level-6/gut-table-l6-relative/gut-table-l6-relative.tsv > ./abundance-from-filtered/level-6/gut-table-l6-relative.csv

# Collapse level 7
time qiime taxa collapse \
  --i-table ./filtered-qza/filtered-table-dada.qza \
  --i-taxonomy ./filtered-qza/filtered-taxonomy.qza \
  --p-level 7 \
  --o-collapsed-table ./abundance-from-filtered/gut-table-l7.qza

# level7 relative abundance download
time qiime feature-table relative-frequency \
  --i-table ./abundance-from-filtered/level-7/gut-table-l7.qza \
  --o-relative-frequency-table ./abundance-from-filtered/level-7/gut-table-l7-relative.qza

# level7 .biom "relative"
qiime tools export \
  --input-path ./abundance-from-filtered/level-7/gut-table-l7-relative.qza \
  --output-path ./abundance-from-filtered/level-7/gut-table-l7-relative/

# level7 - Convert .biom to tsv
time biom convert \
  --input-fp ./abundance-from-filtered/level-7/gut-table-l7-relative/feature-table.biom \
  --output-fp ./abundance-from-filtered/level-7/gut-table-l7-relative.tsv \
  --to-tsv

# Convert tsv to csv
csvformat -t ./abundance-from-filtered/level-7/gut-table-l7-relative/gut-table-l7-relative.tsv > ./abundance-from-filtered/level-7/gut-table-l7-relative.csv

## Output Files
- `gut-table-l1.qza` → Kingdom level  
- `gut-table-l2.qza` → Phylum level  
- `gut-table-l3.qza` → Class level  
- `gut-table-l4.qza` → Order level  
- `gut-table-l5.qza` → Family level  
- `gut-table-l6.qza` → Genus level  
- `gut-table-l7.qza` → Species level  
- Corresponding `*-relative.csv` files for each level represent relative abundance tables.

## Citation
- Bokulich NA et al., Nat Methods, 2018 – **QIIME2**.

## Author
**G. Sivasubramaniyan**
Assistant Professor & PhD scholar, Department of Microbiology,
Sri Ramachandra Institute of Higher Education and Research (SRIHER), Chennai, India
Email id: shivaviro24@gmail.com, sivasubramaniyan@sriramachandra.edu.in

**Acknowledgment**: Workflow guidance provided by a collaborator Dr Dilip Abraham from Christian Medical College Vellore.
