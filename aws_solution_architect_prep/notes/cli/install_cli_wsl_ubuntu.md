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
* Install the AWS CLI with pip
* Upgrading to the latest version of the AWS CLI
* Add the AWS CLI Executable to Your Command Line Path
* Installing Python on Linux
* Install the AWS CLI on Amazon Linux
### Install pip, if necessary
First, check for pip and for pip version:
```sh
$ pip --version
```
Proceed with steps to install pip as needed:
```sh
$ sudo apt-get update
$ sudo apt-get install python3-distutils
$ curl -O https://bootstrap.pypa.io/get-pip.py
```
When the --user flag is included with the command below, the script installs pip to the path ~/.local/bin.
```sh
$ python3 get-pip.py --user
```
### Install the CLI tool using pip
```sh
$ sudo apt-get install aws
```
Verify installation:
```sh
$ aws s3 ls
```
The above should list all s3 bucket names if the CLI tool installed successfully; otherwise, the following messages may display:
"access denied" 
"invalid key"
The messages above may necessitate re-creation of the keys previously generated for providing access via the CLI
### Upgrade to latest version of CLI
Check for outdated packages:
```sh
pip3 list -o
```
If CLI is outdated, get latest version:
```sh
pip3 install --upgrade --user awscli
```
### Add the CLI Executable to your Path:
```sh

```
verify folder used by pip to install the CLI:
$ which aws

* Add the AWS CLI Executable to Your Command Line Path


```
Run ls -al to determine where the output to the executable points and if different from the folder added to your path when installing pip, be sure to add this folder revealed in the output to your path as well; e.g.:
* Install the AWS CLI on Amazon Linux
