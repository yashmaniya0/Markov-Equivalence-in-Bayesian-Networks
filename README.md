# btp

Last updated: Nov 10, 2023

Motivation
- Benchmark the existing Markov equivalence class management strategies
- Accidentally we may come up with our own MEC management strategy which 
  might be a (new scoring fn, DAG constraint) pair.
- We will choose a small dataset like the sprinkler dataset and benchmark
  tie breaker strategies on top of bnlearn's exhaustive search algo
- We will choose a large dataset and benchmark
  tie breaker strategies on top of a heuristic-based or constraint-based
  structure learning algorithm. For selecting structure learning algo,
  we will follow Scutari's recommendations.

Report
- Curate a template of your choice - DONE

Papers
- Who learns better Bayes net? by Scutari - PUT ON HOLD
- Find papers that address MEC problem and present in the meetings - PUT ON HOLD

Steps to complete before the BTP report: 
* bnlearn
- Pick a small dataset of your choice with the true network known
  For "bn.structure_learning.fit(df, methodtype='ex', scoretype='bic')",
  (a) figure out how to output all the best fit DAGs (if there are multiple) - Save the adj matrices
  as Python objects and visualize them as graph plots. [DONE but please present your DAG outputting function to SP]
    (a1) Look for new small datasets (with 6-10 vertices). 
         If found, output the best fit DAG(s).
		 If there are multiple best fit DAGs, calculate their F1-scores.
		 All such DAGs should have the same likelihood score, record that likelihood score.
  (b) Figure out what tie breaker strategy is implemented there.
      For that purpose, trace which functions are called by 
	  "bn.structure_learning.fit(df, methodtype='ex', scoretype='bic')". 
      It seems like the source code of "pgmpy.StructureEstimator" class implements the tie breaking algo we are looking for.
  (c) Write a function to calculate the F1-score of a predicted DAG. 
      Using this function, calculate the F1-scores of the best fit DAGs. [DONE, the code has been reviewed and looks good]
 

