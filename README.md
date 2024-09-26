# fMRI-Data-Analysis-AFNI
This project involves working with functional MRI (fMRI) data and processing it through various stages, focusing on structural and functional brain data. Here's a detailed breakdown of the project:

Part 1: Structural Data Processing
Initial Image Preparation:

The project starts by processing structural MRI images. The first step involves using a tool called 3dSkullStrip to remove non-brain tissues from the MRI images.
Volume Calculation:

The volume of the brain is calculated using voxel dimensions extracted from the image header. The volume is computed based on the number of voxels and their size in each spatial direction, resulting in a total brain volume of approximately 8650 cm³.
Gray Matter Isolation:

A brain mask is created using the 3dAutomask function to isolate brain tissues from the skull-stripped images.
Using 3dcalc, a threshold is applied to the skull-stripped dataset to isolate gray matter, and a gray matter mask is created. This mask highlights gray matter regions in the brain for further analysis.
Part 2 & 3: Functional Data Preprocessing and Mapping
Preprocessing Pipeline:

The fMRI data undergoes several preprocessing steps:
Removal of Initial Volumes: Discarding the first few volumes to stabilize the scanner.
Slice Timing Correction: Correcting for the timing differences between slices acquired at different times during the scan.
Motion Correction: Aligning the images to account for any movement by the subject during the scan.
Normalization: Adjusting the images to match a standard anatomical template.
Spatial and Temporal Filtering: Reducing noise and artifacts from the data.
Global Intensity Normalization: Ensuring consistent signal intensity across the entire dataset.
Mapping Functional Data to Structural Data:

The processed functional images are aligned with structural images using the align_epi_anat.py function. This step ensures that the functional data (which shows brain activity) is correctly overlaid on the structural data (which shows brain anatomy).
Part 4 & 5: Event-Related Analysis
Stimulus Onset Extraction:

The onset timings for visual stimuli and reaction times are extracted from the event-related file (.tsv format) and saved in text files.
GLM Analysis with 3dDeconvolve:

The General Linear Model (GLM) is applied to the preprocessed fMRI data using 3dDeconvolve. This model analyzes the relationship between the brain activity (as measured by fMRI) and the experimental conditions (e.g., visual stimuli).
Specific contrasts, such as the difference between standard and oddball stimuli, are calculated to identify brain regions activated by these stimuli.
Part 6: General Insights and Conclusion
The project concludes by reflecting on the importance of the preprocessing steps and the GLM analysis in accurately identifying task-related neural responses. The final output includes statistical maps showing brain activation in response to the experimental conditions.
This project showcases a comprehensive approach to processing and analyzing fMRI data, combining structural and functional imaging techniques to understand brain activity in response to specific stimuli.
