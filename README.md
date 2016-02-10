## python-beid - BEID helpers for Python

Those helpers are meant to be used on a RaspberryPi with Raspbian Jessie (tested on B+ and 2), but it should work fine on other platforms/OS, with perhaps some adjustments for the prerequisites.

###Installation :

    sudo apt-get install swig libpcsclite-dev libacr38u
    git clone https://github.com/LudovicRousseau/pyscard.git
    cd pyscard
    python3 setup build-ext install
    cd ..

###Utilisation :

    from beid.beid import scan_readers

    r = scan_readers()[0]
    r.read_card()
