# Data analysis

Christine Doucet   

[doucet@cbs.cnrs.fr](mailto:doucet@cbs.cnrs.fr)

Report due : **10/10/25** as a pdf file, sent by email to the above address.



## Aim of this course :

***Get the fundamental notions and tools to exploit, analyze and present the data you will get during the BioImaging practicals.***

- what is an image ?

  - what are the important parameters to know about an image in order to extract quantitative information ?
  - How to display these parameters when making a figure ?

- what is the structure of the image and the different formats ?

- manipulate stacks

- measure pixel size and save it

- measure SNR

- measure PSF

  

***What we expect in your report:***

- *at minima* : 

  - Explain what we have done together during the course - you can follow the structure of this document. 
  - Explain the concepts, the procedure 
  - Present data in figures with legends and all useful information. Make figures to explain how you analyzed the images and plot the results of your analyses when appropriate. Make sure all the required information is displayed in your figure and/or its legend (scale bar, color scale when appropriate, channel, sample, axes, units, statistics...)

- *bonus* : Extrapolate some of the analyses using Python. **<u>This part is not mandatory !</u>** But for the future practicals (and your life as a scientist !!), this will be very helpful, in particular to automatize some procedures and build analysis pipelines.

  

## 1. What is an image ?

A matrix, with each cell of the matrix (= pixel) that contains a quantitative information (height, intensity, nb of photons…)

To analyze the information within the image, we need to characterize a number of parameters inherent to the images / microscope:

- pixel size ⇒ spatial scale
- color-scale (nb of photons, height, lifetime…)
- noise (different sources of noise)

- SNR
- PSF
- what are the metadata ?

You will find three image files in the Github repository  \InLab-Data-analysis\Data\

- a widefield image of a calibration grid => measure the pixel size, in the sample plane, of a given setup.
- a stack of images of a cell expressing nuclear pores fused to GFP. 
- a stack of images of the same cell, acquired in DNA-PAINT (SMLM). Channel = cy3b, time stack = 2000 frames.
- there are also 2 txt files, that contain the metada of the image files.



## 2. How to open an image ?

- what is the structure of different types of images (tif, jpg) ?

Differences Between **JPG**, **PNG** and **TIFF**

| Feature            | **JPG (JPEG)**                             | **PNG**                                                 | **TIFF**                                     |
| ------------------ | ------------------------------------------ | ------------------------------------------------------- | -------------------------------------------- |
| **Compression**    | Lossy (details discarded for smaller size) | Lossless (no data loss)                                 | Lossless or uncompressed (supports both)     |
| **File size**      | Smallest                                   | Larger than JPG, smaller than TIFF                      | Often very large                             |
| **Bit depth**      | Typically 8-bit per channel                | 8-bit or 16-bit per channel                             | 8, 16, 32-bit per channel (flexible)         |
| **Channels**       | RGB (3), sometimes grayscale               | Grayscale, RGB, RGBA (supports transparency)            | Grayscale, RGB, RGBA, multispectral          |
| **Transparency**   | ❌ Not supported                            | ✅ Alpha channel supported                               | ✅ Can support alpha                          |
| **Multi-page**     | ❌ Single image only                        | ❌ Single image only                                     | ✅ Can store multiple pages/frames            |
| **Color profile**  | Commonly sRGB                              | Supports color profiles                                 | Supports ICC profiles, metadata-rich         |
| **Best use cases** | Photography, web, social media             | Web graphics, icons, logos, images needing transparency | Scientific imaging, medical scans, archiving |
| **Performance**    | Very fast to load and display              | Fast, but larger size than JPG                          | Slower, especially with very large file      |
|                    |                                            |                                                         |                                              |

<u>**Quick takeaways:**</u>

- **JPG** → Best for **photos where size matters** (social media, websites, cameras).
- **PNG** → Best for **graphics with sharp edges or transparency** (logos, icons, screenshots).
- **TIFF** → Best for **scientific/archival quality** (medical imaging, remote sensing, publishing).



[] Open the **GFP.tif** file in Image J.

[] Understand and describe the structure of the image.

[] what is the file format ? the image type ? how many frames ? px size ? Where can you find this information ?



## 3. Manipulation of stacks

Using the **GFP.tif** image you just opened:

[] split stack in two sub-stacks

[] concatenate again the 2 sub-stacks

[] z-project the stack ⇒ max, min, average, sum, std

- What is the difference (conceptually)? 
- Display the different results
- Comment
- If you want to analyze the intensity of GFP across pores, what type of projection should you use ?



