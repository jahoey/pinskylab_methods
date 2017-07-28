#**Guide to using the Amarel cluster**

Amarel is a high-performance computer cluster managed by the Rutgers
Office of Advanced Research Computing (OARC; <https://oarc.rutgers.edu/>).
Amarel resources are available to the Rutgers community and are useful
for when you need to perform research computation that exceeds the
resources of your personal computer or the Pinsky Lab cluster,
Amphiprion. This guide describes the steps necessary to get an account
and how to submit and run jobs on Amarel.

##**Getting started**:

To get an account on Amarel, you will need to complete the official
access request form (<https://oarc.rutgers.edu/access/>) and might
consider going to an OARC training session
(<https://oarc.rutgers.edu/events/>) to familiarize yourself with the
Amarel system and how to plan for and submit jobs. Also a basic
familiarity with the command line and bash scripting are very helpful.
If you need to first brush up on the command line, there are many good
tutorials online, including Codecademy.

##**Overview of Amarel & slurm**:

Like many other clusters, Amarel uses an open-source job scheduler
called slurm to manage and schedule jobs. To submit jobs to the slurm
scheduler, you’ll use the sbatch and srun commands depending on the
specifications of your job. It is a good idea to skim through the slurm,
sbatch and srun man pages. The Amarel User Guide
(<http://rci.rutgers.edu/~gc563/amarel/>) also has very useful
information on how to connect to Amarel, install software and run jobs.
Finally, the OARC staff are very helpful and can assist with any issues
(<help@oarc.rutgers.edu>). I highly recommend testing small versions of
your job on Amphiprion and then Amarel before scaling up to full-scale
production on Amarel.

##**Submitting a job**:

Once you have logged into Amarel and installed any necessary software,
you are ready to write a script to submit your jobs to slurm. The
following example describes how to submit a fastsimcoal2 job to Amarel
assuming the fsc25 executable and any fsc25 input files are in
/home/\$USER. If you need to, it is easy to submit this job to Amarel
many times using a simple bash for loop.

	[jah414@fen1 ~]$ less run_fsc.sh

############################

	#!/bin/bash 						  ## Allows script to be run as a bash script
	#SBATCH --nodelist = hal0001		## enter the node where your data on node scratch is located
	
	
	wait
	
Once everything is working, submit your job to the slurm scheduler using sbatch. Your job will sit in the queue until slurm assigns resources to your job. In the settings of run_fsc.sh I told Amarel to email me when the job ended.


##**Helpful slurm commands**:

