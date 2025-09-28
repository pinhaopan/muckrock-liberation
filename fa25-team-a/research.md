# Research Work
The project data provided to us is inform of PDFs, so the first priority is to organize it into a proper database. After that, we can begin applying different analytical techniques and perform Exploratory Data Analysis as per the client requirement. Hence, below are some research papers and important links which could help us reach our goal efficiently:-

## Background Research on Provided Data
* The provided data is in PDF format containing screenshots of tabular data.
* There are a few data points marked flagged in Red Bold fonts in the Navy Revenue Report files and some data points are missing.
* The Copy of Revenue Comparison has 53% of the data marked classified.

## Research Categories
#### Regional analysis on US Military Bases
* There are 63 US Military bases in Japan, which collectively generated over 25 million USD in revenue in 2022. This represented 40% of the total revenue generation of approximately 63 million USD. This resource helps us in mapping the locations of all the military bases in Japan using the Japanese Government’s official website [1][2] to analyze which base has higher gambling rates.
* We also found a research paper whose classification methods could be utilized in this project to classify and categorize data by countries. The paper shows how ensemble models can be fine-tuned to handle complex datasets and produce more reliable classifications on breast tumor data [3]. Even though the context is medical, the classification model is very effective. 

#### Research on Gambling
* We conducted a research on a Machine Learning Tree-Based Algorithm that directly relates to gambling behavior among people [4]. This paper analyzes human behavior and predicts the optimal location for the next gambling center to maximize revenue generation. The machine learning model developed in this paper could be helpful to detect the gambling patterns of military officials and help in identifying the bases with higher gambling rates. This could be helpful in setting up limitations on gambling at specific military bases to mitigate any addictive behavior.
* The article “Exploring the prevalence of gambling harm among active duty military personnel: a systematic scoping review”[6] provides an overview and synthesis of the academic literature on gambling within military populations. It suggests that service members may be at an increased risk of gambling-related harm than the general population because stress they incur from being deployed, their isolation and access to on-base gambling. Building these observations into our analysis is of crucial contextual value, as accounting for the incidence of gambling harm can help translate patterns in revenue to possible social and behavioral consequences.
* According to a recent U.S. Government Accountability Office report entitled, “Military Personnel: DOD and the Coast Guard Need to Screen for Gambling Disorder Addiction and Update Guidance”[7] slot machines on U.S-military bases may bring in as much as $100 million annually. It also highlights the danger of gambling disorder among military personnel and the importance of screening and developing guidelines to address the possibility of addiction. This twofold viewpoint with regard to the economic benefits and correlated risks constitutes an essential basis for the consideration of gambling on military bases.

#### Data Cleaning and Machine Learning Algorithms
* Since the data provided is about trends of revenue generated in a given span of time, performing Time-Series Analysis could bring important insights on revenue generation at US Military Bases. We researched on Deep Learning Model based on Time Series Analysis with Frequency Transformation [5]. Applying this to ARMP revenue data might show whether the given data is stable over time or just a temporary spike. It could also help predict if similar revenue concentrations will show up in other regions in the future.
* The application of Regression Analysis has also permeated the gambling research. The article "Table Games, Slot Machines and Casino Revenue"[8] uses regression analysis to examine the expected impact of slot machines and table games on casino revenue. Further deviations such as being situated on a base, whether base is located in the states or OCONUS, machine type, military affiliation and dates but there were local effects on revenue from slot machines.
* Furthermore, the study ‘Slot Operations: A Regression Analysis of Factors Impacting Slot Revenue’[9] uses a multiple regression model to study slot machine performance in commercial casinos (Miller and Metz 2010). A similar categorical approach can be used in our project to segment the effect of machine type, number of machines, base location and service branch on slot revenue in military environment.

## References
[1] Japan Ministry of Defense - https://www.mod.go.jp/en/presiding/law/usfj.html \
[2] FA’25 – MuckRock: US Military Base Slot Machine Revenue Explorer. Copy of Presentation.pdf \
[3] An optimized ensemble model based on meta-heuristic algorithms for effective detection and classification of breast tumors Springer (2024) - https://link.springer.com/content/pdf/10.1007/s00521-024-10719-9.pdf \
[4] Spatial Clusters of Gambling Outlet: A Machine Learning Tree-Based Algorithm. MDPI (2024) - https://www.mdpi.com/2571-905X/8/1/4 \
[5] A Survey on Deep Learning based Time Series Analysis with Frequency Transformation. arXiv (2023) - https://arxiv.org/pdf/2302.02173
[6] Paterson, M., Whitty, M., & Leslie, P. (2021). Exploring the prevalence of gambling harm among active duty military personnel: a systematic scoping review. Journal of gambling studies, 37(2), 529-549.
[7] U.S. Government Accountability Office. (2017, January 30). Military Personnel: DOD and the Coast Guard Need to Screen for Gambling Disorder Addiction and Update Guidance (GAO-17-114). https://www.gao.gov/products/gao-17-114
[8]Thalheimer, R., & Ali, M. M. (2008). Table games, slot machines and casino revenue. Applied Economics, 40(18), 2395-2404.
[9]Lucas, A. F., & Brewer, K. P. (2001). Managing the slot operations of a hotel casino in the Las Vegas locals’ market. Journal of Hospitality & Tourism Research, 25(3), 289-301.
