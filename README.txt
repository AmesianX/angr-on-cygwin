This time is not work..
현재 버전에서 작동하지 않음

# $ mkdir angr
# $ cd angr
# $ git clone https://github.com/libffi/libffi.git
# $ git clone https://github.com/angr/angr-doc.git
# $ git clone https://github.com/angr/simuvex.git
# $ git clone https://github.com/angr/cle.git
# $ git clone https://github.com/angr/vex.git
# $ git clone https://github.com/angr/pyvex.git
# $ git clone https://github.com/angr/archinfo.git
# $ git clone https://github.com/angr/fidget.git
# $ git clone https://github.com/angr/angr.git
# $ git clone https://github.com/angr/binaries.git
# $ git clone https://github.com/angr/claripy.git
# $ git clone https://github.com/angr/angr.github.io.git
# $ git clone https://github.com/angr/angr-z3.git
# $ git clone https://github.com/angr/angr-management.git
# $ git clone https://github.com/angr/angr-dev.git
# $ git clone https://github.com/angr/wheels.git
# $ cd ..

#-------------
# [+] BEGIN 
#-------------

$ patch -p0 < ./angr_on_cygwin_patch.diff
$ easy_install-2.7 pip
$ pip install rpyc
$ pip install futures
$ pip install networkx
$ pip install cachetools
$ pip install mulpyplexer
$ pip install progressbar
$ pip install cooldict
$ pip install ana
$ pip install archinfo
$ pip install capstone
$ cd angr/libffi
$ ./autogen.sh
$ ./configure
$ make
$ make install
$ cd ../angr
$ python setup.py install
$ cd ../angr-z3
$ python scripts/mk_make.py
$ cd build
$ make
$ make install
$ cp libz3.dll /usr/lib/libz3.dll
$ cd ..
$ python setup.py install
$ cd ../pyvex
$ python setup.py install
$ cd ../simuvex
$ python setup.py install
$ cd ../cle
$ python setup.py install

#--------------------------------------------------------------------
# [+][WARN] You must uninstall the pre-installed claripy from pip..!!
#--------------------------------------------------------------------

$ pip uninstall claripy
$ cd ../claripy
$ python setup.py install
$ cd ..

#-------------
# [+] END
#-------------

$ python

Python 2.7.10 (default, Jun  1 2015, 18:05:38)
[GCC 4.9.2] on cygwin
Type "help", "copyright", "credits" or "license" for more information.
>>> import angr
>>>
