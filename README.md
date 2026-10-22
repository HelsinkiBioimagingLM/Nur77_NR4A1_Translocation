# Nur77_NR4A1_Translocation

Image analysis pipeline for measuring the ratio of intensity between the nuclei and cytoplasm of treated and untreated cells at various timepoints

All datapoints are an n=1, so statistical inferences cannot be made.

[Requirements for python enviroment](requirements.txt) running Python v3.12

Analysis in brief:

Central 3 slices of each z-stack were projected based on median values. CellPose4 was used to segment the cell and nuclei separately. These segmentation masks were processed such that no objects touched the XY border and all cells contained a nuclei and vice versa. The resulting objects were then used to generate the cytoplasm segmentation through array subtraction (cells - nuclei). Intensity measurements were then quantified within each compartment using scikit-image and the ratio of the nuclei to cytoplasm intensity calculated from the resulting measurements. The mean of all ratios per datapoint were calculated and used for plotting.