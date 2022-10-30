##################			
# Workflow			
##################

1.	Firstly, the Clark datafile is uploaded into R Session, and use coding like summary function to calculate the summary statistics including the mean and the stand error for each specie. And then use spread function to calculate the count and generate it into a data file
2.	Generate the data file obtained from the first step and combine it with the clark datafile to get complete statistics data and use rbind function to connect it with ocean datafile
3.	In the light of the complete datafile, then the effect size as log response ratio and the sampling variance has been calculated by ecalc function in the metafor library, then the meta object has been built by the rma.mv function.
4.	A series of diagnostics like the confidence interval and predict interval has been calculated. In addition to this , there is a warning which indicates that the sample variance differs a lot so there is a new dataset which can take the place of it
5.	The forest plot has been drawn through functions. And Funnel plot is also plotted to examine the publication bias.
6.	Finally, the time lag plot is drawn to figure out the time lag publication bias. And the inverse sampling variance is also included in the model to examine the file fewer bias. 

##################			
# DATA file structure			
##################

The name of the repository is "ixia", and it is a public repository containing one folders and nine documents in different formats. 
The document called "readme_BIOL6207.txt" is a description of a project that usually contains a description.
The document called "R_code. Rmd" is the R markdown file for this assignment. And the "R_code. Html" is the html format file for this assignment.
And other documents are the materials which were used for this assignment.

### clark_paper_data.csv ###			
			
columnHeading		description	
-------------		-----------	
Study			Code for each individual study
Authors			Authors of each paper	
Year (online)		Year the final paper was made available online
Year (print)	                Year the final paper was included in a journal volume/issue
Title			Title of each paper
Journal			Journal the paper was published in
Pub year IF		The journal impact factor for the year the paper was published; obtained from InCites Journal Citation Reports
2017 IF			The journal impact factor for 2017 (i.e., most recent journal impact factor); obtained from InCites Journal Citation Reports
Average n                               Average sample size for the study; average of indiviudal sample sizes for the contol and experimental groups
Effect type                              The type of effect concluded by the study regarding the effect of OA on behaviour; strong, weak, or no effect (see Supplementary Methods for details)
Climate (FishBase)                  Climatic region for each species; obtained from FishBase
Env cue/stimulus                    Whether or not the experiment included a cue or stimulus in the experiment (olfactory, visual, auditory, or physical)
Cue/stimulus type                  The type of cue or stimulus used
Behavioural metric                 The specific measure of behaviour tested
Life stage                                Life stage of the fish tested
			
*** Data used to summary statistic in the manuscript			
			
			
			
### meta-data_ocean_meta.csv ###			
			
columnHeading		description	
-------------		-----------	
Study			Code for each individual study
Authors			Authors of each paper	
Year (online)		Year the final paper was made available online
Year (print)	                Year the final paper was included in a journal volume/issue
Title			Title of each paper
Journal			Journal the paper was published in
Pub year IF		The journal impact factor for the year the paper was published; obtained from InCites Journal Citation Reports
2017 IF			The journal impact factor for 2017 (i.e., most recent journal impact factor); obtained from InCites Journal Citation Reports
Average n                               Average sample size for the study; average of indiviudal sample sizes for the contol and experimental groups
Effect type                              The type of effect concluded by the study regarding the effect of OA on behaviour; strong, weak, or no effect (see Supplementary Methods for details)
Species                                   The species used in each individual experiment
Climate (FishBase)                  Climatic region for each species; obtained from FishBase
Env cue/stimulus                    Whether or not the experiment included a cue or stimulus in the experiment (olfactory, visual, auditory, or physical)
Cue/stimulus type                   The type of cue or stimulus used
Behavioural metric                  The specific measure of behaviour tested
Life stage                                 Life stage of the fish tested
ctrl.n                                        Sample size of the control group
ctrl.mean                                 Mean of the control group
ctrl.sd                                       The standard deviation of the control group, calculated from ctrl.vartype
oa.n                                          Sample size of the experimental group
oa.mean                                   Mean of the experimental group
oa.sd                                        The standard deviation of the experimental group, calculated from ctrl.vartype
			
*** Data used to summary statistic in the manuscript			
			
			
			
### OA_activitydat_20190302_BIOL3207.csv ###			
			
columnHeading		description	
-------------		-----------	
loc			Location, and year, where the data were collected.	
species			Species name: Acanthochromis = Acanthochromis; Ambon = Pomacentrus amboinensis; Chromis = Chromis atripectoralis; Humbug = Dascyllus aruanus; Lemon = Pomacentrus moluccensis
treatment		"Elevated CO2 [CO2] (850-1,050) or control [Control] (400 - 450) groups"
animal_id			Fish identity
SL			Standard length of the fish in mm
size			Size grouping of the fish, separated at 15 mm standard length into 'big' or 'small'
activity		Number of seconds the fish was active per minute, averaged across the duration of the trial
comment			Comment with notes on the origin of the data

*** Data used to summary statistic in the manuscript			
			
			
			
### AIMS 2015 lat data.csv ###			
			
columnHeading		description	
-------------		-----------	
Study			Code for each individual study
Authors			Authors of each paper	
Year (online)		Year the final paper was made available online
Year (print)	                Year the final paper was included in a journal volume/issue
Title			Title of each paper
Journal			Journal the paper was published in
Pub year IF		The journal impact factor for the year the paper was published; obtained from InCites Journal Citation Reports
2017 IF			The journal impact factor for 2017 (i.e., most recent journal impact factor); obtained from InCites Journal Citation Reports
Average n                               Average sample size for the study; average of indiviudal sample sizes for the contol and experimental groups
Effect type                              The type of effect concluded by the study regarding the effect of OA on behaviour; strong, weak, or no effect (see Supplementary Methods for details)
Species                                   The species used in each individual experiment
Climate (FishBase)                  Climatic region for each species; obtained from FishBase
Env cue/stimulus                    Whether or not the experiment included a cue or stimulus in the experiment (olfactory, visual, auditory, or physical)
Cue/stimulus type                   The type of cue or stimulus used
Behavioural metric                  The specific measure of behaviour tested
Life stage                                 Life stage of the fish tested
ctrl.n                                        Sample size of the control group
ctrl.mean                                 Mean of the control group
ctrl.var                                     Measured variance of the control group
ctrl.vartype                              The metric of variance used for the control group (standared deviation, standard error, 95% confidence interval, or inter-quartile range
ctrl.sd                                       The standard deviation of the control group, calculated from ctrl.vartype
oa.n                                          Sample size of the experimental group
oa.mean                                   Mean of the experimental group
oa.var                                       Measured variance of the experimental group
oa.vartype                               The metric of variance used for the experimental group (standared deviation, standard error, 95% confidence interval, or inter-quartile range
oa.sd                                        The standard deviation of the experimental group, calculated from ctrl.vartype
lnRR                                         Raw effect size (natural log transformed response ratio)
|lnRR|                                       Absolute effect size (natural log transformed response ratio)
Weighted mean |lnRR|            The mean effect size for each study computed as the average of |lnRR| measurements for a given study
Notes                                       General notes regarding the nature of the data; includes rationale for omissions and other alterations to the data
JS check                                   Data checked by Josefin Sundin; X = yes
JCC final check                         Data final checked by Jeff Clements; X = yes
Precise sample size description in text?
                                                 Whether or not the study adequately described sample sizes in the text of the paper
Sample size source                  How the sample size for each group in each study was derived

*** Data used to help understanding in the manuscript				
			


