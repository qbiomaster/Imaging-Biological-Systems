## Aim of the InLab :

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

You will find three image files in the Github repository

- a widefield image of a calibration grid => measure the pixel size, in the sample plane, of a given setup.
- a stack of images of a cell expressing nuclear pores fused to GFP. Channel = GFP, time stack = 100 frames.
- a stack of images of the same cell, acquired in DNA-PAINT (SMLM). Channel = cy3b, time stack = 2000 frames.



## 2. How to open an image ?

- what is the structure of different types of images (tif, jpg) ?

Differences Between **JPG** and **TIFF**

| Feature          | JPG                       | TIFF                                          |
| ---------------- | ------------------------- | --------------------------------------------- |
| **Compression**  | Lossy (some detail lost)  | Can be lossless (or even uncompressed)        |
| **Bit depth**    | Usually 8-bit per channel | Can be 8, 16, 32-bit per channel              |
| **Channels**     | Typically 3 (RGB)         | Can store grayscale, RGB, RGBA, multispectral |
| **Pages/Frames** | Single image only         | Can store multiple images (multi-page TIFF)   |
| **Use cases**    | Photography, web          | Scientific imaging, medical scans, archives   |
| **File size**    | Small                     | Large                                         |

 **Summary**:

- If you’re working with **normal images/photos**, JPG is fine => only use it to display images in a report for instance. If you want to extract quantitative data from your images, use TIFF format.
- If you’re handling **scientific or high-fidelity images**, TIFF is preferred because it supports higher bit depth and lossless storage.



[] find the most straightforward procedures to open them in Python, what is the structure of the output ?

- in ImageJ

- in Python

  

## 3. Manipulation of stacks

- split stacks
- concatenate stacks
- z-project ⇒ max, min, average, sum, std
- comment

In ImageJ, bonus : do it in Python



## 4. Measure pixel size

- [x]  find an image of a calibration grid + information

What do we need to measure pixel size from a microscopy system ?

- measure px size from a calibration grid image

  - use the line tool in ImageJ
  - trace a line profile, measure from two peaks
  - calculate the px size

- calculate the size of the FOV

  

## 5. Calculate SNR

What is SNR ? [video](https://www.google.com/search?q=signal+to+noise+ratio+fluorescence+microscopy&sca_esv=8482df87b229566e&sxsrf=AE3TifNCifrLtNLhK0aGvF9-saanBtyTUg%3A1758528109698&ei=bQLRaNWzKof6nsEP34qJsA4&oq=signal+to+noise+ratio+fluorescence+&gs_lp=Egxnd3Mtd2l6LXNlcnAiI3NpZ25hbCB0byBub2lzZSByYXRpbyBmbHVvcmVzY2VuY2UgKgIIATIGEAAYFhgeMgYQABgWGB4yBhAAGBYYHjIGEAAYFhgeMggQABiABBiiBDIFEAAY7wUyBRAAGO8FMgUQABjvBTIIEAAYgAQYogRIgA9QfVh9cAF4AJABAJgBYqABqQGqAQEyuAEDyAEA-AEBmAICoAJzwgIKEAAYsAMY1gQYR5gDAIgGAZAGBpIHAzEuMaAH_QmyBwMwLjG4B2rCBwUyLTEuMcgHDg&sclient=gws-wiz-serp#fpstate=ive&vld=cid:00690878,vid:mGPJBNsq7bA,st:0)



## 6. Measure PSF

Use the stack of SMLM.

- what is a PSF ?





*Bonus*: here, writing a script in Python will allow you to analyze the 2000 frames, detect all the single molecules from the entire stack, fit them with Gaussians and extract the sigma. => you will get a more precise description of your PSF.

## 7. A few words on other types of data (1D)

- [ ]  find FCS curves (1 and 2 components)
- [ ]



## Take-home messages

- 