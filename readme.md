# Tutorial for phyllotaxy images analysis

## Introduction 

Here we aim to evaluate the maize plant canopy orientation by directly measure azimuthal leaf orientations from top view UAV images.
Each image normally contains four rows of plants with same genotype. The middle two rows will be selected for the measurement.
The relative angles to the planting row of the top-most leaves from each side of a plant are then measured using imageJ. This enable us to display the distribution of the azimutal angles of these leaves in a polar chart.

As shown in the following image, the mutant and its relative wild type control exhibit different canopy orientation.

![](images/Presentation1.jpg)

## Chapters

1. Image analyses
2. Codes for polar charts
3. Codes for statistic analysis 

#  Chapter 1 Image Analyses

In each image, angles of azimuthal canopy orientation were measured from N (normally 6 plants) consecutive plants from each of the two middle rows of four-row plots. These plants exhibited the typical alternate-distichous phyllotaxy of maize. The top-most fully expanded leaf was selected from each side of each plant (Supplemental Figure S22). Thus 2N plants, i.e., 4N leaves per genotype per replication, were measured.

For 60 DAP plants, where the tassel can be seen in the image. The three top-most leaves, the flag leaf and the two leaves below the flag leaf, were in most instances still upright and not fully expanded and thus were not measured. As a result, the measured leaves were typically the third and fourth leaves below the flag leaf. The younger stages plants, such as 50 or 40 DAP, there would normally 4 to 5 leaves that were not fully expanded and shall be skipped for data collection. Thus, it would be the topmost and second topmost collar leaves that were collected for plants at 40 or 50 DAP. 

Beginning at the axis of planting, the counterclockwise angle between the axis of planting and the midrib (Supplemental Figure S22) was measured for each selected leaf, using the angle measurement function of ImageJ software (https://imagej.nih.gov/ij/). 

A measured sample can be found at W22.csv which shall looks like folowing:

![image](https://github.com/cndkczy/Tutorial/assets/16928387/a208366f-d9c5-4e0b-a6ce-7202f34db286)



