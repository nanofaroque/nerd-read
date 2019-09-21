## A "How to" - installing the AWS CLI tool to Ubuntu on WSL
> The following assists in streamlining the
> installation of the Amazon Web Services (AWS)
> command line interface (CLI) tool as much  
> as possible. The CLI tool is installed here to
> a desktop running Windows Subsystem for Linux (WSL)
> which in turn runs Ubuntu 18.04.
> Note: though a virtual environment was used here,
> this is not necessary.
## Overview
* Install pip
* Install the AWS CLI tool using pip
* Upgrade to latest version of the AWS CLI
* Add the AWS CLI Executable to Your Command Line Path
### 1. Install pip
a. Check for whether pip is installed:
```sh
$ pip --version
```
b. If needed, proceed with further steps to install pip:
```sh
$ sudo apt-get update
$ sudo apt-get install python3-distutils
$ curl -O https://bootstrap.pypa.io/get-pip.py
```
c. When the --user flag is included with the command below, the script installs pip to the path ~/.local/bin.
```sh
$ python3 get-pip.py --user
```
d. Ensure the folder containing pip is part of your PATH variable:
```sh
$ ls -a ~
```
e. If the folder containing pip is not part of your PATH variable, add it to your profile script (below example is for bash shell):
```sh
$ nano .profile
export PATH=~/.local/bin:$PATH
```
f. Finally, after adding the export command, reload your profile:
```sh
$ source ~/.profile
```
g. Confirm pip was correctly installed:
```sh
$ pip3 --version
```
### 2. Install the AWS CLI tool using pip
a. Command to install the CLI:
```sh
$ sudo apt-get install aws
```
b. Verify installation:
```sh
$ aws s3 ls
```
The above command should list all s3 bucket names if the CLI tool installed successfully; otherwise, the following messages may display:
"access denied" 
"invalid key"
Any of the two messages above may necessitate re-creation of any key previously generated for providing access via the CLI.
### 3. Upgrade to latest version of the AWS CLI
a. Check for an outdated CLI package:
```sh
pip3 list -o
```
b. If outdated, get latest version:
```sh
pip3 install --upgrade --user awscli
```
### Add the CLI executable to your Path:
a. Verify which folder was used by pip to install the CLI:
```sh
$ which aws
```
b. Determine where the output to the CLI executable points by running the ls -al command on the path to the folder where the executable is stored:
```sh
$ ls -al /home/blohmeier/anaconda3/bin/python3
```
c. if the output revealed is different from the folder added to your path when installing pip (see step 1e), be sure to add this folder revealed in the output to your path as well.
For example, the steps below result in the output following the "->" below (i.e., an output location for the python3.7 executable that is stored at /usr/bin/python3):
```sh
$ which python3
/home/blohmeier/anaconda3/bin/python3
$  ls -al /home/blohmeier/anaconda3/bin/python3
/home/blohmeier/anaconda3/bin/python3 -> python3.7
$ whereis python3.7
python3: /usr/bin/python3 /usr/bin/python3.6 /usr/bin/python3.6m /usr/lib/python3 /usr/lib/python3.6 /usr/lib/python3.7 /etc/python3 /etc/python3.6 /usr/local/lib/python3.6 /usr/share/python3 /usr/share/man/man1/python3.1.gz
```
The output from above points at a folder different from that added to the path in step 1e which was:
```sh
~/.local/bin 
```
Thus we need to add this most recent location pointed to by the output to our profile as well:
```sh
$ nano .profile
export PATH=/usr/bin:$PATH
```
