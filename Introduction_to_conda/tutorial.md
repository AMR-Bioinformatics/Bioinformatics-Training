![Conda](https://upload.wikimedia.org/wikipedia/commons/e/ea/Conda_logo.svg)

# An introduction to Conda

## What is Conda?

Conda is a package and environment manager that is by far the easiest way to handle installing most of the tools we want to use in bioinformatics.

## Why conda?

1. It's an open source management system
2. Conda quickly installs, runs and updates packages and their dependencies
3. Conda easily creates, saves, loads and switches between environments on your local computer
4. Conda as a package manager helps you find and install packages
5. If you need a package that requires a different version of Python, you do not need to switch to a different environment manager, because conda is also an environment manager

### What is an environment and why are they important in conda?

A conda environment is a directory that contains a specific collection of conda packages that you have installed.  For example, you may be working on a research project that requires NumPy 1.18 and its dependencies, while another environment associated with an finished project has NumPy 1.12 (perhaps because version 1.12 was the most current version of NumPy at the time the project finished)

Conda lets us easily create and manage separate environments to avoid these types of version conflicts, and automatically checks for us when we try to install something new (so we find out now, before we break something somewhere under the hood and have no idea what happened)

The benefits go further, like helping with reproducibility

## Getting and installing Conda

Conda comes in two broad forms: Anaconda and Miniconda. Anaconda is large with lots of programs in it already, Miniconda is more lightweight and then we can install just what we want.

To get started with Conda,

For linux users and Windows users on WSL

    curl -LO https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh

For MacOS users

    curl -LO https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-x86_64.sh

Now we can install that by running it as a bash command:
```bash Miniconda3-latest-*.sh```

We need to interact with the following during installation:

    We will be asked to review the licence agreement. After pressing return/enter, we can view it and hit the space bar to advance. At the bottom, we need to type in yes to accept.
    It will then ask if the location is ok, hitting enter will place it in our current home directory, which is usually great.
    At the end it will ask if we want to initialize Miniconda3. There might be reasons to not want to do this, but until we hit one of those reasons, it probably makes things easier to say yes to that.

Great! Now we have conda installed. We just need to reload our current shell session, which we can usually do like so:

```source ~/.bash_profile || source ~/.bashrc```

And after that we should see a (base) at the start of our prompt, which tells us we are in the “base” conda environment. If the above didn’t work, you can also just open a new terminal window, and it should be updated there 👍

## Creating and navigating environments

### Base environment

The “base” conda environment is, like it sounds, kind of our home base inside conda. We wouldn’t want to install lots of complicated programs here, as the more things added, the more likely something is going to end up having a conflict. But the base environment is somewhere we might want to install smaller programs that we tend to use a lot

### Making a new environment

The simplest way we can create a new conda environment is like so:

```conda create -n new_env```

Where the base command is conda create, then we are specifying the name of our new environment with -n (here “new_env”). It will check some things out and tell us where it is going to put it, when we hit y and enter, it will be created.

### Entering an environment

To enter that environment, we need to execute:

```conda activate new_env```

And now we can see our prompt has changed to have (new_env) at the front, telling us we are in that environment.

If we had forgotten the name, or wanted to see all of our environments, we can do so with:

```conda env list```

Which will print out all of the available conda environments, and have an asterisk next to the one we are currently in.

Other useful codes include:
```
conda list #shows you everything installed in your current environment
conda list -n [ENV NAME] #shows you everything installed in the specified environment
```

### Exiting an environment

We can exit whatever conda environment we are currently in by running:

```conda deactivate```

### Making an environment with a specific python version

By default, the conda create command will use the python version that the base conda environment is running. But we can specify a different one in the command if we’d like:

```conda create -n (my_env) python=3.10```



    Breakdown

        conda create – this is our base command
        -n (my_env) – we are naming the environment “my_env”
        python=3.10 – here we are specifying the python version to use within the environment

After entering y to confirm and complete that, we can see this worked by checking our python version inside and out of these environments.

**`Exercise:`**
How do we do this?

### Removing an environment

And here is how we can remove an environment, by providing its name to the -n flag:

```conda deactivate # we can't be inside the environment we want to remove```

```conda remove --name my_env --all # --all flag asks conda to remove all dependencies as well```

Did it work? If not, can you spot why?

## Setting up the appropriate channels for Bioinformatics

Once you have successfully created your new environment, one of the first key things is to add the Bioconda channel which houses alot of Bioinformatics tools

```
conda config --add channels defaults
conda config --add channels bioconda
conda config --add channels conda-forge
```

with the highest priority being the last entry

And we can see our channel list and priority order with the following:

```conda config --get channels```

## Finding and installing packages

To install the packages (tools/programs) we want, we use the conda install command. But we need to tell conda where to look for it (conda stores and looks for packages in different “channels”), and we need to know what it is called in the conda system (usually this is just the program name we are familiar with). Let’s imagine we want to install the Integrative Genomics Viewer tool(IGV). It's a Fast, efficient, scalable visualization tool for genomics data and annotations. 

Let’s change into our “new_env” and check if prodigal is there already:

```conda activate new_env```

```igv -v```

And we get a “command not found” error if this isn’t installed on our system and accessible in our current environment. So let’s look at a common way to find it and install it through conda!

### Searching for packages

The first thing I would suggest to do, whether I know if a program is conda-installable or not, is just search in a web-browser for “conda install” plus whatever program I am looking for. For example, searching for “conda install igv” on google brings the top hit back as the igv package page on anaconda.org (which is where these are all hosted). Anaconda.org is also a great place to look if we are having trouble finding a program.

There is another option to use on the command-line

```conda search <name of package>```

This list of the different package versions that exist within conda and allows you to select a specific version

### Installing packages

Looking at the igv package page, we can see there are instructions for installing through conda. These specify where they are specifying the appropriate channel to look in with the -c flag. So we can just run this line to install igv:

```conda install -c bioconda igv```

Without defining our channels from the start of the environment, this would have been how the working method of installing igv considering that somethimes dependencies may be stored in different channels:
```conda install -c conda-forge -c bioconda -c defaults igv```

This way we get what’s needed each time, and we don’t have to worry about changing the underlying conda channel hierarchy on each system we use it on like the bioconda documentation demonstrates. 

***Can you spot how long and untidy the above piece of code looks?***

*That's why we emphasize that we define our channels from the very beginning of any new environment*

And now since the program is installed in this environment, we get the version information printed out as we should by running:

```igv -v```

 If we move out of this environment, it will not be found again (unless it is installed there too):

```conda deactivate```

```igv -v ```

`Note` What output do you get? Mark this number down on paper somewhere

### Uninstalling a package

If we wanted to remove igv, we would want to first be inside the environment that has it, so let’s switch back in to our new environment:

```conda activate new-env```

And then we would run:

```conda uninstall igv```

Once we confirm that with y and hit return, igv is once again gone:

```igv -v```

### Installing a specific version of a package

If we wanted to specify a different version of igv to install, we first need to know it exists in conda. We can see all the version types available like so:

```conda search -c bioconda igv```

```conda install -c conda-forge -c bioconda igv -c defaults igv=x.x.x```#replace the x(s) with the right numbers to install the **2nd latest version**

Just like above when we specified the python version we wanted, we can place an equals sign and then the version we want of any program we are installing.

Confirming that by entering y and hitting return finishes the installation, and we can see we have this older version now:

```igv -v```
Compare the output to what you previously put down

Once you are done with an environment, it is always proper to exit that environment. To exit an environment just type:

```conda deactivate```

## Troubleshooting tips

If you use conda long enough, it’s only a matter of time before you will run into issues where an environment will fail to install (usually with an error like “failed to resolve conflicts”, or it might just hang forever on ‘solving environment’).  If this happens, you may be able to fix the issue simply by changing the way your Conda installation handles channels.  

* first check your channel priority setting the conda configuration file with
```conda config --show channel_priority```
* then change to the opposite (e.g. if set to strict, change to flexible):
```
conda config --set channel_priority flexible
#alternatively, conda config --set channel_priority strict
```
* Now retry installing your conda environment. 

## BONUS: mamba

mamba is a drop-in replacement for conda that works to improve upon some aspects of the conda infrastructure. It can very frequently perform installations much faster (helping loads with the “solving environment” steps).

Just to get you started, here is how to install mamba on your base environment in conda but the environment option is all upto you

    conda install -n base -c conda-forge mamba

If interested, you can look for more information on mamba online
