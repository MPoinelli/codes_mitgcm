# codes_mitgcm
Repositories with mitgcm codes


Here the description of what I use these codes for:

code_larsen_v5_68i_2 -> test 1, remove shelfice&ptracer from code_larsen_v5_68i
code_larsen_v5_68i -> larsen code to be compiled on mitgcm_c68i
code_larsen_v5_full_FAST  -> same as code_larsen_v5_full but with D. Kokron edit and nx=ny=20 (faster)
code_larsen_v5 -> based on Nakayama2019, with the only addition of a seaice sponge layer.
code_larsen_v5_full -> based on Nakayama2019, with the only addition of a seaice sponge layer.
code_larsen_v4_Nakayama2019 -> based on Nakayama 2019 but with geometry v4

code_meltchannels -> meltchannels experiment of S Nanninga

code_rifts -> code used for rifts experiment, Poinelli 2022, JPO



/OLD_CODES: repo with outdated mitgcm codes

        code_larsen_v2_ICELOAD -> same as code_larsen_v2 but with define define SEAICE_CAP_ICELOAD in SEAICE_OPTIONS.h
        code_larsen_v2 -> same as code_larsen_Nakayama but using larsen geometry v2
        code_larsen_v1_Nakayama2019 -> same as code_larsen_v1 but with SEAICE_OPTIONS.h, OBCS_OPTIONS.h (except for define Seaice_Sponge), CPP_OPTIONS.h from Nakayama2019
        code_larsen_v1_UVICE -> larsen simulation, based on larsen geometry v1 and define OBCS_SEAICE_COMPUTE_UVICE
        code_larsen_v1  -> larsen simulation, based on larsen geometry v1 and seaice edits of v0_seaice
        code_larsen_v0_seaice  -> larsen simulation, based on llarsen geometry v0 and define OBCS_SEAICE_AVOID_CONVERGENCE
        code_larsen_v0  -> larsen simulation, based on llarsen geometry v0
        code_larsen_full -> same as above but without empty tiles

        code_testCaseRift -> idealized cracked geoemtry


""
Kokron, D.
The default way MITgcm computes global sums used by the cg2d routine is less than optimal.
Fortunately, the code has a path that is optimal.
You can enable the optimal path by setting the following in your MITgcm/eesupp/inc/CPP_EEOPTIONS.h and recompiling.
Enabling this 'fast' path provided a dramatic increase in model simulation speed for the llc_540 case and the testCaseRift case.

#undef GLOBAL_SUM_ORDER_TILES
#undef GLOBAL_SUM_SEND_RECV


