# [TPAMI 2024] Benchmark for VG-based Detection and Chart Understanding (VG-DCU) 
## Introduction

<p align="center">
<img src="figures\RGvsVG.png" alt="Differece" width="80%">
</p>

Rendering vector graphics into pixel arrays can result in significant memory costs or loss of information, as demonstrated in above Figure 1. We propose the first large-scale chart-based vector graphics dataset focusing on VG-based Detection and Chart Understanding. 

| Task                             | Dataset                            | Type | Source            | \# Chart Type | \# Nums  |
|----------------------------------|------------------------------------|------|-------------------|---------------|----------|
| ChartQA                          | DVQA                  | RG   | Synthetic         | 1             | 300,000  |
|                                  | FigureQA          | RG   | Synthetic         | 5             | 100,000  |
|                                  | PlotQA            | RG   | Synthetic         | 3             | 224,377  |
|                                  | LEAF-QA             | RG   | Synthetic         | 4             | 250,000  |
| Chart-to-Table                   | ICPR 2020         | RG   | Synthetic \& Real | 15            | 40,322   |
|                                  | ICPR 2022         | RG   | Real              | 15            | 36,183   |
| VG Detection (YOLaT used)       | SESYD-Floorplans| VG   | Synthetic         | -             | 1,000    |
|                                  | SESYD-Diagrams  | VG   | Synthetic         | -             | 1,000    |
| VG Detection & Chart-to-Table    | VG-DCU(Ours)                      | VG   | Synthetic \& Real | 16            | 15,197   |

The currently available public vector graphics datasets are limited to the two small datasets indicated in Table and lacks the complexity necessary for the advancement of vector image detection. In contrast, our proposed dataset comprises over 10,000 vector charts utilizing diverse primitives with rich attributes.
## Dataset Construction
<p align="center">
<img src="figures\types.png" alt="Differece" width="80%">
</p>
The proposed VG-based chart dataset contains two subsets:
+ **Vega-Lite**: a synthetic subset generated with scripts and fictional data
+ **Plotly**a real-world subset drawn by users. 

## Dataset Statistic
**Dataset Split**: We collect 10,682 synthetic and 4,515 real charts in the VG-DCU dataset, by default using 80% as the training set and 20% as the test set. We divide the training and test set so that objects from the same category are included in both the training and testing set. 

|                  | Vega-Lite     |            | Plotly     |            |
|------------------|--------------|------------|------------|------------|
| Chart Type       | Train        | Test       | Train      | Test       |
|------------------|--------------|------------|------------|------------|
| Area             | 0            | 0          | 87         | 22         |
| Bar (Vert. \& Hor.) | 2,400       | 601        | 1,704      | 426        |
| Box (Vert. \& Hor.)| 0           | 0          | 482        | 121        |
| Donut\&Pie       | 2,395        | 599        | 200        | 50         |
| Line             | 3,749        | 938        | 146        | 37         |
| Scatter          | 0            | 0          | 640        | 161        |
| Heatmap          | 0            | 0          | 154        | 39         |
| Counter          | 0            | 0          | 180        | 45         |
| Violin           | 0            | 0          | 82         | 21         |
| Sankey           | 0            | 0          | 21         | 6          |
| Total            | 8,544        | 2,138      | 3,609      | 906        |
