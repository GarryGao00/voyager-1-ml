# voyager-1-ml
Use machine learning techniques to analyze the Voyager-1's Plasma Wave Spectrometer Waveform



#### Before cloning this repository

1. Download the needed data from UIowa's server at /opt/project/voyager/data/dust/interplanetary/voyagerN/
2. Read ./other-materials/readme.txt, which is also included in the data/ folder you just downloaded
3. Read ./other-materials/v1_dust_impact_time.pdf. This is the hit record in pdf format



#### How to use this repository

**cdf_read_test.ipynb**: The files from the data/ folder are in the format of .cdf. Use cdf_read_test.ipynb to test read one of the .cdf files. 

**dust_impact_time_to_excel.ipynb**: Use this notebook to generate a cleaned Excel sheet containing all the dust impact/hit timestamps from data/hits/ folder. This notebook generates files like *voyager1-impacts-unique.xlsx*. 

**read_in_impact_excel.ipynb**: Use this notebook to read timestamps from the Excel sheet you just created. Then you can draw the corresponding CDF files using the timestamps to visually check if the timestamp is correct. This notebook also generates two CSVs recording the time waveforms during hits and non-hits, *hit.csv* and *non_hit.csv*. 

**voyager-1-ml-train-test.ipynb**: This notebook trains a PyTorch model based on the hits you found. Generates a model named *voyager_dust_impact_4layer_model_v1.pt*

**test_cdfs.ipynb**: This notebook utilizes the model just created to classify CDFs if they contain hits. It also saves the predicted hits as png images in folder temp/.
