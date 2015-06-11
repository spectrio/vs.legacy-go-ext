# VSN External Go dependencies

### Changing go-ext contents

To add, remove or update libraries in go-ext, checkout the repository:

    git clone git@github.com:vs-networks/go-ext.git

Edit the Godeps file contains in the root path of the repo. See online
documentation of GPM for a description of this file format.

To update the repo based on the contents of the Godeps file:

    ./tools/update

`update` runs `gpm` in the background after cleaning up existing files and
setting the correct `GOPATH`.

Run maketar to create a new tarfile with update go-ext modules:

    cd <go-ext parent dir>
    ./go-ext/tools/maketar

This will generate a tar file with a random hex component. This random component
goes at the top of /golibs/goext in the VSN repo. It will also push the file
to files.vs-networks.com for use by others.
