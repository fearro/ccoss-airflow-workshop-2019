# Setting up your Airflow developer environment

We'll be following the official Airflow [contributing](https://github.com/apache/airflow/blob/master/CONTRIBUTING.md) guide, using [Airflow Breeze](https://github.com/apache/airflow/blob/master/BREEZE.rst) to develop.

## Pre-reqs for all platforms:

- Git & a Github account.
  - We'll be using GitHub to open Pull Requests to do our contributions
  - Make sure you have Git installed in your machine, and that your GitHub account is linked locally. This, so that you can clone repositories and push code.

- Clone / Fork Airflow:
  - Head over to https://github.com/apache/airflow and Click on the `Fork` icon on the top. This will create a fork of Airflow in your own account, which is needed to create contribution's Pull Requests. 
  - From here you can then clone your fork of github in your computer via `git clone git@github.com:<your_username>/airflow.git` or `git clone 
https://github.com/<your_username>/airflow.git`.


- Docker & Docker Compose
  - Follow the [Docker](https://docs.docker.com/install/) and the [Docker-Compose](https://docs.docker.com/compose/install/)  installation guides for your platform 
  - If you are in macOS, please increase the Docker disk space following [this guide](https://docs.docker.com/docker-for-mac/space/).

## macOS / Unix / Linux Setup

The last packages you need to install are gnu getopt and gstat. If you are in macOS, and have [homebrew](https://brew.sh/) installed you can run `brew install gnu-getopt coreutils` Finally, you will add the package folder to your path via: 
```
echo 'export PATH="/usr/local/opt/gnu-getopt/bin:$PATH"' >> ~ .bash_profile
. ~/.bash_profile
```

If you are running a **Linux** distro please install it via `apt install util-linux coreutils` , and don't forget to add the folder to your PATH.


Before running any breeze commands, make sure that you have Docker running. This can be done in macOS by opening up the Docker app from the Applications folder. You can also start it via the terminal.

After cloning your Airflow fork, head over to that new folder, usually via  `cd airflow`, and run `./breeze` . This will initialize an airflow breeze environment. Since this will download some docker images, the first run will take some time. 

After the `./breeze` command is finished, you will be all set up, and it will drop you in a shell inside the airflow container.


## Windows Setup

Unfortunately, Airflow doesn't yet support Windows. Nevertheless, here are two ways to try Breeze in Windows

### Windows 10 + WSL2

In Windows 10, we can run Breeze via [Windows Subsystem for Linux 2](https://docs.microsoft.com/en-us/windows/wsl/wsl2-install).

Please note that this will take more time to configure. However, once it's setup Docker and Breeze should be easy to install following the Linux instructions above.

### Virtual Machine / Dual-boot

Another way to run Airflow and Breeze on Windows is by creating a virtual machine with Linux.

First, install VMWare Player or VirtualBox. Then, chose a Linux distro like Ubuntu or centOS. After installing the disto, please follow the Linux instructions above. In a similar fashion, we can install a Linux distro in our hard drive, dual-booting, and then follow the Linux instructions.