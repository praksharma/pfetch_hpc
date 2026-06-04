# pfetch for HPC clusters
The original README of pfetch can be found [here]([url](https://github.com/dylanaraps/pfetch/blob/master/README.md)).

## How to use it?
Copy the sh file to your machine and run it.

Chatgpt codex was used to add certain codes as I don't understand everything in bash scripting.

## Preview
```
[user@login-q-1 ~]$ bash pfetch_hpc.sh
    ___       user@login-q-1
   (.. |      os     Rocky Linux release 8.10 (Green Obsidian)
   (<> |      host   PowerEdge XE8545
  / __  \     cpu    AMD EPYC 7763 64-Core Processor
 ( /  \ /|    cores  1
_/\ __)/_)    gpu    1x NVIDIA A100-SXM4-80GB
\/-____\/     hpc    slurm job JOB_ID queue NODE account ACCOUT_NAME 1 node 1 task 1 gpu
              node   gpu-q-49
              kernel 4.18.0-553.125.1.el8_10.x86_64
              uptime 1d 11h 35m
              pkgs   3334
              memory 215110M / 1031142M
```
