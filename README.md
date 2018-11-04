# andy_flow_tools
Jupyter notebooks for processing tidy FCS files into gates, joy plots, GMM fits, and more!

NOTE: Currently there are no unit tests for any of the code provided. Caveat emptor. 

The standard workflow is as follows. 

0. 
Pre-process your .fcs files into tidied .csv files. I use fcsparser, there are other python compatible tools available that I'm sure work just as well. 

1. 
Gate your tidied .fcs files. This is performed using "ADH_automatic_flow_gating_and_well_labeling.ipynb"

The input is the tidied .csv files. The output is a similar tidied .csv file, but containing only cells that pass gating. 

2. 
Use gated files for making joy plots. This is performed using "ADH_make_joy.ipynb"

The input is the output from "ADH_automatic_flow_gating_and_well_labeling.ipynb" the output is either single joyplots or entire 96-well plate layouts each with an individual joyplot. 

3. 
Use gated files for automatic peak detection. This is performed using "ADH_find_peaks.ipynb" 

The input is the output from "ADH_automatic_flow_gating_and_well_labeling.ipynb" the output is a summary datafile in tidy format where each well from the flow cytometry run is now reduced to a single tidy format output containing the peak positions (mean), mass (fraction of population), number of peaks, and mean across the entire well. This is useful for further data processing. 

4. 
Use peak data for making reduced representation plots. 

This is performed using "ADH_reduced_plots"

The input is the output from "ADH_find_peaks.ipynb" the output are plots either using entropy or multidot plots that attempt to reduce the higher dimension flow data into lower dimensional plots. 
