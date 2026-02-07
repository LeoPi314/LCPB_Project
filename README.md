Contents and suggested viewing order:

A) Real_Data_Analysis:

	- 0) Data_Distribution: contains study on single track variables of the real data (a couple of chunks were used for this).
							It justifies the cuts chosen for the single track variables in the first part of the analysis.
							
	- 1) Parallel_Pairs_Creation: contains the procedure with which couples of opposite electrical charge were created to reconstruct
								  the original D0 or anti-D0 mother.
								  
	- 2) MC_Ratio_For_Fit: replicates on MC the cuts chosen in order to compute the efficiency and obtain the ratio for the reflected
						   component.
						   
	- 3) Pair_Analysis: filters data based on single track + pair variables cuts and plots the resulting invariant mass histogram.

B) Monte_Carlo_Analysis:

	- 0) MC_cut_analysis_single_tracks: contains study and cuts gridsearch for single track variables of the MC data.
							
	- 1) MC_cut_analysis_pair_variables: contains study and cut search for pair track variables of the MC data. Also contains invariant mass fit.
	
C) efficiency_pt_intervals_MC_cuts:
	In this notebook there is the efficiency computation for different cuts from monte carlo analysis and on $p_T$ intervals. 

D) Machine Learning implementation for particle selection:

The folder Candidate_ML_Analysis/ contains all notebooks used for the final analysis
	- 0) Inside each subdirectory, e.g. D0_Pt_2, there file DefinitiveXGBoost.ipynb contains:
		- the model training on the MC data for a specific $P_T$ interval 
		- the grid search for the optimal cuts on the training scores
		- the efficiency computation on MC test set
	- 1) For each subdirectory, one or multiple files Candidate_Selection_X.ipynb are present:
		- these have been used to apply the trained model on all data chuncks in a specific $P_T$ sub interval
		- the results are shown in a graph and have been saved (remotely) in condensed dataframes
	- 2) Only for D0 subdirecories, Candidate_Extra_X.ipynb files are present, those show how the trained model apply cuts on the original variables
	- 3) The last file is Particle_Counting.ipynb, in which:
		- all chunck results for each pt interval and subinterval are shown 
		- for each subinterval the raw yield for both particle is extracted
		- from the two set of raw yield, corrected yield, particle ratio and cross section are computed
		- finally, the production ratio between the two particles is computed and all results shown in a graph