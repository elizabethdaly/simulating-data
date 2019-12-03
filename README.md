# Simulation of a dataset using Python
## Elizabeth Daly

### HDip Data Analytics 2019 Programming for Data Analysis Project

- Git-hub repository at: https://github.com/elizabethdaly/simulating-data.git

- Jupyter notebook: **eyesight.ipynb**

![NumPy](images/numpy_logo.png)

# Table of contents
1. [Introduction](#intro)

2. [Myopia](#section2)

3. [Factors associated with myopia](#section3)

4. [Variables](section4)
    
5. [Generating the data set](#section5)
    
6. [blah 6](#section6)
    
7. [Conclusions](#conclusions)

8. [References](#references)

## 1. Information <a name="intro"></a>
- This README describes work done for the Programming for Data Analysis module project, due 13 December 2019. 
- Resources used include Python and associated packages Jupyter, matplotlib, and NumPy. These come as part of the Anaconda distribution of Python.
- The analysis takes the form of a single Jupyter notebook of filename given above. To view this file, download it from this repository and start Jupyter notebook from the folder containing the file: type **Jupyter notebook** on the command line.
- Alternatively, view a static version of the notebook (by providing its GitHub url) using Jupyter Nbviewer.
- All images intended for inclusion in this README are located in the **images** subdirectory of this repository.
- I would like for this README to complement the analyses performed in the notebook rather than just repeat what's done there.

## 2. Myopia <a name="section2"></a>
In this notebook I wish to create a data set of variables associated with short-sightedness, or myopia. One of the questions  I would like to address is: what is the distribution of short-sightedness (myopia) in a random sample of the population? I would also like to explore the relationships, if any, between factors which seem to contribute to myopia.

### What is myopia?
Myopia is also referred to as short-sightedness or near-sightedness. I will stick to using the term myopia as it saves a bit of typing. It happens mainly because the eyeball grows too long so that distant objects appear blurry while only very close objects are sharp. It happens because light entering the eye comes to a focus in front of (rather than on) the back of the eye - the retina. This means that the clearest image of the object is formed in front of the retina rather than on it, where our brain records images. It is a refractive error of the eye: as light travels through the eye it is bent (refracted) and absorbed by the different structures it passes through, primarily the cornea and the lens. The cornea is the front surface of the eye and the lens is a transparent element behind the iris that helps to bring light to a focus. If the end result is that the light from an object comes to a focus away from the retina, then that person has a refractive error. In myopia light from distant objects comes to a focus in front of the retina.

<!--![myopia](images/myopia-and-normal.jpg)-->
<p align="center"> 
    <img src=images/myopia-and-normal.jpg>
 </p>

There are other common refractive errors apart from myopia. These include hyperopia (light comes to a focus behind the retina) and astigmatism (light in different planes comes to a focus at different points). A person with normal vision is emmetropic or, an emmetrope. The different refractive errors are illustrated below.

<!--![refErrors](images/Refractive-states-web.jpg)-->
<p align="center"> 
    <img src=images/Refractive-states-web.jpg width="400" height="300">
 </p>

Myopia, hyperopia, and astigmatism are easily corrected by optometrists who prescribe glasses or contact lenses of the correct power. In recent decades, laser eye surgery has also become very popular as a way to permanently correct these refractive errors for suitable candidates. It does so by re-shaping the surface of the cornea, changing its shape, and therefore changing how light is refracted as it travels through the front of the eye. On the surface it seems like an attractive option, but it is permanent and not without its own risks.

### How is it quantified/corrected?
Refraction is measured in units called Dioptres (D), which is the reciprocal of focal length f measured in metres: D = 1/f(m). For example, 1 D = 1/(f=1m), 2 D = 1/(f=0.5m), 3 D = 1/(f=0.33m) and so on. So a 5 D lens would focus light at 1/5 = 0.2 m. For a person with normal vision, the combined power of the lens and cornea is 60 D (meaning the human eye focal length is approximately 17 mm). The amount of myopia is quantified by the power of the lens required to correct it (move the best focus back onto the retina). Negative values are needed to correct myopia so a sort-sighted person might have a prescription of -2 D perhaps. Conversely, a person with hyperopia (far-sighted) will have a positive prescription.  The severity of myopia is quantified as follow:

| Degree    | Amount (D)    |
| :---------|:-------------:|
| Low       | 0 to -3       |
| Moderate  | -3 to -6      |
| High      | more than -6  |

The current threshold value for myopia is a refractive error of less than or equal to -0.50 D. So someone with a -0.25 D error is not technically short-sighted. Lenses used for myopia correction usually come in 0.25 D steps - the closest one to a patient's prescription is used. The image below shows how a negative (concave) lens is used to correct myopia.

<p align="center"> 
    <img src=images/myopia-verses-myopia-corrected.png>
 </p>

### Why this question?
I'm interested in this question on a personal level because my teenage daughter has myopia. She started wearing glasses when she was nine years old, and every year her prescription went up a little, as expected. However, when she was 14 years old her eyesight deteriorated and her prescription almost doubled in just 10 months. By that stage she had the same prescription as her dad. Myopia progresses as you (and your eyeballs) grow, so if she continued on this track her optometrist speculated that she could end up at -5 or -6 D by the time she had finished growing. She is now wearing myopia correcting contact lenses for six days out of every seven, in an attempt to slow her myopia progression. These lenses have a central pupil which provides correction in the same way as ordinary contact lenses do. However, they also have a peripheral ring on the outside edge of the lens, where the correction is lower so that light from this part of the lens comes to a focus in front of the retina. Somehow, (I haven't been able to find the exact detail of how they work), this discourages growth of the eyeball and therefore slows myopia progression. They appear to be working - fingers crossed.

I'm also interested in this subject on a professional level because for many years I worked as a physicist building instruments to take very high-resolution images of the human eye. Light travelling from the retina out of the eye to form an image in a camera is affected by refractive errors in the same way as light coming into the eye. So errors like focus and astigmatism above, along with ones that have higher spatial frequencies, can degrade the quality of retinal images. I  measured higher order refractive errors in the eye and attempted to correct them using active optics. These are errors which cannot be compensated for using lenses, as they have complicated spatial patterns when measured over the pupil of the eye. The aim of that research was not to improve vision, rather to improve the quality of images of the retina.

There appears to be a very strong genetic component to myopia. Among my five siblings, only one started wearing glasses as a child, but my husband and all three of his siblings did. Typically, a child who has myopia will end up with more of it than their parent/s. So it progresses with each generation. Nowadays, one in four people have some degree of myopia and it appears to be becoming more prevalent. It is estimated that, if current trends continue, half of the world's population could have myopia by 2050. I'm interested in the reasons for this.

### What are the risks associated with myopia?
It is inconvenient to wear glasses or contact lenses every day, especially for someone who does a lot of sports; I can't imagine not being able to see clearly when swimming, for example. Apart from this, there are also more serious consequences of having high myopia. In later life it is associated with an increased risk of retinal detachment, glaucoma, cataracts and other types of damage in the central retinal area. This higher risk comes from having a longer eyeball where the tissues are thinner and stretched; this thin tissue is more susceptible to tears, inflammation, weak blood vessels, and scarring. These pose serious threats to eyesight.

## 3. Factors associated with myopia <a name="section3"></a>
Some of the factors which contribute to, or are associated with, myopia include:
- Genes; one is much more likely to by myopic if one or both parents are. this might be a categorical variable with values 0, 1, 2 reflecting no, some, or strong genetic predisposition. 
- The amount of close work done such as reading, screens, mechanical work can influence the progression of myopia. This would be a continuous numerical variable.
- There is some evidence to suggest that increasing the amount of time spent outdoors may have a protective effect against myopia. Another continuous numerical variable.
- It's unusual for young children to develop myopia. It's usually picked up towards the end of primary school. So, there must be some association with age - a positive integer.
- Education may play a role. Those with more education have spent more time doing close work, so it could be associated with level of education. The level might be a categorical variable of value primary, secondary, third.
- Socio-economic status may also be a factor. In a sweeping generalization, I would say that those of higher social class are more likely to progress to higher levels of education, therefore spending more time doing close work (less time outside), possibly increasing the progression of myopia, *if* the genetic predisposition is already there. Social class would be a categorical variable reflecting the, apparently, seven levels: elite, established middle class, technical middle class, new affluent workers, traditional working class, emergent service workers, and precariat. 
- Gender is a possible option, not because one gender is more or less likely to be myopic, just because it is a common thing to record when taking a random sample of people. A M, F categorical variable.
- The measure of myopia, refractive error, is the most important variable associated with myopia. This is a numerical variable, negative in value, and containing two decimal places.

For this project I am going to examine four variables, and in the next section I investigate each of them in detail. The variables I have chosen are: 
1. Genes
2. Refractive error (or prescription)
3. Age
4. The environmental factor of hours spent outside over some fixed period.

## 4. Variables <a name="section4"></a>

### 4.1 Genes
blah

### 4.2 Refractive error

### 4.3 Age

I would like to simulate the distribution of ages in a population. 

<p align="center"> 
    <img src=images/census2016_popPyramid.JPG>
 </p>

### 4.4 Environmental factors

As I imagine what the final data set might look like I'm thinking: what would a Seaborn pairplot look like? I might expect
- RE to be related to age (starts in childhood, progresses with growth, decreased in older people)
- RE to be related to genes. Maybe data from the three genes variables would be clustered in groups?
- Hours outside to be related to age - maybe decreases as get older? See Child in the City below.
- Hours outside to decrease as close work increases?


## 5. Generating the data set <a name="section5"></a>
## 6. blah 6 <a name="section6"></a>
## 7. Conclusions <a name="conclusions"></a>
## 8. References <a name="references"></a>

**General:**

- [1]  Anaconda Distribution
https://www.anaconda.com/
- [2] Python Software Foundation
https://www.python.org/
- [3] Project Jupyter
https://jupyter.org/
- [4] Sharing Jupyter notebooks
https://nbviewer.jupyter.org/
- [5] matplotlib: Python plotting library
htts://matplotlib.org/
- [6] NumPy
https://numpy.org/
- [7] GitHub
https://github.com/
- [8] Python for Data Analysis: Data Wrangling with Pandas, NumPy, and IPython. 
Wes McKinney. ISBN-13: 978-1491957660 ISBN-10: 1491957662
- [9] Random sampling (numpy.random)
https://docs.scipy.org/doc/numpy-1.16.0/reference/routines.random.html

**Myopia**

- [] WIKIPEDIA: Near-sightedness
https://en.wikipedia.org/wiki/Near-sightedness

- [] American Academy of Ophthalmology: Global Prevalence of Myopia and High Myopia and Temporal Trends from 2000 through 2050
https://www.aaojournal.org/article/S0161-6420(16)00025-7/abstract

- [] All about vision: What is myopia?
https://www.allaboutvision.com/conditions/myopia-faq/what-is-myopia.htm

- [] VISION EXCELLENCE: Myopia (short-sightedness)
https://www.visionexcellence.com.au/common-eye-conditions/myopia-short-sightedness/

- [] Cooper Vision: MiSight 1 day lenses
https://coopervision.co.uk/contact-lenses/misight-1-day

- [] [] All about vision: Why myopia progression is a concern.
https://www.allaboutvision.com/parents/myopia-progression.htm

- [] Health Service Executive: Myopia
https://www.hse.ie/eng/health/az/m/myopia/treating-short-sightedness.html

- [] IMI – Defining and Classifying Myopia: A Proposed Set of Standards for Clinical and Epidemiologic Studies
https://iovs.arvojournals.org/article.aspx?articleid=2727312

**Misc**

- [] Measuring Socioeconomic Status and Subjective Social Status
https://www.apa.org/pi/ses/resources/class/measuring-status

- [] BBC: What is your 21st Century social class?
https://www.bbc.com/news/magazine-34766169

**Genes**

- [] Insight into the molecular genetics of myopia (a bit technical)
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5757860/

- [] Stanford at The Tech: Understanding Genetics 
https://genetics.thetech.org/ask/ask73

- [] Science Daily: New genetic risk factors for myopia discovered
https://www.sciencedaily.com/releases/2016/04/160421133905.htm

 - [] All About Vision: Is being nearsighted genetic?
 https://www.allaboutvision.com/conditions/myopia-faq/is-being-nearsighted-genetic.htm

**Refraction**

- [] Characteristics of Refractive Errors in a Population of Adults in the Central Region of Poland
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5800189/

- [] stackoverflow: How to specify upper and lower limits when using numpy.random.normal
https://stackoverflow.com/questions/18441779/how-to-specify-upper-and-lower-limits-when-using-numpy-random-normal

**Age**

- [] WIKIPEDIA: Population pyramid
https://en.wikipedia.org/wiki/Population_pyramid

- [] StackExchange: If my histogram shows a bell-shaped curve, can I say my data is normally distributed?
https://stats.stackexchange.com/questions/129417/if-my-histogram-shows-a-bell-shaped-curve-can-i-say-my-data-is-normally-distrib

- []  Central Statistics Office:  E3001: Enumerated Population 1926 to 2016 by Age Group, Sex and CensusYear
https://statbank.cso.ie/px/pxeirestat/Statire/SelectVarVal/Define.asp?maintable=E3001&PLanguage=0

**Environment**

- [] Scientists Determine the Exact Amount of Time We Should Be Spending Outside
https://www.inverse.com/article/56685-nature-outdoors-mental-health-link

- [] Healio Primary Care Optometry News: Time outdoors reduces myopia risk in subset of children
https://www.healio.com/optometry/pediatrics/news/online/%7B7aa57b69-30ea-44fb-9f44-5159e62a6f79%7D/time-outdoors-reduces-myopia-risk-in-subset-of-children

- [] Time spent in outdoor activities in relation to myopia prevention and control: a meta‐analysis and systematic review
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5599950/
"Saw et al. [9] showed that compared to children of nonmyopic parents, children of myopic parents have a higher degree of myopia (average, 0.39 D for those with one myopic parent and 0.74 D for those with two myopic parents)"

- [] The association between time spent outdoors and myopia in children and adolescents: a systematic review and meta-analysis.
https://www.ncbi.nlm.nih.gov/pubmed/22809757

- [] The National Human Activity Pattern Survey (NHAPS)
https://www.nature.com/articles/7500165.pdf?origin=ppub

- [] US Bureau of Labor Statistics: Average hours per day spent in selected activities by age
https://www.bls.gov/charts/american-time-use/activity-by-age.htm

- [] Flowing Data: How People Like You Spend Their Time (interactive tool based on above reference)
https://flowingdata.com/2016/12/06/how-people-like-you-spend-their-time/

- [] Independent: CHILDREN SPEND TWICE AS LONG LOOKING AT SCREENS THAN PLAYING OUTSIDE, STUDY FINDS
https://www.independent.co.uk/life-style/children-screens-play-outside-computer-phone-time-healthy-games-a8603411.html

- [] Child in the City: Children spend half the time playing outside in comparison to their parents
https://www.childinthecity.org/2018/01/15/children-spend-half-the-time-playing-outside-in-comparison-to-their-parents/?gdpr=accept


