# python-beid - BEID helpers for Python

Installation :

sudo apt-get install swig libpcsclite-dev libacr38u
git clone https://github.com/LudovicRousseau/pyscard.git
cd pyscard
python3 setup build-ext install

Utilisation :

from beid.beid import scan\_readers

r = scan\_readers()[0]
r.read\_card()
