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

What is SNR ? [video](https://www.google.com/search?q=signal+to+noise+ratio+fluorescence+microscopy&sca_esv=8482df87b229566e&sxsrf=AE3TifNCifrLtNLhK0aGvF9-saanBtyTUg%3A1758528109698&ei=bQLRaNWzKof6nsEP34qJsA4&oq=signal+to+noise+ratio+fluorescence+&gs_lp=Egxnd3Mtd2l6LXNlcnAiI3NpZ25hbCB0byBub2lzZSByYXRpbyBmbHVvcmVzY2VuY2UgKgIIATIGEAAYFhgeMgYQABgWGB4yBhAAGBYYHjIGEAAYFhgeMggQABiABBiiBDIFEAAY7wUyBRAAGO8FMgUQABjvBTIIEAAYgAQYogRIgA9QfVh9cAF4AJABAJgBYqABqQGqAQEyuAEDyAEA-AEBmAICoAJzwgIKEAAYsAMY1gQYR5gDAIgGAZAGBpIHAzEuMaAH_QmyBwMwLjG4B2rCBwUyLTEuMcgHDg&sclient=gws-wiz-serp#fpstate=ive&vld=cid:00690878,vid:mGPJBNsq7bA,st:0)

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



*Bonus*: here, writing a script in Python will allow you to analyze the 2000 frames, detect all the single molecules from the entire stack, fit them with Gaussians and extract the sigma. => you will get a more precise description of your PSF. 



## 7. A few words on other types of data (1D)





## Take-home messages

- 