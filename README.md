# How to put this folder and its Jupyter notebooks on your Pynq board.

Already did this and want to get the new stuff? [Jump ahead](#update)

First, determine if your Pynq board can access the internet by opening a terminal on it (open 192.168.2.99 in the browser, log in, and choose terminal) and trying to ping github.com. If it cannot get to github.com, then either troubleshoot with these instructions or skip to method 2:
    https://www.nengo.ai/nengo-pynq/connect.html 

Note that you may also need to change the board's IP address to make this work.

## Method 1

If you have internet access on your Pynq board, use this method. Open a terminal window on the board (or ssh to it), then:

On your Pynq board, add git if not there:

    sudo apt-get install git

and then

    cd /home/xilinx/jupyter_notebooks/
    git clone https://github.com/argoc/WORTH_workshops.git

## Method 2

If your board cannot access the internet, do the git clone on your local machine (need git? https://git-scm.com/download):

    git clone https://github.com/argoc/WORTH_workshops.git

and then scp or use a network drive connection to copy the files to the pynq board, i.e.:

    scp -r WORTH_workshops xilinx@pynq:/home/xilinx/jupyter_notebooks/

Linux and MAC have scp; Windows can get scp from MinGW (https://sourceforge.net/projects/mingw-w64/files/latest/download). 

If you don't want to install MinGW, you can use a network drive like so: https://pynq.readthedocs.io/en/v2.0/getting_started.html#accessing-files-on-the-board

## After copying

Once you have WORTH_workshops on the Pynq board, you can navigate to it through Pynq's web interface and open the Jupyter notebook(s) contained within it.


## Get the next workshop material<a name="update"></a>

If you need to get the new stuff onto your PYNQ board, if your board can see the internet, then open a terminal window through the browser, and issue these commands:

    cd jupyter_notebooks/WORTH_workshops
    git pull

If you run into any issues with this, contact one of your workshop teachers for assistance.

If you need to get the new stuff onto your PYNQ board, and your board can't see the internet, then open a command window on your PC where you did the git clone and issue these commands:

    cd WORTH_workshops
    git pull
    scp -r workshop_1_solution xilinx@pynq:/home/xilinx/jupyter_notebooks/WORTH_workshops/

(if cd does not work, use chdir instead ... cd assumes mingw is on your system)
(your "scp" might be done through File Explorer/Finder on a MAC like you did in the initial setup if the actual scp command isn't working on your machine).

If you run into any issues with this, contact one of your workshop teachers for assistance. Note this pulls over workshop_1_soluton material; repeat as appropriate for workshop_2 and workshop_3. If you need a completely new copy, contact one of your workshop TAs/teachers for assistance.
