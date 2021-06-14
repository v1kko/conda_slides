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
 
  - tinyurl.com/3ejxxb7a

---

<section data-background-iframe="https://hackmd.io/@Uq1CWlKHSA-BBaTuPwE06g/ByYDT9xsO/edit"
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


## Excercise 1

1. Create a new environment called “machine-learning-env” with Python and the most current versions of IPython, Matplotlib, Pandas, Numba and Scikit-Learn.
2. How would you specify a specific version of python to work with in this environment ? 

Link to conda commands: [Conda general commands](https://docs.conda.io/projects/conda/en/latest/commands.html
)


---

## Excercise 2

Dask provides advanced parallelism for data science workflows enabling performance at scale for the core Python data science tools such as Numpy Pandas, and Scikit-Learn. Have a read through the [official documentation](https://docs.conda.io/projects/conda/en/latest/commands.html) for the `conda install`{: .ic } command and see if you can figure out how to install Dask into the `machine-learning-env`{: .ic } that you created in the previous challenge.


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

## Excercise 4

Create a new directory called `r-project-dir`{: .ic}.
Take a look at the [list of R packages](https://anaconda.org/r/repo) available by default for installation. Finally create a new local conda environment within the `r-project-dir`{: .ic} with some R packages (you choose!).

---

## Cleaning up

```bash
$ conda remove --name my_env --all
$ conda remove --prefix /path/to/local/env --all
```

As a last excercise, clean up all environments and local environments!

