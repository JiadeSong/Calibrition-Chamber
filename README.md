# Calibrition-Chamber
* This pathon notebook is used to determine if the machines tested are in good condition by comparing with the calibration chamber audio. 
* The ideas are: 
 1. Use a *.csv* file (which contains the number of Audiomoth and SD card number) to guide the code to test the machines.
 2. Import the *.wav* audio file directly from the SD card and use UTC_timeDiff to take out the testing time period we want. 
 3. Process the audio file and transform it into a spectrum image in grey form. Then, it will be save in the oringinal folder in a form of *.jpg*. (code from Trieste's provious code)
 4. Functions, *getss* and *getdiff*, calculate the average and variance of a image and resize this image into a square with nxn blocks. Then, the greyness of every block will be prepared with the average of every row to grap the features of evert graph. 
 5. In *comparingfigure* function, 2 images are imported and differences of different images will be shown on a line graph.
 6. This code can detect SD cards in the computer and read them into the program by the order and information shown in *.csv*. 
 7. Mixed with the prvious code calib_v2.(code from Trieste's provious code)
 
### Warning: must ensure no files in the computer contain the same name strings of SD card names. 

* Instructions: 
 1. In the same dictionary of the code, create a *.csv* chart with the info of AM, SD and Notes seperated by comas.
 2. When starting the Audiomoths, record the UTC times (*playback_start*) which is simultaneously recorded into the machines before deploying. 
 3. In *Running all the scripts* chunk, input enter the *playback_start* time. 
 4. In *Calibrate* chunk, input the *.csv* name coresponding to the *playback_start* and the standart audio file path in your computer. (The standart audio file must have the same *playback_start* time with the testing file.)
 5. Input the lenth of time that you want to test in these audio files and input it in the *preprocess--duration* in seconds. 
 6. If you find the start-time of tagart sudio fragment starts a little earlier or later (less than 1s), which can be corrected in *preprocess--delay*. 
 7. If more feature points of the audio files are needed to increase the precision, the number can be adjusted in *getdiff--Sidelength*. 
 

