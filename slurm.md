## Slurm Notes

# Scheduling Queues

### Report only on jobs allocated to the specified node or list of nodes:

Command: ``squeue -w lxbk0[195-196]``

Output-Format:

_JOBID PARTITION     NAME     USER ST       TIME  NODES NODELIST(REASON)_

**Displays information about the debug queue:**

Command: ``scontrol show partition debug``

Output:

_AllowGroups=ALL AllowAccounts=ALL AllowQos=ALL  
AllocNodes=ALL Default=NO  
DefaultTime=00:02:00 DisableRootJobs=NO GraceTime=0 Hidden=NO  
MaxNodes=UNLIMITED MaxTime=00:20:00 MinNodes=1 LLN=NO MaxCPUsPerNode=UNLIMITED  
Nodes=lxbk0[195-200],lxlcsc0001  
Priority=1 RootOnly=NO ReqResv=NO Shared=NO PreemptMode=OFF  
State=UP TotalCPUs=280 TotalNodes=7 SelectTypeParameters=N/A  
DefMemPerCPU=2048 MaxMemPerCPU=3072_