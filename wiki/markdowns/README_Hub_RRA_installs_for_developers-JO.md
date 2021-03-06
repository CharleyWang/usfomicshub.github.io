<h2> Software-installs for Hub developers</h2>
We have three primary methods through which we install and maintain Hub software. 

**1. Anaconda environment-manager**

   + Anaconda3
   + Anaconda2

**2. Homebrew package-manager**

**3. Install direct from source**



**Default-permissions for anything members of the omicshub group install into /shares/omicshub/apps are readable by all RRA-users. Only the omicshub group-members have write-permissions.**

   + After any installations, execute the following command on the top-level of the newly-installed directory to ensure any permissions specified in src are overwritten and that any files executable by the omicshub group are also executable by all other RRA-users:
    
            + chmod -R o+rX <directory_name>
    
    

### Creating and using module files ###

**UNDER CONSTRUCTION**

To make the module command know where to look for modules (besides default), we need to append a line to add the Hub-modulefiles path to ~/.bash_profile (here we're appending to the path, so RC system-modules--those in /apps--are searched first) :

    export MODULEPATH=$MODULEPATH:/shares/omicshub/modulefiles

   hub module-files are stored in /shares/omicshub/modulefiles/hub.apps.
   
 Best-practice to keep your environment clear of programs you don't need that could cause compatibility-problems when loading the programs you *do* need is to keep track of modules you may have already loaded, then PURGE them:
 
    module list
    module purge
   
   Next activate the module (using the seekdeep module as an example):

    module load hub.apps/seekdeep/2.6.0
    
   When you're finished, purge all your modules again:
   
    module purge




