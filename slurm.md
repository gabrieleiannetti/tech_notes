## Slurm Notes

# Scheduling Queues

**Report only on jobs allocated to the specified node or list of nodes:**

``squeue -w node0[195-200]``

Output-Format:

_JOBID PARTITION     NAME     USER ST       TIME  NODES NODELIST(REASON)_

**Displays information about the debug queue:**

``scontrol show partition debug``

Output:

_AllowGroups=ALL AllowAccounts=ALL AllowQos=ALL  
AllocNodes=ALL Default=NO  
DefaultTime=00:02:00 DisableRootJobs=NO GraceTime=0 Hidden=NO  
MaxNodes=UNLIMITED MaxTime=00:20:00 MinNodes=1 LLN=NO MaxCPUsPerNode=UNLIMITED  
Nodes=lxbk0[195-200],lxlcsc0001  
Priority=1 RootOnly=NO ReqResv=NO Shared=NO PreemptMode=OFF  
State=UP TotalCPUs=280 TotalNodes=7 SelectTypeParameters=N/A  
DefMemPerCPU=2048 MaxMemPerCPU=3072_

# Displaying Job Information

**Display job information for a user within specific time points and output format:**

``sacct -u USER -S2017-08-09-15:30 -E2017-08-09-16:00 -o 'Start,End,Elapsed,State' | grep -e '2017-08-09T15:3'``
