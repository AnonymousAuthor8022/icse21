## Genetic Algorithm Implementation
The chromosome has one gene for each configuration option where the alleles are the possible configuration option values.

#### Fitness 
Our fitness equation is : (no of quality hits)+w\_distance, where w\_distance is the weighted distance given by w\_distance= 100/20\*(20-0). We are maximizing this fitness equation. 

#### Parameters
* population size = 16
* mutation rate = 0.5
* number of generations = 50


## Genetic Algorithm Results

#### The GA-RunSummary.csv file bears details of the genetic algorithms's runs for our study. We have presented outcomes of 20 runs. The file's column descriptions are as follows:
**Column 1** denotes the **run no** which represents each independent run of the genetic algorithm. 
**Columns 2 to 20** denote the following **configuration options** from our model under study:
    dust, lcase_masking, soft_masking, ungapped, xdrop_gap, xdrop_gap_final, xdrop_ungap, word_size, min_raw_gapped_score, strand, show_gis, num_description, num_alignment, line_length, html, max_target_seqs, sum_stats, parse_deflines, num_threads
**Column 21** denote the **quality hits** which is the total number of hits observed for a specific configuration set found by the genetic algorithm.
**Column 22** denote the **distance** of the configuration set found by the genetic algorithm from the default configuration set.

#### The GA-RunTime.csv file bears information about the run time recorded for each of the 20 runs of our genetic algorithm. The file's column descriptions are as follows:
1. **Run No:** Represents each independent run of the genetic algorithm. 
2. **Time in nanosec:**	The time recorded for a particular run of the algorithm in nanoseconds.
3. **Time in millisec:** The time recorded for a particular run of the algorithm in milliseconds.
4. **Time in minutes:** The time recorded for a particular run of the algorithm in minutes.

#### The overall run statistics can be summarized as follows:
1. **Average time required for all 20 runs to complete (in minutes):** 78.73 minutes.
2. **Standard deviation calculated for all runs taken together (in minutes):** 4.2 minutes.
3. **The minimum runtime recorded over all 20 runs:** 63.78 minutes.
4. **The maximum runtime recorded over all 20 runs:** 84.89	minutes.
5. **The sum of all 20 runs in minutes:** 1574.59 minutes.
6. **The sum of all runs in hours:** 26.2431904 hrs.	
7. **The sum of all runs in days:** 1.093466267 days.	


