
Couch DB localhost url
```
http://localhost:5984/_utils
```

Links:

- [Chaincode for Developers](https://hyperledger-fabric.readthedocs.io/en/release-1.3/chaincode4ade.html)
- [Writing Your First Application](https://hyperledger-fabric.readthedocs.io/en/release-1.3/write_first_app.html)
- [Using CouchDB](https://hyperledger-fabric.readthedocs.io/en/release-1.3/couchdb_tutorial.html)
- [Github: fabric-samples](https://github.com/hyperledger/fabric-samples)

## TrustMe Repository

Commands

```sh
# terminal 2
CORE_PEER_ADDRESS=peer:7052 CORE_CHAINCODE_ID_NAME=gcp:0 ./generic-chain-product

# terminal 3
export CORE_LOGGING_LEVEL=INFO

peer chaincode install -p trustmechain/generic-chain-product -n gcp -v 0

peer chaincode instantiate -n gcp -v 0 -c '{"Args":[""]}' -C myc
 
peer chaincode list --instantiated -C myc

# upload product(ProductID, DynamicInfo, Timestamp)
peer chaincode invoke -n gcp -c '{"Args":["uploadProduct", "12345", "HelloProduct", "2018/11/13"]}' -C myc

# view product
peer chaincode invoke -n gcp -c '{"Args":["viewProduct", "12345"]}' -C myc
```