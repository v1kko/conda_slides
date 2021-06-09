---
theme : "simple"
transition: "slide"
height: 1080
highlightTheme: "monokai"
#logoImg: "logo.png"
#slideNumber: false
title: "Introduction to conda"
---
<style>
  .reveal section p {
    font-size: 0.6em;
    line-height: 1.2em;
  }

  .ic {
    background: #ddd;
    font-family: monospace;
  }
</style>
## Introduction to conda

### setting up the environment

---


## Let's start with a question

- What would you use environments for?
 
  - https://hackmd.io/@Uq1CWlKHSA-BBaTuPwE06g/HywQN705_/edit

---

<section data-background-iframe="https://hackmd.io/@Uq1CWlKHSA-BBaTuPwE06g/HywQN705_/edit"
          data-background-interactive>
</section>

---

### Create workspace for Conda environments

If you haven't done it yet, create a new `introduction-to-conda-for-data-scientists`{: .ic } directory on your Desktop in order to maintain a consistent workspace for all your conda environment. 

For osx and linux the following commands should create the directory
```bash
$ cd ~/Desktop
$ mkdir introduction-to-conda-for-data-scientists
$ cd introduction-to-conda-for-data-scientists
```

For Windows users you may need to reverse the direction of the slash and run 
the commands from the command prompt.
~~~
> cd ~\Desktop
> mkdir introduction-to-conda-for-data-scientists
> cd introduction-to-conda-for-data-scientists
~~~
{: .language-bash}

---

## What are conda environments

- A [Conda environment](https://docs.conda.io/projects/conda/en/latest/user-guide/concepts/environments.html) 
is a directory that contains a specific collection of Conda packages that you have installed.<!-- .element: class="fragment" -->

- Conda can switch between environments quickly and easily<!-- .element: class="fragment" -->

- Removing or installing packages does not affect other conda environments<!-- .element: class="fragment" -->

- A conda environment can be created with the `conda create`{: .ic } command<!-- .element: class="fragment" -->

- <!-- .element: class="fragment" -->

<!--```bash
$ conda create --name python36-env python=3.6
``` -->

<!-----

## Some live coding

<!--```bash
conda activate #activate base environment
# create new environment with python 3.6 and pandas
conda create --name my_env python=3.6 pandas 
conda activate my_env #activate the newly created environment
```
-->

---

## Excercise 1

1. Create a new environment called “machine-learning-env” with Python and the most current versions of IPython, Matplotlib, Pandas, Numba and Scikit-Learn.
2. How would you specify a specific version of python to work with in this environment ? 

Link to conda commands: [Conda general commands](https://docs.conda.io/projects/conda/en/latest/commands.html
)

<!---

## (some) conda commands

```bash
$ conda search
$ conda activate
$ conda deactivate
$ conda create
```

Link to conda commands: [Conda general commands](https://docs.conda.io/projects/conda/en/latest/commands.html
)
-->

---

## Excercise 2

Dask provides advanced parallelism for data science workflows enabling performance at scale for the core Python data science tools such as Numpy Pandas, and Scikit-Learn. Have a read through the [official documentation](https://docs.conda.io/projects/conda/en/latest/commands.html) for the `conda install`{: .ic } command and see if you can figure out how to install Dask into the `machine-learning-env`{: .ic } that you created in the previous challenge.

--

## Some live coding 

<!--```bash
conda activate #activate base environment
# create new environment with python 3.6 and pandas
conda create --name my_env python=3.6 pandas 
conda activate my_env #activate the newly created environment
```
-->


---

## Where do conda environments live?

- By default they live somewhere in your home folder `/Users/$USERNAME/miniconda3/envs`{: .ic }  or `C:\Users\$USERNAME\Anaconda3`{: .ic } (windows)<!-- .element: class="fragment" -->

- `/home/$user/miniconda3/envs`{: .ic } (linux)<!-- .element: class="fragment" -->

- We can see all environments by using ls (linux) or dir (windows) on this folder.<!-- .element: class="fragment" -->

- Or we can run `conda info –envs`{: .ic } or `conda env list`{: .ic }<!-- .element: class="fragment" -->

- <!-- .element: class="fragment" -->

---

## Local conda environments

- Conda environments can be installed in a different place<!-- .element: class="fragment" -->

- Local conda environments do not show up with `conda env list`{: .ic }<!-- .element: class="fragment" -->

- Local environments make the code more reproducible<!-- .element: class="fragment" -->

- Uses the `--prefix`{: .ic} argument instead of the `--name`{: .ic} argument<!-- .element: class="fragment" -->


- <!-- .element: class="fragment" -->

---

## Excercise 3

First create a project directory called project-dir using the following command.
```bash
$ mkdir project-dir
$ cd project-dir
```
Next, create a new environment inside the newly created `project-dir` in a sub-directory called `env` an install Python 3.6, version 3.1 of Matplotlib, and version 2.0 of TensorFlow.

Afterwards, try to activate and deactivate this environment.

---

## Quality of life improvement

- Short name for local conda environments: 
```bash
$ conda config --set env_prompt '({name})'
```


![cat](./cat.gif)

--

## Another set of handy commands

```bash
# list packages in the macinge learning environment
$ conda list --name machine-learning-env  
# list packages in a local conda environment
$ conda list --prefix /path/to/conda/env
```

---

## Conda can create environments for R projects too!

--

~~~bash
$ conda create --prefix ./env \
> r-base \
> r-tidyverse \
> r-sparklyr \
~~~


---

## Excercise 5

Create a new directory called `r-project-dir`{: .ic}.
Take a look at the [list of R packages](https://anaconda.org/r/repo) available by default for installation. Finally create a new local conda environment within the `r-project-dir`{: .ic} with some R packages (you choose!).

---

## Cleaning up

```bash
$ conda remove --name my_env --all
$ conda remove --prefix /path/to/local/env --all
```

As a last excercise, clean up all environments `conda env list`{: .ic} and local environments!