## 4. Measure the pixel size

What do we need to measure the pixel size from a microscopy system ?

[] Open the **pixel_size_10um.tif** file. What is it ? How can you use it to measure the pixel size of the setup taht was used to acquire this image ?

[] measure the px size from the calibration grid image

- use the line tool in ImageJ
- trace a line profile, measure from two peaks
- calculate the px size

- calculate the size of the FOV

  

## 5. Calculate SNR

What is SNR ? [video](https://www.google.com/search?sca_esv=8482df87b229566e&sxsrf=AE3TifM87_5mn5mf80Gk4FBu244zQLRNdQ:1759142629519&udm=7&fbs=AIIjpHx4nJjfGojPVHhEACUHPiMQ_pbg5bWizQs3A_kIenjtcpTTqBUdyVgzq0c3_k8z34EAuM72an33lMW6RWde9ePJUaUO3wWcgaT7PNi5dBZP8ljuTG1cA8EPe4ubs9oo4f7I8cfVU7zyjvBef49SeNNlyxHdnQOllfsLSGSugRKfYBQ03R2CRSn-X7_Q-1QkYdGSLDgS&q=signal+to+noise+ratio+fluorescence+microscopy&sa=X&ved=2ahUKEwiBvar85P2PAxWXcKQEHfQTHZ4QtKgLegQIEBAB&cshid=1759142718879362&biw=1513&bih=853&dpr=1#fpstate=ive&ip=1&vld=cid:52762fd3,vid:mGPJBNsq7bA,st:0)

[] what is SNR ? How would you calculate it ?

Using what you have done before:

[] Measure the SNR from the **GFP.tif** file. Explain how you proceed.

[] Repeat this measurement from the Average projection.

[] Comment on the relevance of these two measurements.



## 6. Measure the PSF of a microscope

[] what is a PSF ? How is it usually approximated ? Consequently, what characteristic measurement will you use to describe the PSF ?

[] Open the **Nup107.tif** file. What do you see ? 

[] From this file, how can you measure the PSF of the microscope ? Justify and explain how you will proceed. 

[] Measure the PSF from at least ten single molecules. Plot the results.



*Bonus*: here, writing a script in Python will allow you to analyze the 2000 frames, detect all the single molecules from the entire stack, fit them with Gaussians and extract the sigma. => you will get a more precise description of your PSF. use the Astropy library to detect local maxima.



## 7. Manipulating channels

The tools to play with different channels are located in Image>Color

[ ] Make three substacks of 30 images in the **Nup107.tif** stack.

[ ] make average projections of each substack.

[ ] overlay the three resulting projections in RGB.

[ ] repeat the same process with the **GFP.tif** stack.

What do you observe ?

*When overlaying different channels, the different colors used must be clearly identified.* 



## 8. Changing the LUT - Adding scale and calibration bars

The LUT (Look Up Table) defines the range of colors attributed to ranges of pixel values. It can be uniform (grey levels, greens...). In this case, the intensity directly reflects the px value. If it is multicolour, a calibration bar is necessary to interpret the color scale.

To change the LUT, go to Image>LookUpTables

The scale bar is required to understand the size of the objects present in the image. The calibration bar is not mandatory, in particular if the information embedded in the images is fluorescence intensity. However in some cases, it si required. The scale and scale unit must be present either directly close to the scale bars, or indicated clearly in the figure legend. 

To insert scale bars or calibration bars, go to Analyze>Tools.

[] open the **GFP.tif** image

[] apply a standard deviation projection.

[] change the LUT to fire.

[] add a scale bar and a calibration bar



## 9. A few additional useful manipulations

- Cropping / duplicating a ROI
- Scaling up and down
- drawing
- using the ROI manager
- adjusting levels
- plotting histograms
- recording tasks to write simple macros



## Take-home messages

- When you acquire images, make sure the signals are not saturated, that the important metadata are saved or written down in the lab book, save in tiff format.
- When you manipulate your images, keep in mind what you want to do with them and be careful with levels, scales, etc...
- ALWAYS KEEP YOUR RAW DATA.
- Include as much information as possible in your image (channel, scale bar with units, calibration bar...). If not directly included in the image, make sure that the information is present in your legend. But having everything in your image really helps when you want to re-use figures of your written report in your presentation for instance...
- Include all the useful information in the legend (type of sample, is it fixed or live ? type of imaging, experimental conditions, how quantifications were performed, on how many cells, from how many distinct experiments, incude statistics...)

