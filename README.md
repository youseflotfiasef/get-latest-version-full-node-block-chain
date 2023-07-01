# latest_version-blockchain full node
script python get latest version blockchain (bitcoin ethereum bsc litecoin,...) send with telegram 

#arr ={"cardano":cardano_now,"walletcardano":walletcardano_now,"bsc":bsc_now,"bc":bc_now,"teron":teron_now,"tezos":teron_now,"litecoin":litecoin_now,"ethereum":ethereum_now}
import os, sys
import re
import json
from typing import Any
import requests
from http_parser.parser import HttpParser

def replace_last(source_string, replace_what, replace_with):
    head, _sep, tail = source_string.rpartition(replace_what)
    return head + replace_with + tail
#send output to telegram 
def telegram():

    bot_token = '2146359208:*******ggwTs5_lp*******'
    message = ('https://tele.sohani.me/bot'+ bot_token + '/sendMessage' )
    data = {'chat_id':-100172*********, 'text': changes}
    send = requests.post(message, data = data)
    # print(send.json())
    
#get url from github repository
```
urls = {
    'cardano':'https://github.com/input-output-hk/cardano-node/releases/latest',
    'walletcardano':'https://github.com/input-output-hk/cardano-wallet/releases/latest',
    'bsc':'https://github.com/binance-chain/bsc/releases/latest',
    'bc':'https://github.com/gavinhoward/bc/releases/latest',
    'teron':'https://github.com/tronprotocol/java-tron/releases/latest',
    'litecoin':'https://github.com/litecoin-project/litecoin/releases/latest',
    'ethereum':'https://github.com/ethereum/go-ethereum/releases/latest'
}
```

versions = []
for index,value in enumerate(urls):
    res = requests.get(urls.get(value))
    urlPaths = res.url.split("/")
    versions.append(value + ":" + urlPaths[len(urlPaths)-1])
   
f = open('/home/y.lotfiasef/Documents/version_now'+".txt", 'r')

print(versions)
result = ""
changes = ""
for i,v in enumerate(f):
    v = v.replace("\n","")
    if v != versions[i]:
        result = result + (versions[i] + "\n")        
        changes = changes + (versions[i] + "\n")     
    else:
        result = result + (v + "\n")
w = open('/home/y.lotfiasef/Documents/version_now'+".txt", 'w')
w.write(result)
w.close()
telegram ()
f.close()


