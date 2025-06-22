# RNA-seq with DESeq2 Analysis RMarkdown

A single document performing:

1. **Setup**  
   - Load DESeq2, stringr, reshape, scales, xlsx

2. **Differential Expression (DESeq2)**  
   - Read raw counts, gene lengths, sample design  
   - Build `DESeqDataSet`, normalize counts  
   - Run `DESeq()`, extract `results()`  
   - Filter `NA` padj, sort by padj  
   - Write DE table & normalized counts

3. **TPM Conversion**  
   - Reload counts & gene lengths  
   - Compute TPM = (counts / (len/1e3)) / (sum / 1e6)  
   - Write `tpm.txt`

4. **DE on Combat-seq Corrected Data**  
   - Load COMBAT counts & design  
   - Design formula `~ replicate + condition`  
   - Run DESeq2 as above  
   - Output DE results & normalized counts

5. **PCA & t-SNE**  
   - Read TPM (or normalized) matrix  
   - Filter low/ambiguous genes, select top variable  
   - Perform PCA → plot PC1 vs PC2  
   - Run t-SNE → plot 2D embedding  
   - Save PCA figure as PDF
