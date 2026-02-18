---
title: "Miniforge"
description: "Notes for installing and configuring Miniforge (conda-forge)"
tags: ["development"]
date: 2025-10-01
draft: false
---


- Download conda-forge installer from the [website](https://conda-forge.org/download/)

- Go to the directory and run

```bash
bash Miniforge3-$(uname)-$(uname -m).sh
```

Since `uname` outputs `Linux` and `uname -m` outputs `x86_64`, running the command `Miniforge3-$(uname)-$(uname -m).sh` is similar to mentioning the actual file name `Miniforge3-Linux-x86_64.sh`.


- It will ask to read the license agreement and now it will show `end`. Now type `yes` and the installation will begin.

```bash
Miniforge3 will now be installed into this location:
/home/gowtham/miniforge3

- Press ENTER to confirm the location
- Press CTRL-C to abort the installation
- Or specify a different location below
```

Press `ENTER`

- Once installation is done, it prompts

```bash
Do you wish to update your shell profile to automatically initialize conda?
This will activate conda on startup and change the command prompt when activated.
If you'd prefer that conda's base environment not be activated on startup,
run the following command when conda is activated:

conda config --set auto_activate_base false

You can undo this by running `conda init --reverse $SHELL`? [yes|no]
```

If `yes` - Adds Conda to your shell startup file. conda is ready every time. 
If `no` - You’ll have to manually source `~/miniforge3/bin/activate` each time.

press `yes` in this case. 


- Successfully installed

```bash
(base) gowtham@deb-gowarc:~$ conda --version
conda 25.3.0
```

- To prevent the automatic activation of the conda base environment when you open a new terminal
```bash
conda config --set auto_activate_base false
```

Once again, reopen the terminal. Conda can still be accessed in Konsole but we need to activate the environment when needed.
```bash
gowtham@deb-gowarc:~$ conda --version
conda 25.3.0
gowtham@deb-gowarc:~$ conda activate base
(base) gowtham@deb-gowarc:~$ conda deactivate
gowtham@deb-gowarc:~$ conda env list

# conda environments:
#
base                   /home/gowtham/miniforge3
```

