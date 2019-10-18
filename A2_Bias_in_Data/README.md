# Project Goal
The goal of project will be to analyze potential bias in Wikipedia article coverage of politicians by country and region. 
This method will look into the abundance of articles (or lack thereof) proportional to the geographical population, as well as the proportion of quality articles, as rated by the ORES (Objective Revision Evaluation Service) Wikimedia algorithm.
Python version 3.6.8 was used. The code dependencies are as follows:
* numpy v1.16.4
* pandas v0.24.2
* pickelshare v0.7.5

ORES provides one of 6 quality category estimates for articles based on probabilities for each. The scores take into accout the timing of the evaluation. The 6 categories, from best to worst, are as follows:

* FA - Featured article
* GA - Good article
* B - B-class article
* C - C-class article
* Start - Start-class article
* Stub - Stub-class article

The documentation for the ORES API can be found at https://ores.wikimedia.org/. Version 3 was the API was used.

The politician article data was retrieved from https://figshare.com/articles/Untitled_Item/5513449 on 10/16/2019. Version 6 was used for this analysis. The data is released under the CC-BY-SA 4.0 license. The following data description was copied directly from the page.

<i>The data was extracted via the Wikimedia API using the associated code. It is formatted as a CSV and saved as page_data.csv in the "data" directory. Columns are:

1. "country", containing the sanitised country name, extracted from the category name;
2. "page", containing the unsanitised page title.
3. "last_edit", containing the edit ID of the last edit to the page.

Country codes are inconsistent. Where possible, they have been modified to match the country names found in http://www.prb.org/DataFinder/Topic/Rankings.aspx?ind=14 - but the PRB dataset contains nations not found in Wikipedia, and vice versa.

The actual recursion only went 2 levels deep into the category tree: someone listed as an Antiguan politician, say, is included - someone exclusively listed as an Antiguan politician who was assassinated is not.</i>

The world population data was retrieved from https://www.prb.org/international/indicator/population/table/, using the population labeled as of mid-2018.
* Geography: The geographical area the for the entry. Entries in all capitals (e.g. ASIA) represent aggregated regions
* Population mid-2018 (millions): The recorded population (in millions) of the associated geographical area as of mid-2018

<i>Note: There is an issue with attempting to use the python ORES API with Windows 10. The pyenchant dependency, which has an enchant C library dependency, is an abandoned project as of 2018 and will likley not be fixed. The pickle file provided to circumvent this issue is courtesy of Alexander Van Roijen.</i>


This code and analysis is relased under the MIT License.
