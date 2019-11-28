---
layout: post
title: How to install Anaconda on WSL2 and create virtual environments
---


1. Download the newest version of Anaconda from [Anaconda](https://www.anaconda.com/distribution/), on the site choose to download the Linux installer, right click the link and choose *Copy link location*.
2. Open WSL2 Terminal go to *~/Downloads* (if the folder doesn't exist create it with mkdir ~/Downloads). When in the Downloads folder write *curl -O* and then paste in the copied link from the anaconda website. It should look like this: *curl -O https://repo.anaconda.com/archive/Anaconda3-2019.10-Linux-x86_64.sh* .
3. Once the installer is finished downloading just write: *bash ~/Downloads/Anaconda3-2019.10-Linux-x86_64.sh*. This will install Anaconda into your WSL2 environment.
4. Agree to the license terms and choose to install it into the default location that the installer offers. After that Anaconda offers you to run *conda init* which you should do, this will write a script to your .bashrc file so you can run anaconda from the commandprompt. Now just enter the command *source ~/.bashrc* in your terminal, after that the Anaconda *base environment* should be activated.
5. If everything works and the *base environment* is active just type *conda deactivate* to close the *base environment*. Because I don't want to run the conda virtual environment everytime I start a new shell I now run: *conda config --set auto_activate_base False*.

Thats it for installing Anaconda, now we're going to create a new VirtuaEnv.

---

# Creating a VirtualEnvironment with Anaconda on WSL2.
Now I'm going to create a VirtualEnv for Scrapy, which is a so called Webcrawler.
1. First we have to create a new a Env, we do this with *conda create --name scrapy* where scrapy is gonna be the name of the environment. This will create environment named scrapy in *~/Anaconda3/envs*.
2. Now make sure that your environment is activated, you should see the name of your env on the left side of your Bashprompt, this tells you that it's active. In case it's not just run: *conda activate scrapy*.
3. Now to install scrapy run: *conda install -c conda-forge scrapy*. The -c indicates from where you install a Anaconda package, in this case it is *conda-forge*. To learn more about this just visit [CondaForge](https://conda-forge.org/docs/).

---

