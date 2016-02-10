## python-beid - BEID helpers for Python

Those helpers are meant to be used on a RaspberryPi with Raspbian Jessie (tested on B+ and 2), but it should work fine on other platforms/OS, with perhaps some adjustments for the prerequisites.

###Prerequesite :

Basicaly, the helpers only need pyscard, and the drivers for the reader (libacr38u for the "official" Beid readers).

Btw, for pyscard to install and work correctly with Python 3 (at least in Raspbian Jessie), one should compile and install it from git sources :

    sudo apt-get install swig libpcsclite-dev libacr38u python3-setuptools build-essential git
    git clone https://github.com/LudovicRousseau/pyscard.git
    cd pyscard
    python3 setup build_ext install
    cd ..
    rm -fr pyscard

###Installation

    git clone https://github.com/Lapin-Blanc/python-beid.git
    cd python-beid
    python3

###Utilisation :

    from beid.beid import scan_readers
    from pprint import pprint

    r = scan_readers()[0]
    pprint(r.read_card())

    infos = r.read_card(read_photo=True)
    with open("photo.jpg", "wb") as f:
        f.write(infos['photo'])