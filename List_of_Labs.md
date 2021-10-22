# List of Labs for UE Imaging Biological Systems

Repository of the UE Imaging Biological Systems - qbio master curriculum - University of Montpellier



[TOC]

## OVERVIEW

The UE Imaging Biological Systems is organized around three sections with increasing levels of complexity:

​	In section I. the students will be taught the good practices when handling potentially hazardous or fragile instruments and will learn how to align optics and characterize them. 

​	In section II. they will design and build an imaging setup (among which a TIRF, a confocal and an AFM). Then they will use it to run simple experiments.

​	In section III. the students will use advanced microscopes used routinely by researchers at CBS. They will design the experiment, participate in the sample preparation and then run the experiment and analyse the data.

| Sections | Hours | Status | Teachers | Description |
| ------------ |----| ------ | ------- | ----------- |
| I. Basics | 5h CM + 4h TP = 9 hours** |       |         | Safety & Good practices |
| II. Build a setup | 4h TD + 12h TP = **16 hours** |      |         | TIRF/Confocal/AFM |
| III. Practicals | 5h TD + ~2x5h TP = **15 hours** |      |         | SMLM/FCS/AFM |


## Timetable
**Instructors**:
ALG : Antoine Le Gall
CC : Caroline Clerté
CD : Christine Doucet
CG : Cédric Godefroy
EM : Emmanuel Margeat
JBF : Jean-Bernard Fiche
LC : Luca Costa
RQ : Robert Quast
PEM : Pierre-Emmanuel Milhiet



### Section #1-Basics
| Date | Schedule | Subject | Location | Instructors|
| ------------ |----| ------ | ------- | ----------- |
| 14/10/21 |11:00-12:00| Intro & Laser safety| CBS | CD,ALG,CC |
| 20/10/21 |09:00-13:00| TP : Optics basics| CBS | ALG |
| 22/10/21 |14:00-15:00| CM : Physics, Electronics, ... | CBS | LC        |
| 22/10/21 |15:00-16:00| CM : N&B and smFRET | CBS | EM        |
| 26/10/21 |09:00-11:00| TD : Optics basics tutorials| CBS | ALG |

### Section #2-Build a setup
| Date | Schedule | Subject | Location | Instructors|
| ------------ |----| ------ | ------- | ----------- |
| 29/10/21 |14:00-16:00| TD : Intro to building your setup| CBS | ALG, EM, LC |
| 10/11/21 |14:00-16:00| TD : Troubleshooting| CBS | ALG, EM, LC  |
| 17/11/21 |14:00-18:00| TP : Building your setup| CBS | ALG, EM, LC  |
| 18/11/21 |14:00-18:00| TP : Building your setup| CBS | ALG, EM, LC  |
| 19/11/21 |14:00-16:00| TP : Building your setup-acquisition| CBS | ALG, EM, LC  |
| 03/12/21 |09:00-11:00| Oral restitutions #1| CBS | ALG, EM, LC, CD  |

### Section #3-Practicals
| Date | Schedule | Subject | Location | Instructors|
| ------------ |----| ------ | ------- | ----------- |
| 02/12/21 |09:00-11:00| TD : Check exp design| CBS | JBF/CD/ALG, CC/EM, RQ/EM, LC/CG  |
| 07/12/21 |10:00-12:00| TP : Sample preparation| CBS | JBF/CD/ALG, CC/EM, RQ/EM, LC/CG  |
| 07/12/21 |13:00-17:00| TP : Acquisition #1| CBS | JBF/CD/ALG, CC/EM, RQ/EM, LC/CG  |
| 08/12/21 |10:00-12:00| TP : Sample preparation| CBS | JBF/CD/ALG, CC/EM, RQ/EM, LC/CG  |
| 08/12/21 |13:00-17:00| TP : Acquisition #2| CBS | JBF/CD/ALG, CC/EM, RQ/EM, LC/CG  |
| 07/01/22 |14:00-16:00| Oral restitutions #2| CBS | JBF/CD/ALG, CC/EM, RQ/EM, LC/CG  |
## List of all Labs 



### I. Basics - 9h

[readme](Tutorials_Optics_basics/Tutorials_Optics_basics.pdf)

* CM 1h : [Laser safety](/Intro_Laser_safety/Laser safety class.pdf) + optics handling + objective nomenclature + good practices
* TP 4h (3 groups) : 
  * Good practices = how to align a laser, lens, iris, targets, etc...
  * Set up a telescope (Keplerian vs Galilean telescope)
  * Measure a laser beam waist and divergence
  * Identify laser polarization (linear, circular, ...)
  * Check dichroic transmission with angle?
  * Measure a laser beam spectrum vs LED vs white light?
  * oscilloscope ? ...

* CM : 4h

  * Piezoelectric
  * Electronic

  * smFRET
  * N&B

### II. Build a setup - 14h

| Setup | Experiments | Instructors | Comments |
| ----- | ----------- | -------- | ----------- |
| TIRF build+calibrate (beads, grid) | Image nuclear pore complex and cell membrane in Epi vs TIRF | Antoine |             |
| Confocal build+calibrate | Characterize concentration of free dyes in solution | Manu ||
| AFM build+calibrate | Image lipid bilayers? Cell membrane | Luca ||

* TD 2h Introduction 

  *  Optics formula to characterize the system:
     *  Size BFP, objective focal length, objective FOV
     *  Beam expansion (FOV illumination or BFP coverage)
     *  Nyquist (cam pix size)
     *  
  *  Optical aberrations and how to identify them:
     *  spherical, 
     *  astigmatism, 
     *  coma, 
     *  chromatism, 
     *  etc...
  *  Setup simulation tools
  *  Fiji + others ? (Gwyddion ?)
  *  

  --> homework : design setup ~4h

* TD 2h Design troubleshooting

* TP 8h (3 groups) : Build setup 

* TP 2h  (3 groups): Run simple experiment 

  --> homework : prepare restitution ~4h
  
* Oral restitution + written report + demo other groups (4h)
=> the goal is to have all the groups being familiarized with all setups (to start preparing the second session of TPs). The binome who built the setup will explain and guide the others to use their setup and run an acquisition.

### III. Practicals - 14h



| Technique | Sample Preparation | Experiment | Instructors |
| ---- | ------ | ------- | ----------- |
|  AiryScan-PALM  | Nuclear pore complex : labeling | Super resolution | JBF/CD(/ALG?) |
|  FCS-N&B    | Dyes solution, bacteria samples | volume and diffusion time characterization, oligomerization state | CC |
| TIRF-FRET          | GPCR mGluR purif and labeling| Conformation dynamics | RQ, EM|
|  AFM-FLIM  | Lipid bilayers with bodipy labeling | Topography, force measurements, life time measurements | CG/PEM |

* CM 15min :  Sample mounting / preparation

* TD 2h : Design experiment

  ​	--> TD: check design (sample preparation, which dyes, read papers, acquisition conditions, expected results and analysis...)

* TP 2h : sample preparation #1

* TP 4h : acquisition #1

* TP 2h : sample preparation #2

* TP 4h : acquisition #2

* Data analysis + report preparation

* Oral restitution + written report


| TP | Experiment | Analysis tools |
| ---- | ------ | ------- |
| STORM | NPC | Reconstruction with Thunderstorm |
| N&B | strains UE SynBio + Rho | Patrack |
|  smFRET     |     mGluR                    |   ?  |
|    AFM+FLIM   |           ?              |       ?                           |
|       |                         |                                  |
