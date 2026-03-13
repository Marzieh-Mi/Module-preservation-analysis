# module_preservation_analysis
This repository includes scripts and workflows for analyzing the preservation of modules in gene co-expression networks.

## 1. Analytical Architecture:
# Cross-dataset Validation: 
Assessing whether the module structure identified in a "Reference" dataset is maintained in a "Test" dataset.
# Connectivity & Density Metrics: 
Evaluating preservation through Z_{summary} statistics, combining measures of module density and connectivity.
# Significance Thresholding: 
* Z_{summary} > 10: Strong evidence of preservation.
* 2 < Z_{summary} < 10: Weak to moderate preservation.
* Z_{summary} < 2: No evidence of preservation.
* Robustness Testing: Utilizing permutation testing (e.g., n=200) to ensure the results are statistically significant and not due to random chance.

## 2. Method
Weighted Gene Co-expression Network Analysis (WGCNA)

Reference:
Langfelder, P., & Horvath, S. (2008). WGCNA: an R package for weighted correlation network analysis

## 3. Analysis Workflow
1. Import gene expression data
2. Construct co-expression modules
3. Calculate module preservation statistics
5. Visualize preservation results (MedianRank & Zsummary plots)

## 4. Tools
- R
- WGCNA package

# 5. Related Repositories: 
Gene-co-expression-network-analysis
Downstream functional analysis (GO, promoter, miRNA)

```mermaid
graph TD
    A[Reference Network Modules] --> B[Test Dataset Integration]
    B --> C{Permutation Testing}
    C --> D[Calculate MedianRank]
    C --> E[Calculate Zsummary Statistics]
    D & E --> F{Preservation Assessment}
    F --> G[Identify Stable vs. Condition-Specific Modules]
