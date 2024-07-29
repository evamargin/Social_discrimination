This repo contains python notebooks for analyzing silicone probe recordings in mice performing social tasks.

1_Single_cell_anal Code takes spike data after kilosort and phy from “Processed data” in Filer. Also, Behavioral data required. Giulio aligned data on Matlab and saved it as Behavior.mat file. I opened it in Python and used it for extracting nosepoke timestamps. Output: heatmap for all cells with 50 ms binned mean firing rate; Rasters for each cell + psth

2_Populational_analysis Spikes from kilosort, behavior from Behavior.mat (Filer). Code performs pca, plots clusters in pcs space; then I calculated Mahalanobis distances and saved them as a matrix. Pkl file is also saved and can be used in the 7th notebook to calculate the average across sessions. Plus I found MD bw centroids and compared it with shuffle.

3.1_Models_morning SVM and Bayesian decoder. Discriminate between: 1) social (alpha+beta mice) and blank (no mouse) trials; 2) between 2 mice (alpha and beta). Shuffle control and p-val.

3.2_Models_left_right Here on sessions with 2 ports, we compare the decoding of mice identity with the decoding of a place of reward collection. Output: pca, MD matrix, SVM with shuffle control

3.3_Models_evening Compare morning and evening blocks from the same session (day). Pca, MD, euclidean distance; decoding alpha vs beta mouse: train on morning data, test on evening. Control decoding: morning (alpha+beta) vs evening (alpha+beta). Shuffle control.

3.4.1_Models_aaa_bbb Code for a time control experiment where we presented the same mouse (alpha or beta) in 3 subsequent blocks. Returns pca, MD, decoding results (SVM), shuffle control. Decoding between pairs of blocks: 1 vs 2, 2 vs 3, 1 vs 3.

3.4.2_Models_aaa_bbb_control The same approach as in 3.4.1 but with data from the experiment with 2 mice (mouse1, mouse2, blank; file 3.1). We want to see whether block sequence influenced the results we obtained.

4_Window_shift Code performs pca, MD, ED, decoding (SVM) for different behavioral windows: from -1sec t +1sec relative to nosepoke event

5_Taking_out_analysis This code fits SVM decoder on data with different neurons number and different trials number. Basically we investigate how accuracy depends on # of neurons and # of trials.

6_Surprize Takes results of Giulio’s surprise analysis and makes meta data that will be used in 7th notebook

7_meta Notebook that takes results of other notebooks and summarize results across all sessions

Performance_speed Take txt files with timestamps and calculates duration of 20 trials in each block

Nosepokes Code counts the number of nosepokes performed by recorded and visiting mice; count reciprocal nosepokes; at the end I played with crosscorr

Learning Plots performance of the mouse from session to session
