# building a RockyLinux8  based singularity/apptainer container for scipion3 (using cuda 12.3)

Tru <tru@pasteur.fr>

## Why ?
- ready to use runtime environment for scipion3
- just add miniconda and scipion3 (use a writable bind mount for /opt)
- allow easy snapshoting/replacement for /opt and upgrade/downgrade
- share scipion with your co-worker

## How to:
- build the container
- use the container with a mounted /opt to
	- install miniconda and scipion-installer
	- install any plugin/binary
- use mksquashfs "freeze" your scipion and share it with the rl8 runtime

## helper scripts (read and modify to your needs especially `_S` and `_B`)
- `setup.sh` build the container and install scipion3 conda environment
- `scipion3.sh` run scipion3 from the container

## use the artefact produced on github instead of building your own:
```
apptainer build ghrc-io-singularity-rl8-scipion-runtime-cuda123.sif oras://ghcr.io/truatpasteurdotfr/singularity-rl8-scipion-runtime-cuda123:latest
```

## References
- https://scipion.i2pc.es/

## Caveat
- playground, use at your own risk!

