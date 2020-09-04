## Genetic Algorithm Implementation

The chromosome has one gene for each configuration option where the alleles are the possible configuration option values.

#### Fitness 
When using BLAST, a biologist may want to increase the number of quality hits they match from the database.  Often, users restrict two quality values, e-value and the percentage identity. We use these values for optimization. We introduce the GA to search for the best possible quality hits, that is, hits with e-value equal to zero and percentage identity is equal to 100 which is a common use case for BLAST. We also include distance from the default configuration in our fitness. Our GA aims to achieve the maximal possible quality hits under the minimal possible distance, for all inputs taken together when BLAST is executed. Our goal is to stay close to the original configuration.

We are maximizing the fitness score. Our fitness equation is : (no of quality hits)+w\_distance, where w\_distance is the weighted distance given by w\_distance= 100/20\*(20-0).  Our model uses 19 configurations each of which can be changed to different options. Hence, including the default which has a distance of 0, we have total possible 20 different integral values for distance, ranging from 0 to 19. We chose an uniform scale where for every single increment of distance, unless the quality hits observed for the chromosome with the greater distance exceeds that of the one with the lower distance by at least 5, the fitness score of the chromosome with the lower distance will be preferred over the other one.  For example: A chromosome with a quality hit of 100 and distance equal to 5 will be preferred over a chromosome with a quality hit of 103 and distance of 6.

#### Genetic Algorithm Parameters
We heuristically tuned our algorithm. A population size of 16 was used for this study. One chromosome of the initial randomly generated population is filled with the default values which is “unset”. This ensures a fair chance for the default to be selected in the final population, if it is indeed the best. One-point crossover was used and a random point within the middle two thirds of the chromosome for each pair was selected for the purpose. Even and odd numbered chromosomes were paired in a ranked order (e.g. the best with the third best and second best with the fourth best) to maintain some diversity. We also introduced elitism alongside rank selection and we never mutate the best two chromosomes of the previous generation. 

The mutation rate was set at 0.5 for the process. 50 percent of the genes in the population were randomly selected and mutated with a random value (with replacement). We chose the generation of runs as 50 since we observed convergence within the first 20-30 generations.


#### Experimental Setup
All experiments are run on a parallel computing RedHat Enterprise Linux 7 Server with Intel(R) Xeon(R) Gold 6244 CPU 2.60GHz nodes. We collected the results obtained by the genetic algorithm by making repeated BLASTn calls through our program. A single file bearing the entire input yeast dataset was fed as an input to the GA. The results for the final best observed chromosome were collected once the algorithm terminated at the end of 50 generations. Since we also consider both the parent and child chromosomes while comparing and choosing the best 16 chromosomes per generation, we have a total of 32 BLASTn calls per generation, resulting in 1,600 BLASTn calls through a single run of the program. The following outputs were collected completion of the GA: the best configuration set observed by the GA, its corresponding distance from the default and the number of quality hits, the fitness score of the configuration chosen as the best.


## Genetic Algorithm Results

The GA-RunSummary.csv file bears details of the genetic algorithms's runs for our study. We have presented outcomes of 20 runs. The file's column descriptions are as follows:
1. Run No: It represents each independent run of the genetic algorithm. 
2. dust: 
3. lcase_masking	
4. soft_masking	
5. ungapped	
6. xdrop_gap	
7. xdrop_gap_final	
8. xdrop_ungap	
9. word_size	
10. min_raw_gapped_score	
11. strand	
12. show_gis	
13. num_description	
14. num_alignment	
15. line_length	
16. html	
17. max_target_seqs	
18. sum_stats	
19. parse_deflines	
20. num_threads
21. Quality hits	
22. Distance
