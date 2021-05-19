# How to put this folder and its Jupyter notebooks on your Pynq board.

First, determine if your Pynq board can access the internet by opening a terminal on it (open 192.168.2.99 in the browser, log in, and choose terminal) and trying to ping github.com. If it cannot get to github.com, then either troubleshoot with these instructions or skip to method 2:
    https://www.nengo.ai/nengo-pynq/connect.html 

Note that you may also need to change the board's IP address to make this work (on Windows).

## Method 1

If you have internet access on your Pynq board, use this method. Open a terminal window on the board (or ssh to it), then:

On your Pynq board, add git if not there:

    sudo apt-get install git

and then

    cd /home/xilinx/jupyter_notebooks/
    git clone https://github.com/argoc/WORTH_workshops.git

## Method 2

If you can mount the pynq board as a network drive on your PC/Mac, you can also do the commands locally on your PC/Mac but have them written directly to the PYNQ board.

Windows: in File Explorer, click the folder on the left of the address bar showing the current directory, and then type \\pynq\\xilinx (or if that doesn't work, try \\192.168.2.99\xilinx - if you changed your IP address, use the new one, not that one!). It will prompt for a username and password, use xilinx in both and click "remember this drive" so you will not need to re-enter them.  
You now have access to the Pynq board on your PC; you should put all new notebooks under jupyter_notebooks so they show up in the Pynq web interface.

Mac: 
From the Finder menu, click Go. Click Connect to Server from Go’s drop down menu.
In the Server Address field, enter smb://192.168.2.99/xilinx
and click + to add it to your Favorite Servers, then click Connect. 
When prompted, enter username xilinx, password xilinx, and remember this password, then click Connect.
You now have access to the Pynq board on your Mac; you should put all new notebooks under jupyter_notebooks so they show up in the Pynq web interface.

## Method 3

If your board cannot access the internet, and you can't mount it as a network drive on your PC, do the git clone on your local machine (need git? https://git-scm.com/download):

    git clone https://github.com/argoc/WORTH_workshops.git

and then scp or use a network drive connection to copy the files to the pynq board, i.e.:

    scp -r WORTH_workshops xilinx@pynq:/home/xilinx/jupyter_notebooks/

Linux and MAC have scp; Windows can get scp from MinGW (https://sourceforge.net/projects/mingw-w64/files/latest/download). 

If you don't want to install MinGW, you can use a network drive like so: https://pynq.readthedocs.io/en/v2.0/getting_started.html#accessing-files-on-the-board

## After copying

Once you have WORTH_workshops on the Pynq board, you can navigate to it through Pynq's web interface and open the Jupyter notebook(s) contained within it.


## If there are updates to the workshop material<a name="update"></a>

If you need to get updates from GitHub onto your PYNQ board, if your board can see the internet, then open a terminal window through the browser, and issue these commands:

    cd jupyter_notebooks/WORTH_workshops
    git pull

If you run into any issues with this, contact one of your workshop teachers for assistance.

If you need to get the new stuff onto your PYNQ board, and your board can't see the internet, then open a command window on your PC where you did the git clone and issue these commands:

    cd WORTH_workshops
    git pull
    scp -r workshop_1_solution xilinx@pynq:/home/xilinx/jupyter_notebooks/WORTH_workshops/

(if cd does not work, use chdir instead ... cd assumes mingw is on your system)
(your "scp" might be done through File Explorer on Windows/Finder on a MAC like you did in the initial setup if the actual scp command isn't working on your machine).

If you run into any issues with this, contact one of your workshop teachers for assistance. 
