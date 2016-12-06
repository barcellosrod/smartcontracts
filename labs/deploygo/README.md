# WALLET

peer node start --peer-chaincodedev

cd $GOPATH/src/github.com/hyperledger/fabric/examples/chaincode/go/chaincode_getgoing
CORE_CHAINCODE_ID_NAME=gg CORE_PEER_ADDRESS=0.0.0.0:7051 ./chaincode_getgoing


 peer chaincode deploy -n gg -c '{"function":"init", "args":["a", "100", "b", "200"]}'
 
 peer chaincode invoke -l golang -n gg -c '{"function":"invoke","args":["a","b","10"]}'
 
 peer chaincode query -l golang -n gg -c '{"function":"query","args":["b"]}'

 # REGISSTRY


#start go code
CORE_CHAINCODE_ID_NAME=myassets2 CORE_PEER_ADDRESS=0.0.0.0:7051 ./finished

peer chaincode deploy -n myassets2 -c '{"function":"init", "args":["hello_world", "ola"]}'

peer chaincode invoke -n myassets2 -c '{"function":"invoke", "args":["hello_world", "ola_mundo"]}'

peer chaincode query -l golang -n myassets2 -c '{"function":"read","args":["hello_world"]}'