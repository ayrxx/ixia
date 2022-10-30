# Workflow：
1.	Firstly, the Clark datafile is uploaded into R Session, and use coding like summary function to calculate the summary statistics including the mean and the stand error for each specie. And then use spread function to calculate the count and generate it into a data file
2.	Generate the data file obtained from the first step and combine it with the clark datafile to get complete statistics data and use rbind function to connect it with ocean datafile
3.	In the light of the complete datafile, then the effect size as log response ratio and the sampling variance has been calculated by ecalc function in the metafor library, then the meta object has been built by the rma.mv function.
4.	A series of diagnostics like the confidence interval and predict interval has been calculated. In addition to this , there is a warning which indicates that the sample variance differs a lot so there is a new dataset which can take the place of it
5.	The forest plot has been drawn through functions. And Funnel plot is also plotted to examine the publication bias.
6.	Finally, the time lag plot is drawn to figure out the time lag publication bias. And the inverse sampling variance is also included in the model to examine the file fewer bias. 

# Data file structure
The name of the repository is "ixia", and it is a public repository containing one folders and nine documents in different formats. 
The document called "readme_BIOL6207.txt" is a description of a project that usually contains a description.
The document called "R_code. Rmd" is the R markdown file for this assignment. And the "R_code. Html" is the html format file for this assignment.
And other documents are the materials which were used for this assignment.

# Meta-data
It is data that provides information about other data, but not the content of the data.

