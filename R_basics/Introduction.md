## Getting started

**1. Install R**

To install R on your computer (legally for free!), go
to the home website of R 
[https://cran.r-project.org/bin/windows/base/]
www.r-project.org
and do the following (assuming you work on a windows computer):
1. click download CRAN in the left bar
2. choose a download site
3. choose Windows as target operation system
4. click base
5. choose Download R 4.3.1 for Windows2
and
choose default answers for all questions
It is also possible to run R and RStudio from a USB
stick instead of installing them. This is useful when
you don’t have administrator rights on your computer.
See our separate note “How to use portable versions
of R and RStudio" for help on this topic.

**2. Install RStudio**

After finishing this setup, you should see an "R" icon
on you desktop. Clicking on this would start up the
standard interface. We recommend, however, to use
the RStudio interface. To install RStudio, go to:
www.rstudio.com
and do the following:
1. under Download RStudio, click Download
2. below RStudio Desktop (free), click Download
3. click the version for your operating system
4. download the .exe file and run it (choose default
answers for all questions)

**3. RStudio layout**

The RStudio interface consists of several windows (see
Figure 1).
![image](https://github.com/AMR-Bioinformatics/Bioinformatics-Training/assets/109069282/c7dea8ec-43ce-4cf8-9485-d14fb4073a97)

• Bottom left: _console_ window (also called command window). Here you can type commands
after the “>” prompt and R will then execute
your command. This is the most important window, because this is where R actually does stuff.


• Top left: _editor window/source_(also called script window). Collections of commands (scripts) can be
edited and saved. When you don’t get this window, you can open it with File → New → R
script
Just typing a command in the editor window is
not enough, it has to get into the command window before R executes the command. If you want
to run a line from the script window (or the whole
script), you can click Run or press CTRL+ENTER
to send it to the command window.


• Top right: _history window/environment_. In this window you can see which data and
values R has in its memory. You can view and
edit the values by clicking on them. The history
window shows what has been typed before.


• Bottom right: _files / plots / packages / help
/viewer window/output_. Here you can open files, view
plots (also previous plots), install and load packages or use the help function.
You can change the size of the windows by dragging the grey bars between the windows.

**4. Working directory**

Your working directory is the folder on your computer
in which you are currently working. When you ask
R to open a certain file, it will look in the working
directory for this file, and when you tell R to save
a data file or figure, it will save it in the working
directory.Before you start working, please set your working
directory to where all your data and script files are or
should be stored.
Type in the console window:
setwd("directoryname"). For example:
```
> setwd("C:/Users/HP/OneDrive/Documents")
```
To check your working dircetory type in:
```
> getwd()
```
_NB_ Make sure that the slashes are forward slashes. R is case sensitive, so make sure you write capitals where necessary.
Within RStudio you can also go to Session →
Set working directory → Choose directory.


**5. Libraries**


R can do many statistical and data analyses. They
are organized in so-called packages or libraries. With
the standard installation, most common packages are
installed.

To get a list of all installed packages, go to the
packages window or type ```library() ``` in the console
window. If the box in front of the package name is
ticked, the package is loaded (activated) and can be
used.

There are many more packages available on the R
website. If you want to install and use a package (for
example, the package called “geometry") you should:

• Install the package: click install packages in
the packages window and type geometry or type
```install.packages("geometry") ``` in the command
window.

• Load the package: check box in front of geometry
or type ```library("geometry")```  in the command window.


###More resources on Baic R introduction can be found in the following sites:-

1. CRAN Installaition of R - [https://cran.r-project.org/bin/windows/base/README.R-4.3.1]
2. Basic Introduction to R layout- [https://docs.posit.co/ide/user/ide/guide/ui/ui-panes.html]
3. Introduction to R packages and libraries-  [https://www.tutorialspoint.com/r/r_packages.htm]
