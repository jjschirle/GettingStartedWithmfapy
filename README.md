# Getting started with VSCode, Python, and mfapy

As you know, [mfapy](https://www.sciencedirect.com/science/article/pii/S2214030121000171?via%3Dihub) is a Python toolbox for metabolic flux analysis. This guide will take you through being able to use the package as though you are starting from scratch. Skip to the parts that are relevant.

# Prerequisites
## Install VSCode
VSCode is my preferred text editor for a few reasons. It's relatively simple, integrated terminal (which will be useful later), some built-in support for debugging code (different than R, but I find it more useful), tons of extensions for additional functionality (such as more intelligent code error flagging), and my favorite: support for different languages (ex. Python and Jupyter notebooks!), integration with Git, etc.
- You can download VSCode [here](https://code.visualstudio.com/)
- Once you've downloaded VSCode, click the 'extensions' button on the left-hand side panel (or `shift + cmd + X`). Search for and install:
    - Python (this installs support for python in VSCode, not python itself)
    - Jupyter
## Install Python
- Install [Homebrew](https://brew.sh/), a package manager for MacOS. Open your terminal and type `brew install python`.
- Or download from the [Python website](https://www.python.org/).
## Install Git
Git is a version control system. For the purposes of mfapy, it allows us to download the source code easily.
- If you have MacOS/homebrew, open your terminal and type `brew install git`.
- Or download for Windows [here](https://git-scm.com/downloads)


# Getting started with mfapy
## Dowloading the mfapy source code
Consider the following folder structure:
```
Some_awesome_folder/
├── Data/
│   └── readme.md
├── Projects/
│   └── Awesome_Metabolite_Analysis/
└── Source_Code/
    └── mfapy
```

Say you want to download the mfapy source code to the `Source_Code` folder. You'll have to:
- use the `cd` command to get to this directory. Ex. `cd path/to/Source_Code`
- Type `git clone https://github.com/fumiomatsuda/mfapy.git`. This will dowload all the files from the [mfapy github](https://github.com/fumiomatsuda/mfapy)

## Creating a project folder.
- Say you want the folder for your metabolite analysis in your `Projects` folder. I would create the `Awesome_Metabolite_Analysis` as a subdirectory in `Projects`, then open VSCode, select the open folder option, and then select `../Projects/Awesome_Metabolite_Analysis`.

## A note on virtual environments (optional)
A **virtual environment** is a tool that allows you to create isolated environments for your projects. Essentially, if you want to work with `pandas` dataframes, you can install pandas to your *global* environment (any time you attempt to use pandas it may try to use whatever version you have here).

Alternatively, you can install it into your *virtual environment*. When you import pandas, this time it will import the version you have installed in your `venv`, ensuring no dependency issues as packages update when you try to run this code in a couple years. It's extra work, but it's good practice to avoid conflicts.

### Creating a virtual environment
- Once you've opened your `Awesome_Metabolite_Analysis` folder in VSCode, open the terminal in VSCode (click terminal in the top panel, then 'new terminal'). You can create a virtual environment by typing `python3 -m venv venv` in your VSCode terminal. 
    - If on **Windows**, type `venv/Scripts/activate`
    - If on **macOS**, type `source venv/bin/activate`

## Installing required packages
If you've activated your virtual environment, then packages will install to it! You can confirm by the prompt in your VSCode terminal having `(venv)`.
For mfapy, you'll need to type `pip3 install jupyter, ipykernel, numpy, scipy, joblib, nlopt, matplotlib`.

As an aside, I would also encourage exploring [plotly](https://plotly.com/python/), Justin Bois' [iqplot](https://iqplot.github.io/user_guide/user_guide.html), and [bokeh](https://bokeh.org/) graphing libraries as they support some nice customizability and have hover-interactable data. However, it does look like [ggplot](https://plotnine.org/) is ported to python, however I have not attempted to use it.

## Installing mfapy to this environment
Now, use the `cd` command to navigate to the directory that holds your mfapy clone. In the VSCode terminal, we can install mfapy using the command `python3 -m pip install .`.

## Testing the installation
Per the mfapy documentation, we should use the `cd` command to navigate back to `Awesome_Metabolite_Analysis`. Next, run the unit test script by typing `python3 -m unittest`.

## Now, actually using mfapy (and other modules)
We are finally ready to use mfapy! In python, we can import modules and access their methods with the import statement. For mfapy we can include `import mfapy` at the top of our script/notebook. 


# Some other python tutorial stuff
## A note on filetypes and python modules
`.py` files:
- A `.py` file is a python script, similar to an R script. They can be executed from the command line and terminal in our interpreter (VSCode).
- More efficient (faster) than a notebook if running a task that you want to run in its entirety, without interaction or intervention.
`.ipynb` files:
- `.ipynb` files are notebooks creater by Jupyter notebook. They can contain both Markdown text and code. Code is executed in cells, making them user friendly for interactive data analysis and visualizations. Great for running segments of code at a time or debugging.
Python modules
- Python modules contain python code that defines various functions, classes, and variables. They allow us to use classes or functions from different files. This is analagous to R's `source(some_file.R)` with the syntax `import some_file`.

## Some common packages you may find useful at some point
- `jupyter`: A web application that allows you to create and share documents containing live code, equations, visualizations, and narrative text. It's widely used for data analysis, machine learning, and educational purposes.
- `ipykernel`: This package provides the IPython kernel for Jupyter. It enables you to run Python code in Jupyter notebooks, allowing for interactive computing and visualizations.
- `numpy`: A powerful library for numerical computing in Python. It provides support for arrays, matrices, and a wide range of mathematical functions to operate on these data structures. It's essential for scientific computing and serves as the foundation for many other libraries.
- `pandas`: A library that provides high-performance data manipulation and analysis tools. It introduces data structures like DataFrames, which allow for efficient handling of structured data, making it easier to perform operations like filtering, aggregating, and transforming datasets.
- `matplotlib`, `plotly`, `bokeh`, `seaborn`: popular graphing libraries like ggplot.
- `scikit-learn`: A machine learning library that provides simple and efficient tools for data mining and data analysis. It features various algorithms for classification, regression, clustering, and more, making it accessible for both beginners and experienced practitioners.

## Python resources/tutorials
For syntax (apart from Python docs):
- [A Whirlwind Tour of Python](https://github.com/jakevdp/WhirlwindTourOfPython)
- [learnxinyminutes — Python3](https://learnxinyminutes.com/docs/python/)
- [GeeksforGeeks](https://www.geeksforgeeks.org/python-programming-language-tutorial/)
