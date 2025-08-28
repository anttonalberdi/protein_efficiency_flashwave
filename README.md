# Protein efficiency Flashwave analysis

Flashwave analysis of protein efficiency in Mjolnir.

## Input files

Prepare input files in R and upload them to working directory: `protein_efficiency_flashwave/data`

## Screen session

Create an screen session to avoid disconnection from stopping the work.

```sh
screen -S protein_efficiency_flashwave
```

## Interactive session

Open an interactive session for 24h.

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

## Open Julia

```sh
module load julia
julia
```

## Test Flashwave

Test whether everything works fine with Flashwave. Use `]` to enter to package mode. Then,

```sh
test FlashWeave
```

## Run analysis

```sh
using FlashWeave

data_path = "/data/genome_abundances.tsv"
metadata_path = "/data/genome_metadata.tsv"
netw_results = learn_network(data_path, metadata_path, sensitive=true, heterogeneous=false)
```

## Visualise and save

```sh
save_network("/my/example/network_output.edgelist", netw_results)
G = graph(netw_results)
```
