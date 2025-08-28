# Protein efficiency Flashwave analysis

## Input files

Prepare input files in R and upload them to working directory: `protein_efficiency_flashwave/data`

## Screen session

Create an screen session to avoid disconnection from stopping the work.

```sh
screen -S protein_efficiency_flashwave
```

## Interactive session

Create an interactive session in R

```sh
srun \
  --job-name=protein_efficiency_flashwave \
  --partition=cpuqueue \
  --nodes=1 \
  --time=24:00:00 \
  --mem=16G \
  --cpus-per-task=4 \
  --pty bash -I
```


Flashwave analysis of protein efficiency in Mjolnir.
