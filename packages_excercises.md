
## What are conda packages?

A conda package is a compressed archive file (`.tar.bz2`) that contains:

* system-level libraries
* Python or other modules
* executable programs and other components
* metadata under the `info/` directory
* a collection of files that are installed directly into an `install` prefix.

Conda keeps track of the dependencies between packages and platforms; the conda package format is 
identical across platforms and operating systems.

## Package Structure 

All conda packages have a specific sub-directory structure inside the tarball file. There is a 
`bin` directory that contains any binaries for the package; a `lib` directory containing the 
relevant library files (i.e., the `.py` files); and an `info` directory containing package metadata. 

As an example of Conda package structure consider the [Conda](https://pytorch.org/) package for 
Python 3.6 version of PyTorch targeting a 64-bit Mac OS, `pytorch-1.1.0-py3.6_0.tar.bz2`.

<div class="highlight-bash notranslate"><div class="highlight"><pre><span></span>.
├── bin
│   └── convert-caffe2-to-onnx
│   └── convert-onnx-to-caffe2
├── info
│   ├── LICENSE.txt
│   ├── about.json
│   ├── files
│   ├── git
│   ├── has_prefix.json
│   ├── hash_input.json
│   ├── index.json
│   ├── paths.json
│   ├── recipe/
│   └── test/
└── lib
    └── python3.6
        └── site-packages
            ├── caffe2/
            ├── torch/
            └── torch-1.1.0-py3.6.egg-info/
</pre></div>
</div>


## What are Conda channels?

channels are URLS to directories where certain sets of conda packages are downloaded from.

The `conda` command 
searches a default set of channels, and packages are automatically downloaded and updated from the 
[Anaconda Cloud channels](https://repo.anaconda.com/pkgs/). 

*   `main`: The majority of all new Anaconda, Inc. package builds are hosted here. Included in 
    conda's defaults channel as the top priority channel.
*   `r`: Microsoft R Open conda packages and [Anaconda, Inc.'s R conda packages](https://anaconda.org/r/repo). 


Collectively, the Anaconda managed channels are referred to as the `defaults` channel because, 
unless otherwise specified, packages installed using `conda` will be downloaded from these 
channels. 





## install a package from a specific channel

You can install a package from a specific channel into the currently activate environment by passing the --channel option to the conda install command as follows.

```bash
$ conda activate machine-learning-env
$ conda install scipy=1.6 --channel conda-forge
```

This command would install tensorflow package from conda-forge channel into an environment installed into the env/ sub-directory.

```bash
$ conda install tensorflow=1.14 --channel conda-forge --prefix ./env
```

You may specify multiple channels for installing packages by passing the --channel argument multiple times.

```bash
$ conda install scipy=1.6 --channel conda-forge --channel bioconda
```

Search for a package in a specific channel

```bash
$ conda install scipy=1.6 --channel conda-forge --channel bioconda
```


# Exercise 1

Like many projects, PyTorch has its own channel on Anaconda Cloud. This channel has several interesting packages, in particular pytorch (PyTorch core) and torchvision (datasets, transforms, and models specific to computer vision).

Create a new directory called my-computer-vision-project and then create a Python 3.6 environment in a sub-directory called env/ with the two packages listed above. Also include the most recent version of jupyterlab in your environment (so you have a nice UI) and matplotlib (so you can make plots).

## Answer (dont post immediately)

```bash
$ mkdir my-computer-vision-project
$ cd my-computer-vision-project/
$ conda create --prefix ./env --channel pytorch \
 python=3.6 \
 jupyterlab=1.0 \
 pytorch=1.1 \
 torchvision=0.3 \
 matplotlib=3.1
```

## What happens when you install a package?

[Installation of a conda package](https://docs.conda.io/projects/conda/en/latest/user-guide/concepts/installing-with-conda.html)


## Conda (+Pip): Conda wherever possible; Pip only when necessary

When using Conda to manage environments for your Python project it is a good idea to install packages available via both Conda and Pip using Conda; however there will always be cases where a package is only available via Pip in which case you will need to use Pip. Many of the common pitfalls of using Conda and Pip together can be avoided by adopting the following practices.

- Always explicitly install pip in every Python-based Conda environment.
- Always be sure your desired environment is active before installing anything using pip.
- Prefer `python -m pip install` over `pip install`; never use `pip` with the `--user` argument.

