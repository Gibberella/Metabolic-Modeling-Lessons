# Metabolic Modeling Lessons

# Prerequisites
All of the hands-on exercises in this repository are written in Python and packaged in Jupyter Notebooks. Python is a programming language commonly used in many different applications, including scientific computation and data analysis. Jupyter Notebooks are simply a way of viewing and interacting with Python code that allow us to quickly and easily view things like plots and graphs in the same environment we're doing our coding it. It also allows us to create some easy-to-use interfaces for interacting with our metabolic modeling simulations.

To run all of the content in this repository, you need to have the following things installed:
1. **Anaconda**
2. **JupyterLab**
3. **ipykernel**
4. **seaborn**
5. **ipywidgets**
6. **cobrapy**
7. **mfapy**

Please follow the instructions below in the sequence presented to ensure you have everything you need installed on your system prior to running the metabolic modeling lesson code. For Linux or Win32 installation instructions, refer to the "Linux_Installation_Instructions" and "Win32_Installation_Instructions" files in this repository.

## Installation guide

Python is the language our code is written in, but we'll be installing Anaconda, which is a "distribution" of Python (along with R) that comes prepackaged with some of the essential add-ons we want when we're doing scientific computation.

### 1. Go to the Anaconda website and download the installer

Follow the link here: https://www.anaconda.com/products/individual. Download the latest version of Anaconda Individual Edition to your system and execute the installer. Follow all instructions. After installation, confirm that it's been successfully installed by opening up the **Anaconda Prompt** - this should be accessible from your Start Menu or equivalent, depending on your OS. This will open up a command line interface. Don't be scared! We're only going to be copy-pasting some lines of code to install the rest of the stuff we need and then we won't be using the command line again.

### 1a. Mac Users only
Your OS does not have the package installer 'pip' installed automatically. To install it, type

```
sudo easy_install pip
```
into your Terminal Prompt to install it. 

You may need to use your password for admin installation.

Then, follow the guide as normal, but remember that your "Command Prompt" is called "Terminal"!

### 2. Making and activating an environment for the packages we're going to install 
Please make and then activate a new Anaconda environment specifically for this workshop. You can do this by opening up the **Anaconda Prompt** and typing:

```
conda create --name ModelingWorkshop
```

Followed by

```
conda activate ModelingWorkshop
```

You'll then carry out all the following steps in that environment. Note that each time you start up the Anaconda Prompt to launch into Jupyterlab for our exercises, you'll need to first type 


```
conda activate ModelingWorkshop
```

before proceeding.


### 3. Install JupyterLab

From the **Anaconda Prompt**, enter the following code:

```
pip install jupyterlab==3.3.2
```
This will install JupyterLab, the interace we'll be using to interact with the metabolic modeling simulations, onto your system. If any (y/n) prompts come up during the installation, enter "y", without the quotation marks, and press enter. Once the installation is complete, confirm that everything worked by typing the following into the **Anaconda Prompt**:
```
jupyter lab
```
A page with an interface like the one in the image below should show up in your default browser. Leave that open for now while we install the rest of the required packages.

![](JupyterLabExampleResized.png)

### 4. Install ipykernel

From the **Anaconda Prompt**, type 

```
conda install ipykernel==6.9.1
```
Once you've done that, type
```
ipython kernel install --user --name=ModelingWorkshop
```

### 5. Install seaborn

From the **Anaconda Prompt**, enter the following code:

```
pip install seaborn==0.11.2
```

### 6. Install ipywidgets

As you will see, the metabolic models we'll be working with have interactive sliders to allow you to vary parameter values. For this functionality, we'll need the latest version of the ipywidgets package. As before, from your **Anaconda Prompt**, type in and execute the following code:

```
pip install ipywidgets==7.6.5
```
If any (y/n) prompts come up during the installation, enter "y" and press enter.

### 7. Install cobrapy

In order to demonstrate Flux Balance Analysis (FBA) modeling, we'll need the Python distribution of COBRA. As before, from your **Anaconda Prompt**, type in and execute the following code:

```
pip install cobra
```
If any (y/n) prompts come up during the installation, enter "y" and press enter.

### 8. Install mfapy

In order to demonstrate Metabolic Flux Analysis (MFA) modeling, we'll need a python package called *mfapy*. This is slightly more involved than the installations for the other packages. 

a. Go to https://github.com/fumiomatsuda/mfapy

b. Download a .zip file of the contents of the repository and unpack it somewhere easy to navigate to on your system.

c. Open the **Anaconda Prompt**

d. First, we need to install some dependencies. Type and enter:

```
conda install -c conda-forge nlopt
```
e. Next, type and enter:
```
conda install -c anaconda mkl-service
```
f. Navigate to the folder you unpacked on your system by typing
```
cd *path here*
```
For example, I unpacked the folder onto my Desktop, so I typed in:
```
cd C:\Users\Joshua Kaste\Desktop\mfapy-master
```
g. Type and enter:
```
python setup.py install
```
h. If any (y/n) prompts come up during the installation, enter "y" and press enter.

### 9. Confirm that everything is running

We have a quick test notebook you can run to ensure that everything is installed correctly and functional. On the 2022 Metabolic Modeling Workshop GitHub page, you should see a bright green "Code" button to the top right of the file browser above all of this instructional text. Please click that and then select the bottom-most option on the drop-down (**Download Zip**) to download the contents of this GitHub repository. Once you've done that, unpack the contents of the repository to wherever is most convenient for you on your system. Then, **from the JupyterLab interface** in your browser, navigate to the folder you just unpacked. There will be a file titled
```
Day00_TestNotebook.ipynb
```
in the folder. Close out of the Anaconda Prompt you were in before, open it up again, and activate the workshop environment with:

```
conda activate ModelingWorkshop
```

Then, type:

```
jupyter lab
```

Open this in JupyterLab and you should see something like the image below. In the top-right of the Jupyter lab interface you should see a small circle with a name next to it - click the name and you'll be presented with a list of "kernels" to choose from. Select the **"ModelingWorkshop"** option. Then, follow the instructions in the notebook to run the single block of code in. Scroll down to confirm that the output below the code reads: "All Good!". This means that everything has been successfully installed.
