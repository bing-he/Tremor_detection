# An automatic envelope cross-correlation tremor detection method
A work flow to process data, get envelope, calculate envelope cross-correlation, and detect tremors from the ocean bottom seismic data in Alaska.

The detailed can be find in the paper soon. The basic idea refers the papers below.

One tremor example detected by my method.
<center><img src=Fig_S1.png width="700" height="700"/></center>

### Step1. 1_E_3min_write_loop_save_file.ipynb
Obtain seismic data, 2-8 Hz bandpass filter, get envelope (Obspy), low pass filter to 0.2 Hz, downsample to 1 Hz, save data 

### Step2. 2_EN_hflf_reload_data_cross_correlation.ipynb
Envelop cross-correlate in low (2-8 Hz) and high (10-16 Hz) frequency bands, and reference stations

### step3. 3_calculate_tremor_hierarchy_2.ipynb
using the hierachical cluster method find the most correlated station pairs.
The tremor is located if the cross-correlation is over 0.68 for more than 3 station pairs, but the time window is skipped if the cross-correlation is over 0.65 for at least 6 stations in 10-16 Hz to minimize the local earthquake detections. Besides, when the reference station cross-correlation is over 0.65 for at three four station pairs, that time window is discarded. The detection time window is skipped if it includes the earthueks in catalogs.

### Step4. 4_plot_figure_4paper.ipynb
Plot low, high frequency and hydrophone data

References:

Chen, K. H., Tai, H.-J., Ide, S., Byrne, T. B., & Johnson, C. W. (2018). Tidal Modulation and Tectonic Implications of Tremors in Taiwan. Journal of Geophysical Research: Solid Earth, 123(7), 5945–5964. https://doi.org/10.1029/2018JB015663

Ide, S. (2012). Variety and spatial heterogeneity of tectonic tremor worldwide. Journal of Geophysical Research: Solid Earth, 117(B3). https://doi.org/10.1029/2011JB008840

Todd, E. K., & Schwartz, S. Y. (2016). Tectonic tremor along the northern Hikurangi Margin, New Zealand, between 2010 and 2015. Journal of Geophysical Research: Solid Earth, 121(12), 8706–8719. https://doi.org/10.1002/2016JB013480

Wech, A. G., & Creager, K. C. (2008). Automated detection and location of Cascadia tremor. Geophysical Research Letters, 35(20). https://doi.org/10.1029/2008GL035458




