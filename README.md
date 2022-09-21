# List of Labs for UE Imaging Biological Systems 2022-2023

Repository of the UE Imaging Biological Systems - qbio master curriculum - University of Montpellier



[TOC]

## OVERVIEW

The UE Imaging Biological Systems is organized around three sections with increasing levels of complexity:

​	In section I. the students will be taught the good practices when handling potentially hazardous or fragile instruments and will learn how to align optics and characterize them. 

​	In section II. they will design and build an imaging setup (among which a TIRF, a confocal or an AFM). Then they will use it to run simple experiments.

​	In section III. the students will use advanced microscopes used routinely by researchers at CBS. They will design the experiment, participate in the sample preparation and then run the experiment and analyse the data.

| Sections | Hours | Evaluations | Teachers | Description |
| ------------ |----| ------ | ------- | ----------- |
| I. Basics | 5h CM + 4h TP = 9 hours** | None |         | Safety & Good practices |
| II. Build a setup | 4h TD + 12h TP = **16 hours** | Written report + oral restitution |         | TIRF/Confocal/AFM |
| III. Practicals | 5h TD + ~2x5h TP = **15 hours** | Written report + oral restitution |         | SMLM/FCS/AFM |


## Timetable
**Instructors**:
ALG : Antoine Le Gall
CC : Caroline Clerté
CD : Christine Doucet
CG : Cédric Godefroy
EM : Emmanuel Margeat
JBF : Jean-Bernard Fiche
LB: Léo Bonhomme
LC : Luca Costa
RD : Rémi Doré
RQ : Robert Quast
PEM : Pierre-Emmanuel Milhiet



### Section #1-Basics
| Date | Schedule | Subject | Location | Instructors|
| ------------ |----| ------ | ------- | ----------- |
| 12/10/22 | 09:00-11:00 | TD : [Optics basics tutorials](Tutorials_Optics_basics/Tutorials_Optics_basics.pdf) | Bungalow | ALG |
| 12/10/22 |11:00-12:00| CM : [Laser safety](/Intro_Laser_safety/Intro_Laser_safety.pdf) | Bungalow | CC |
| 14/10/22 |14:00-16:00| CM : [N&B](Number_and_brigthness/Number_and_brigthness.pdf) and [smFRET](smFRET/smFRET.pdf), [Electronics](Electronics/qbio_UE_introduction_electronics.pdf), ... | Bungalow | EM, LC    |
| 19/10/22 |09:00-13:00| TP : [Optics basics](Pratical_Optics_basics/TP_optics_basics.pdf) | qBio | ALG      |
| 25/10/22 |09:45-13:00| TP : BioImaging | CBS | EM |

### Section #2-Build a setup
| Date | Schedule | Subject | Location | Instructors|
| ------------ |----| ------ | ------- | ----------- |
| 26/10/22 |14:00-16:00| TD : Intro to [building your setup](Build_your_setup/Build_your_setup.pdf) | Bungalow/Conference room/Meeting room | ALG, EM, LC |
| 09/11/22 |14:00-16:00| TD : Troubleshooting| qBio/Confocal/AFM | ALG, EM, LC  |
| 18/11/22 |14:00-18:00| TP : [Building your setup](Build_your_setup/Build_your_setup.pdf) | qBio/Confocal/AFM | ALG, EM, LC  |
| 22/11/22 |14:00-18:00| TP : [Building your setup](Build_your_setup/Build_your_setup.pdf) | qBio/Confocal/AFM | ALG, EM, LC  |
| 23/11/22 |14:00-16:00| TP : [Building your setup](Build_your_setup/Build_your_setup.pdf)-acquisition | qBio/Confocal/AFM | ALG, EM, LC  |
| 02/12/21 |14:00-17:00| Oral restitutions #1| Conference room | ALG, EM, LC, CD  |

### Section #3-[Practicals](Practicals_Advanced_microscopy/Practicals_Advanced_microscopy.pdf)
| Date | Schedule | Subject | Location | Instructors|
| ------------ |----| ------ | ------- | ----------- |
| 06/12/22 |14:00-16:00| TD : Check exp design| CBS | JBF/CD, CC, RQ/LB, RD/CG |
| 08/12/22 |10:00-12:00| TP : Sample preparation| CBS | JBF/CD, CC, RQ/LB, RD/CG |
| 08/12/22 |13:00-17:00| TP : Acquisition #1| CBS | JBF/CD, CC, RQ/LB, RD/CG |
| 09/12/22 |10:00-12:00| TP : Sample preparation| CBS | JBF/CD, CC, RQ/LB, RD/CG |
| 09/12/22 |13:00-17:00| TP : Acquisition #2| CBS | JBF/CD, CC, RQ/LB, RD/CG |
| 06/01/23 |14:00-17:00| Oral restitutions #2| Conference room | JBF, CD, ALG, CC, EM, RQ, LB, LC, CG, RD |
## List of all Labs 



### I. Basics - 9h

* CM 1h : [Laser safety](/Intro_Laser_safety/Intro_Laser_safety.pdf) + optics handling + objective nomenclature + good practices
* TP 4h (3 groups) : [Optics basics](Pratical_Optics_basics/TP_optics_basics.pdf)
  * Optics alignment
  * Diffraction and polarisation
  * Spectroscopy

* CM : 4h
  * [Electronics](Electronics/qbio_UE_introduction_electronics.pdf)
  * [N&B](Number_and_brigthness/Number_and_brigthness.pdf) 
  * [smFRET](smFRET/smFRET.pdf)

### II. [Building your setup](Build_your_setup/Build_your_setup.pdf) - 14h

| Setup | Experiments | Instructors | Comments |
| ----- | ----------- | -------- | ----------- |
| TIRF build+calibrate (beads, grid) | Image nuclear pore complex and cell membrane in Epi vs TIRF | ALG |             |
| Confocal build+calibrate | Characterize concentration of free dyes in solution | EM ||
| AFM build+calibrate | Image lipid bilayers? Cell membrane | LC ||

* --> homework : prepare restitution ~4h

* Oral restitution + written report + demo other groups (4h)
=> the goal is to have all the groups being familiarized with all setups (to start preparing the second session of TPs). The binome who built the setup will explain and guide the others to use their setup and run an acquisition.

### III. [Practicals](Practicals_Advanced_microscopy/Practicals_Advanced_microscopy.pdf) - 14h



| Technique | Sample Preparation | Experiment | Instructors |
| ---- | ------ | ------- | ----------- |
|  AiryScan-PALM  | Nuclear pore complex : labeling | Super resolution | JBF/CD(/ALG?) |
|  FCS-N&B    | Dyes solution, bacteria samples | volume and diffusion time characterization, oligomerization state | CC |
| TIRF-FRET          | GPCR mGluR purif and labeling| Conformation dynamics | RQ, EM|
|  AFM-FLIM  | Lipid bilayers with bodipy labeling | Topography, force measurements, life time measurements | CG/PEM |

* 

* Data analysis + report preparation

* Oral restitution + written report

