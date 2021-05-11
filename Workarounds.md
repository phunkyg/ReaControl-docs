To work around Big Sur installation issues for pypcap dependency:

Instead of using pip to install pypac, we can install manually with a small modification.

Download the source ZIP from: https://github.com/pynetwork/pypcap

Unpack to a non restricted location, I used /User/Shared/

Modify the file setup.py

Locate line 87

Comment out line 87 and 88

Add a new line: lib_file_path = '/usr/lib'

The block of code should now look like this:

    if not lib_file_path:
        print("None of the following found: %s" % lib_files)
        #sys.exit(1)
        #return
        lib_file_path = '/usr/lib'
        

Save and exit

Start a command line at this folder
Install the package manually:

python setup.py install



