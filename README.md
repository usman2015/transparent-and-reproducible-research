# bitss-rt2-2020-jupyter
A repository with resources and instructions for the Jupyter Dynamic Documents presentation at BITSS RT2 2020

---

Please check back often for new and updated materials

For a Markdown Cheatsheet, see:

[https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)


If you have issues installing/configuring, please open up an issue in this GitHub repository

If you have any complaints/praise, please email:

Aleksandr Michuda
amichuda@ucdavis.edu

Oscar Barriga Cabanillas
obarriga@ucdavis.edu

---

## Setting up Jupyter Notebooks/ Jupyter Lab

To install Jupyter Notebooks and Rstudio, please go to [https://www.anaconda.com/download/](https://www.anaconda.com/download/) and download the newest version of the Anaconda Distribution. This application installs a Python and R environment on your desktop, as well as some helpful libraries and applications for scientific computing. **Even if you do not plan on using Python or R in the future, (which would be a shame, but regardless) please install this application.** 

After a lengthy installation process, you will have access to Jupyter notebook from the Anaconda Navigator (and notice that there is also a program called Anaconda Prompt, this will be important later). If Jupyter notebooks and/or JupyterLab does not show as installed, please click to install it as well.

## Optional (Installing kernels for other languages)

### Installing the R kernel

Although R has an amazing implementation of dynamic documents in RStudio, you might want to use R in a Jupyter Notebook if you wanted your work to render in Github or for exploration purposes.

Please go to the [IRkernel installation instructions](https://irkernel.github.io/installation/) to learn how to install it.

### Installing the Stata kernel for Jupyter Notebooks

Jupyter Notebooks come with so-called "kernels." The kernels are basically the language that will interpret your code. But the beauty of Jupyter notebooks is that they don't need to only have a Python kernel. In fact, for our purposes, a clever guy developed a Stata kernel, that will make our life very easy. The website for the kernel is [here](https://kylebarron.github.io/stata_kernel/). 

We are going to go through the installation process, but his website has instructions on how to install the stata kernel, as well as some more advanced techniques that would be useful for scientific computing (some of which we will talk about).

#### Checking if ```pip``` is installed

In order to install the Stata kernel, we need to use ```pip```, a Python program that hosts Python programs (that's so meta). To do this, go to *Anaconda Prompt* (which I mentioned before) and type:

``` 
pip --help
```

If you get output from the ```pip``` command, you're GREAT!

If this is your first foray into using a commandline, congratulations, you are now a Hacker(wo)man.
![alt text](http://peroty.com/blog/wp-content/uploads/2015/06/HACKERMAN.png "You did it!")

**Note for Windows Users**: Please follow the steps in [https://www.stata.com/automation/#install] to register your Stata with your computer before installing. 

After this, in the same Anaconda Prompt, you have open now, type:

```
pip install stata_kernel
python -m stata_kernel.install
```

If you get an error about needing to set your Stata path manually, please refer to [Troubleshooting](#Troubleshooting), on the question about your kernel always dying. After this you should be done! To check if the installation worked, go to Anaconda Navigator and open a Jupyter Notebook. In the top right corner, there will be a button for ```New``` and in the dropdown menu, you should see Stata as an option.

If you have any concerns or problems, please email us.

## Troubleshooting

1. > My stata kernel starts, but it keeps dying! What do I do?

This may be due to the stata path not being defined. There will be a file called ```.stata_kernel.conf``` in your home directory:

For Windows Users: C:/Users/\<your username\>

For Linux: /home/\<your username\>

For Mac: /Users/\<your username\>

Inside the ```.stata_kernel.conf```, you will find a variable called ```stata_path```. Write, as a string, the location of the Stata executable you are using. An example would be:

```
stata_path = "C:\Users\<your username>\Stata 15\Stata15-se.exe"
```

It should now be working!



2. > My stata kernel doesn't start and the the console states `
AttributeError: 'StataSession' object has no attribute 'stata'`

That is recent bug that has been squashed (see issue [here](https://github.com/kylebarron/stata_kernel/issues/281). Try upgrading the stata kernel: `

```
pip install stata_kernel --upgrade
```




  
