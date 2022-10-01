PROGRAM      =   SCIMITAR3D_EXE
PROGRAM_NEW  =   SCIMITAR3D_NEW_EXE 
ALL: $(PROGRAM)
include ${PETSC_DIR}/lib/petsc/conf/variables
include ${PETSC_DIR}/lib/petsc/conf/rules
## 2 =Number of Options Packages######################
GAMG:
		-@${MPIEXEC} -n 1 ./$(PROGRAM) -ELAFINT_case_name input -lspaint_ksp_type bcgsl -lspaint_ksp_monitor -pres_ksp_type preonly -pres_pc_type redistribute -pres_redistribute_ksp_type bcgsl -pres_redistribute_pc_type gamg -pres_redistribute_pc_gamg_threshold 0.05 -pres_redistribute_mg_levels_ksp_type richardson -pres_redistribute_mg_levels_pc_type sor -pres_redistribute_mg_coarse_ksp_type richardson -pres_redistribute_mg_coarse_pc_type sor -pres_redistribute_mg_coarse_pc_sor_its 1 -pres_redistribute_pc_gamg_type agg -pres_redistribute_pc_gamg_agg_nsmooths 2 -pres_redistribute_pc_gamg_sym_graph true -pres_redistribute_ksp_monitor_true_residual -vel_ksp_monitor_true_residual
GAMGv:
		-@${MPIEXEC} -n 1 ./$(PROGRAM) -ELAFINT_case_name input -lspaint_ksp_type bcgsl -lspaint_ksp_monitor -pres_ksp_type preonly -pres_pc_type redistribute -pres_redistribute_ksp_type bcgsl -pres_redistribute_pc_type gamg -pres_redistribute_pc_gamg_threshold 0.05 -pres_redistribute_mg_levels_ksp_type richardson -pres_redistribute_mg_levels_pc_type sor -pres_redistribute_mg_coarse_ksp_type richardson -pres_redistribute_mg_coarse_pc_type sor -pres_redistribute_mg_coarse_pc_sor_its 1 -pres_redistribute_pc_gamg_type agg -pres_redistribute_pc_gamg_agg_nsmooths 2 -pres_redistribute_pc_gamg_sym_graph true -pres_redistribute_ksp_monitor_true_residual -vel_ksp_monitor_true_residual
SCIMITAR3D_VAL:
		valgrind --log-file="val.out" ./$(PROGRAM) -ELAFINT_case_name input
SCIMITAR3D:
		./$(PROGRAM) -ELAFINT_case_name input
SCIMITAR3D_NEW:
		./$(PROGRAM_NEW) -ELAFINT_case_name input
E3D:
		-@${MPIEXEC} --quiet -n 6  ./$(PROGRAM) -ELAFINT_case_name input
VALE3D:
		-@${MPIEXEC} -n 3 valgrind --log-file="val.out" ./$(PROGRAM) -ELAFINT_case_name input
E3D_NEW:
		-@${MPIEXEC} -quiet -n 8  ./$(PROGRAM_NEW) -ELAFINT_case_name input
makefolders:
		mkdir RESULTS
		mkdir RESTART
		mkdir RESTART_FILES0
		mkdir RESTART_FILES1
		mkdir RESTART_FILES2
		mkdir RESTART_FILES3
		mkdir RESTART_FILES4
		mkdir RESTART_FILES5
		mkdir RESTART_FILES6
		mkdir RESTART_FILES7
		mkdir RESTART_FILES8
		mkdir RESTART_FILES9
		mkdir RESTART_FILES10

##########################################################
