---
layout: post
title: "Indicator Species"
date: 2019-11-26
---
One way to identify indicator species (and simultaneously cluster sites based on these species) is Latent Dirichlet Allocation.
The method was introduces for natural language processing by Blei et al. (2003) but has since been applied in fraud detection (Xing & Girolami 2007), 
digital image analysis (Vaduva et al. 2013) and bioinformatics (Liu et al. 2010) (this sentence is pretty much copied from Valle et al. (2014)).
With LDA we can describe each sampling unit (e.g. a site or a site at a certain time. In NLP this would be the document) using its communities (topics in NLP). The communities are characterized by their species (words in NLP). One species can occur very often in certain communities but rarely in others, while another species occurs often in all kinds of communities and is therefore not useful as an indicator (however if a species generally occurs across sampling units its absence might be informative). 
This is achieved by decomposing the original multivariate abundnace data into two matrices (see Figure 1). 

## References
Blei, D., Ng, A. & Jordan, M. (2003). Latent Dirichlet Allocation. J. Mach. Learn. Res., 3, 993–1022.     

Valle, D., Baiser, B., Woodall, C. W., & Chazdon, R. (2014). Decomposing biodiversity data using the Latent Dirichlet 
&ensp; &ensp; &ensp; Allocation model, a  probabilistic multivariate statistical method. Ecology Letters, 17(12), 1591–1601. https://doi.org/10.1111/ele.12380
