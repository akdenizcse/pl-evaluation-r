# R Programming Language
## Author: Ross Ihaka and Robert Gentleman
## Developer: R Core Team
## History
---
>R is a system for statistical computation and graphics. It consists of a language plus a run-time environment with graphics, a debugger, access to certain system functions, and the ability to run programs stored in script files.  
R is created by Ross Ihaka and Robert Gentleman at University of Auckland. Initial version of R is released at 1995 and first stable version of R is released in 29th February 2000. R is named from its creators initials which is 'R'.      
Since mid-1997 there has been a core group (the “R Core Team”) who can modify the R source code archive. The group currently consists of Doug Bates, John Chambers ( creator of the S programming language ), Peter Dalgaard, Robert Gentleman, Kurt Hornik, Ross Ihaka, Tomas Kalibera, Michael Lawrence, Friedrich Leisch, Uwe Ligges, Thomas Lumley, Martin Maechler, Martin Morgan, Paul Murrell, Martyn Plummer, Brian Ripley, Deepayan Sarkar, Duncan Temple Lang, Luke Tierney, and Simon Urbanek.  
Design of R is mostly influenced by languages S, Commom-Lisp and Scheme.
  
---
### R is invented for several reasons. 
Which is: 
* R is under GNU license so it is open source. 
* R can run on Windows, Mac OS and Linux.
* R has wide variety of packages.
* R is mostly used for data analysis. In data analysis, real data will have missing value issues. In R many functions have arguments that control how to handle missing values in the data.
---
### When to use R?
>R is designed to be used in statistical analysis:  
1. Data visualizations, risk performance analysis in financial Applications.

2. Social media analytics, to analyze user sentiments & improve their experiences. Makes it easier to target potential customers.

3. Healthcare industries for drug discovery, pre-clinical trials & analyzing drug safety. Also used to predict the spread of diseases.

4. In manufacturing to optimize the products to have minimum production cost and maximum profit.

---
## How to setup and use R
---
R setup can be done in several ways.  
For Windows: 
1. First way is to use the official R website and use CRAN mirrors to obtain R. Go to:  
 [http://lib.stat.cmu.edu/R/CRAN/](http://lib.stat.cmu.edu/R/CRAN/)  
 Download R from base subdirectory.  
For developing programs using R, best environment is RStudio and it can be downloaded from:  
 [http://rstudio.org/download/desktop](http://rstudio.org/download/desktop)  
 Install RStudio.

2. Second way is to use Anaconda. Anaconda comes with Python and R and all developing environments pre-installed such as RStudio for R and Spyder,Pycharm for Python.  
To install Anaconda on your Windows system, go to: [https://www.anaconda.com/products/individual](https://www.anaconda.com/products/individual)  
Download Anaconda Graphical Installer for Windows (32 or 64 bit depending on your system).

For Mac OS:
1. First way is to use official R website and use CRAN mirrors to obtain R. Go to:  
[https://cran.r-project.org/bin/macosx/](https://cran.r-project.org/bin/macosx/)  
Download the latest release and install using default configuration.  
For developing programs using R, best environment is RStudio and it can be downloaded from:  
 [http://rstudio.org/download/](http://rstudio.org/download/)  
 Under All Installations section, download the installer for Mac OS.  
 Install RStudio.
 2. Second way is to use Anaconda. Anaconda comes with Python and R and all developing environments pre-installed such as RStudio for R and Spyder,Pycharm for Python.  
To install Anaconda on your Mac OS system, go to: [https://www.anaconda.com/products/individual](https://www.anaconda.com/products/individual)  
Download Anaconda Graphical Installer for Mac (64 bit).

For Linux:  
1. First way to install R is using the terminal:  
For Ubuntu:  <p>sudo apt update</p>  <p>sudo apt upgrade -y</p><p>sudo apt -y install r-base</p>  For Fedora:  <p>dnf install -y R</p> For Arch:  <p>pacman -S R</p>  For OpenSuse:  
Using YaST tool, install R-base and R-devel.  
For RStudio go to:  
[https://rstudio.com/products/rstudio/download/](https://rstudio.com/products/rstudio/download/)  
Download the corresponding installer for your system.

2. Second way to install R is Anaconda.  
To install Anaconda on your linux based system:    
First install prerequisites:  
For Ubuntu: <p>apt-get install libgl1-mesa-glx libegl1-mesa libxrandr2 libxrandr2 libxss1 libxcursor1 libxcomposite1 libasound2 libxi6 libxtst6</p>  
For RedHat: <p>yum install libXcomposite libXcursor libXi libXtst libXrandr alsa-lib mesa-libEGL libXdamage mesa-libGL libXScrnSaver</p>  
For Arch: <p>pacman -Sy libxau libxi libxss libxtst libxcursor libxcomposite libxdamage libxfixes libxrandr libxrender mesa-libgl  alsa-lib libglvnd</p>  
For OpenSuse: <p>zypper install libXcomposite1 libXi6 libXext6 libXau6 libX11-6 libXrandr2 libXrender1 libXss1 libXtst6 libXdamage1 libXcursor1 libxcb1 libasound2  libX11-xcb1 Mesa-libGL1 Mesa-libEGL1</p>  
After installing prerequisites:  
Go to:  
[https://www.anaconda.com/products/individual#linux](https://www.anaconda.com/products/individual#linux)  
Download the installer.  
After downloading the installer, use:  <p>bash ~/Downloads/Anaconda3-"Replace with version of Anaconda"-Linux-x86_64.sh</p>to install Anaconda.  
Anaconda comes with both R and RStudio so no reason for install RStudio externally.

# Example Codes
 
```R
#Delete missing data
df <- data.frame(
  V1 = c(1,3,6,NA,7,1,NA,9,15),
  V2 = c(7,NA,5,9,12,NA,NA,2,3),
  V3 = c(NA,12,5,6,3,7,2,NA,31)
)

na.omit(df)


```
```R
## Delete variable
df <- Hitters
df[sample(1:nrow(df), 7), "Hits"] <- NA 
df[sample(1:nrow(df), 9), "Runs"] <- NA
df[sample(1:nrow(df), 5), "RBI"] <- NA

```

```R
#Deleting Variables in Multi-Variate Data Set
#Examination of deficiencies on the basis of variables
apply(df, 2, function(x) sum(is.na(x)) / length(x))
e_d <- apply(df, 2, function(x) sum(is.na(x)) / length(x))
#Importing in dataframe
e_d <- as.data.frame(e_d)
#Adding variable names as variables
e_d$degisken_isimleri <- rownames(e_d) 
#Accessing variables above a certain rate
e_d[e_d$e_d > 0.02,] 
#Choosing Variables
e_d[e_d$e_d > 0.02,]$degisken_isimleri 
#Deleting the selected variables for the main data set
e_d_d <- df %>% select(-c(e_d[e_d$e_d > 0.02,]$degisken_isimleri))
str(e_d_d)
```
---








