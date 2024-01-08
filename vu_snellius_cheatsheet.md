# Cheatsheet for the snellius cluster 
1. Check quota on home directory: `myquota`
2. Check quota on project directory: `/gpfs/admin/hpc/usertools/prjspc-quota {insert folder}/`
3. My sbatch jobs disappear when it goes to the queue and running. The slurm.out or slurm.err files did not exist. One reason could be that you have exceeded the quota. Check quota using commands above. 
