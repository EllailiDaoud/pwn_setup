# install Ropper with PyVEX (for semantic analysis)
# CLI
david@david:~/Study/Auto/pwn$ git clone https://github.com/sashs/Ropper.git
cd Ropper
Cloning into 'Ropper'...
remote: Enumerating objects: 4000, done.
remote: Counting objects: 100% (106/106), done.
remote: Compressing objects: 100% (52/52), done.
remote: Total 4000 (delta 61), reused 88 (delta 53), pack-reused 3894 (from 1)
Receiving objects: 100% (4000/4000), 2.47 MiB | 1.30 MiB/s, done.
Resolving deltas: 100% (2803/2803), done.
david@david:~/Study/Auto/pwn/Ropper$ sudo pip install capstone
[sudo] password for david: 
Requirement already satisfied: capstone in /usr/local/lib/python3.10/dist-packages (5.0.5)
WARNING: Running pip as the 'root' user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv
david@david:~/Study/Auto/pwn/Ropper$ sudo pip install capstone
Requirement already satisfied: capstone in /usr/local/lib/python3.10/dist-packages (5.0.5)
WARNING: Running pip as the 'root' user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv
david@david:~/Study/Auto/pwn/Ropper$ sudo pip install filebytes
Requirement already satisfied: filebytes in /usr/local/lib/python3.10/dist-packages (0.10.2)
WARNING: Running pip as the 'root' user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv
david@david:~/Study/Auto/pwn/Ropper$ sudo pip install keystone-engine
Requirement already satisfied: keystone-engine in /usr/local/lib/python3.10/dist-packages (0.9.2)
WARNING: Running pip as the 'root' user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv
david@david:~/Study/Auto/pwn/Ropper$ python setup.py install
Command 'python' not found, did you mean:
  command 'python3' from deb python3
  command 'python' from deb python-is-python3
david@david:~/Study/Auto/pwn/Ropper$ cd ropper/
david@david:~/Study/Auto/pwn/Ropper/ropper$ ls
arch.py     gadget.py    __main__.py  ropchain   semantic.py
common      __init__.py  options.py   rop.py     service.py
console.py  loaders      printer      search.py  z3helper.py
david@david:~/Study/Auto/pwn/Ropper/ropper$ python setup.py install
Command 'python' not found, did you mean:
  command 'python3' from deb python3
  command 'python' from deb python-is-python3
david@david:~/Study/Auto/pwn/Ropper/ropper$ cd ..
david@david:~/Study/Auto/pwn/Ropper$ pip install ropper
Defaulting to user installation because normal site-packages is not writeable
Requirement already satisfied: ropper in /home/david/.local/lib/python3.10/site-packages (1.13.8)
Requirement already satisfied: filebytes>=0.10.0 in /usr/local/lib/python3.10/dist-packages (from ropper) (0.10.2)
david@david:~/Study/Auto/pwn/Ropper$ ropper
(ropper)> /bin/ls --info
*** Unknown syntax: /bin/ls --info
(ropper)> exit
*** Unknown syntax: exit
(ropper)> quit
david@david:~/Study/Auto/pwn/Ropper$ ropper --file /bin/ls --info



ELF Header
==========


Name                  Value               
----                  -----               
Class                 BITS_64
Machine               X86_64
Version               1
EntryPoint            0x0000000000006aa0
ProgramHeader Offset  64
SectionHeader Offset  136232
Flags                 0x0000000000000000
ELF Header Size       64
ProgramHeader Size    56
ProgramHeader Number  13
SectionHeader Size    64
SectionHeader Number  31

david@david:~/Study/Auto/pwn/Ropper$ sudo pip install pyvex
Collecting pyvex
  Downloading pyvex-9.2.139-py3-none-manylinux2014_x86_64.whl (3.1 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 3.1/3.1 MB 1.6 MB/s eta 0:00:00
Collecting cffi>=1.0.3
  Downloading cffi-1.17.1-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (446 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 446.2/446.2 KB 3.2 MB/s eta 0:00:00
Collecting bitstring
  Downloading bitstring-4.3.0-py3-none-any.whl (71 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 71.9/71.9 KB 1.2 MB/s eta 0:00:00
Collecting pycparser
  Downloading pycparser-2.22-py3-none-any.whl (117 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 117.6/117.6 KB 3.3 MB/s eta 0:00:00
Collecting bitarray<3.1,>=3.0.0
  Downloading bitarray-3.0.0-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (278 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 278.3/278.3 KB 3.3 MB/s eta 0:00:00
Installing collected packages: bitarray, pycparser, bitstring, cffi, pyvex
Successfully installed bitarray-3.0.0 bitstring-4.3.0 cffi-1.17.1 pycparser-2.22 pyvex-9.2.139
WARNING: Running pip as the 'root' user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv
david@david:~/Study/Auto/pwn/Ropper$ git clone https://github.com/Z3Prover/z3.git
cd z3
python scripts/mk_make.py
cd build
make
sudo make install
Cloning into 'z3'...
remote: Enumerating objects: 177163, done.
remote: Counting objects: 100% (631/631), done.
remote: Compressing objects: 100% (152/152), done.
error: RPC failed; curl 92 HTTP/2 stream 0 was not closed cleanly: CANCEL (err 8)
error: 15 bytes of body are still expected
fetch-pack: unexpected disconnect while reading sideband packet
fatal: early EOF
fatal: fetch-pack: invalid index-pack output
bash: cd: z3: No such file or directory
Command 'python' not found, did you mean:
  command 'python3' from deb python3
  command 'python' from deb python-is-python3
bash: cd: build: No such file or directory
make: *** No targets specified and no makefile found.  Stop.
make: *** No rule to make target 'install'.  Stop.
david@david:~/Study/Auto/pwn/Ropper$ 
## Insatll 
Disassembler - Ghidra/IDA/Radare/BinaryNinja/Hopper: https://gist.github.com/liba2k/d522b4...
Debugger - GDB-PwnDBG/GEF/PEDA: https://infosecwriteups.com/pwndbg-ge...
Checksec: https://github.com/slimm609/checksec.sh
Ropper:  https://github.com/sashs/Ropper

