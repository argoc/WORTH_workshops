# WORTH_workshops

How to put this folder and its Jupyter notebooks on your PYNQ board.

First, determine if your PYNQ board can access the internet by opening a terminal on it (open 192.168.2.99 in the browser, log in, and choose terminal) and trying to ping github.com. If it cannot get to github.com, then either troubleshoot with these instructions:
    https://www.nengo.ai/nengo-pynq/connect.html 

Note that you may also need to change the board's IP address to make this work.

Or skip to method 2.

## Method 1

Assumes you have internet access on your pynq board. Open a terminal window on the board (or ssh to it), then:

On your pynq board, add git if not there:

    sudo apt-install git

and then

    cd /home/xilinx/jupyter_notebooks/
    git clone https://github.com/argoc/WORTH_workshops.git

## Method 2

If your board cannot see the internet, do the git clone on your local machine:

    git clone https://github.com/argoc/WORTH_workshops.git

and then scp or use a network drive connection to copy the files to the pynq board, i.e.:

    scp -r WORTH_workshops xilinx@pynq:/home/xilinx/jupyter_notebooks/

Linux and MAC have scp; Windows can get scp from MinGW. 

If you don't want to install MinGW, you can use a network drive like so: https://pynq.readthedocs.io/en/v2.0/getting_started.html#accessing-files-on-the-board