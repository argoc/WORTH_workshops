# WORTH_workshops

To put this folder and its Jupyter notebooks on your PYNQ board

On your pynq board, add git if not there:

    sudo apt-install git

and then

    cd /home/xilinx/jupyter_notebooks/
    git clone https://github.com/argoc/WORTH_workshops.git

Or if it cannot see the internet, do the git clone on a local machine and then scp or use a network drive connection to copy the files to the pynq board, i.e.:

    scp -r WORTH_workshops xilinx@pynq:/home/xilinx/jupyter_notebooks/

