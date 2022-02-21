# Accessing Servers

## Softwares to install (Windows)
- __X2GO Client for remote access__ 
  - [Download](https://wiki.x2go.org/doku.php/doc:installation:x2goclient) and install X2Go client.
  - Open X2Go and create a new Session,
    - Give it a Session name (e.g., `dittlab-backend`)
    - Fill in Server-Host: `dittlab-backend.tudelft.nl`
    - Fill in Server-Login: `your NetID`
    - Leave Server-SSH Port as `22`
    - Select Session type as `MATE`
    - Click `OK`, then the new session would appear in the session list.
  - Click on the created session and a box would appear with your login name filled in. Enter `the password of your NetID` in the Password field, then click `OK`.

- __Cyberduck/WinSCP to transfer files__
  - [Download](https://winscp.net/eng/download.php) and install WinSCP.
  - On startup, WinSCP would ask you to setup,
    - Select File protocol: `SFTP`
    - Fill in Host name: `dittlab-backend.tudelft.nl`
    - Leave Port number as `22`
    - Fill in User name: `your NetID`
    - Either 1) enter `the password of your NetID` in the Password field and WinSCP will save it, or 2) Leave the Password field empty and WinSCP will ask for it every time when you login.

- __Terminal/OpenSSH: ssh to the machine__

## Access the Backend
- Either through terminal or remote access 
- ssh username@dittlab-backend@tudelft.nl


## Setup your own python environment
Dittlab-backend has python 3.8.10 and pip 20.0.2 installed. They can be checked by entering `python3` (Use Ctrl+D to exit python, and another Ctrl+D to close the terminal window) and by entering `pip --version` or `pip3 --version`.
- __Update python and pip__ 
  - You are not allowed to update python as this requires superuser permisson.
  - Update pip by `python3 -m pip install --user --upgrade pip`.
- __Setup Conda__ 
  - Install Miniconda or Anaconda referring to the [User guide](https://docs.conda.io/projects/continuumio-conda/en/latest/user-guide/install/linux.html).
  - Take Miniconda as the example, the specific steps are
    - Connect to dittlab-backend via X2Go and open MATE Terminal by either 1) the black icon in the top bar, or 2) Applications -> System Tools -> MATE Terminal
    - Download the installer by either 1) [downloading](https://docs.conda.io/en/latest/miniconda.html#linux-installers) `Miniconda3 Linux 64-bit` and use WinSCP to transfer the file to dittlab-backend (take the root directory `/home/yourNetID/` as the example), or 2) in the terminal entering `wget https://repo.anaconda.com/miniconda/Miniconda3-py39_4.11.0-Linux-x86_64.sh` (this saves the installer to /home/yourNetID/), note that the version is the latest as of 21 Feb 2022 and could be updated
    - In the terminal, enter `sha256sum filename` to verify the encrypted hash. If the previous steps are followed, here the filename is `Miniconda3-py39_4.11.0-Linux-x86_64.sh`; if the installer is saved in another directory, the filename requires an absolute path, i.e., it should be like `/home/yourNetID/yourFolderName/Miniconda3-py39_4.11.0-Linux-x86_64.sh`
    - In the terminal, enter `bash filename`
    - Follow the installation instruction on the screen (if you are unsure about the setting, accept the defaults)
    - When the installation is complete, close and reopen the terminal and you would see `(base) yourNetID@dittlab-backend:-$`.
  - To update Conda, open MATE Terminal and enter `conda update conda`.
  - Conda's base environment now is automatically activated when you open a terminal. In case you don't want this, enter `conda config --set auto_activate_base false` in the terminal. From then on, you will need to use `conda activate` to activate conda.
- __Code with local editor or Visual Studio Code__




## Tunneling jupyter notebook
Tunnel the notebook only from your personal python environment
- https://github.com/Panchamy/Dittlab-PhD/blob/main/Tuneling_Jupyter_server_-_Jupyter_Notebook.pdf
