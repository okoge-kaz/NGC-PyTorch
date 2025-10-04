# NGC-PyTorch

## Build command

```bash
export LOCAL_DIR=/local/1215549.pbs1

cd $LOCAL_DIR
export SINGULARITY_TMPDIR=$LOCAL_DIR

singularity build ngc-pytorch-25.09.sif ngc-pytorch-25.09.def
```

## Debug command

```bash
export LOCAL_DIR=/local/1215549.pbs1

cd $LOCAL_DIR
export SINGULARITY_TMPDIR=$LOCAL_DIR

# make sandbox
singularity build --sandbox ngc-pytorch-25.09 25.09.def

# shell into the sandbox
singularity shell --writable ngc-pytorch-25.09

# change site-packages
> vim /usr/local/lib/python3.12/dist-packages/torch/distributed/checkpoint/filesystem.py

> exit

singularity build ngc-pytorch-25.09.sif ngc-pytorch-25.09
```
