---
title: Core API
---

## IoTeX Chain Core API

### GetAccount

```
Usage:
  Get Account Details
Request:
  Address: Account Encoded Address
Response:
  AccountMeta: Account Metadata
```

Demo:

```
➜  ~ grpcurl -v -plaintext -d '{"address": "io1juvx5g063eu4ts832nukp4vgcwk2gnc5cu9ayd"}' 127.0.0.1:14014 iotexapi.APIService.GetAccount

Resolved method descriptor:
rpc GetAccount ( .iotexapi.GetAccountRequest ) returns ( .iotexapi.GetAccountResponse );

Request metadata to send:
(empty)

Response headers received:
content-type: application/grpc

Response contents:
{
  "accountMeta": {
    "address": "io1juvx5g063eu4ts832nukp4vgcwk2gnc5cu9ayd",
    "balance": "100000000000000000000000000",
    "pendingNonce": 1
  }
}

Response trailers received:
(empty)
Sent 1 request and received 1 response
```

### GetActions

```
Usage:
  Get Actions By Index
Request:
  ByIndex: GetActionsByIndexRequest
    -Start: Start Index of Actions
    -Count: Number of Actions
Response:
  ActionInfo: List of Action Info
```

Demo:

```
➜  ~ grpcurl -v -plaintext -d '{"byIndex": {"start": 0, "count": 2}}' 127.0.0.1:14014 iotexapi.APIService.GetActions

Resolved method descriptor:
rpc GetActions ( .iotexapi.GetActionsRequest ) returns ( .iotexapi.GetActionsResponse );

Request metadata to send:
(empty)

Response headers received:
content-type: application/grpc

Response contents:
{
  "actionInfo": [
    {
      "action": {
        "core": {
          "version": 1,
          "gasPrice": "0",
          "grantReward": {
            "height": 1
          }
        },
        "senderPubKey": "BGP1RCD6FmPHrgmDfKRMgCnTUXT0qp3Vc2lgtLgoYcR3n4bJmJFHv+WZNJqdcnJVH0jTp1rgN2675CIsNXmze7E=",
        "signature": "5LqZitihGMQRLnW++DQ0d7/O3zGbjyKlXGm/i9f3/nx2Z3HHwHRgOCqNAIXDAePZmWlb8ktmn2cyET8WXhowVAE="
      },
      "actHash": "c6f41c716b5c328fc821bd388cb73717785af91abe91c593d821332a8192ff63",
      "blkHash": "9631129b49d5894c738146a735f24982a59ba92bc03fbbf9b194bd51f2639cd2",
      "timestamp": "2019-04-16T23:37:38.925432Z"
    },
    {
      "action": {
        "core": {
          "version": 1,
          "gasPrice": "0",
          "grantReward": {
            "height": 2
          }
        },
        "senderPubKey": "BGP1RCD6FmPHrgmDfKRMgCnTUXT0qp3Vc2lgtLgoYcR3n4bJmJFHv+WZNJqdcnJVH0jTp1rgN2675CIsNXmze7E=",
        "signature": "IJRc4zS1ZZy1HsKS05TRunN2zeeHNj3dlsQu5Vd8/ywGFulMXlwGzQgDfF3sVoLVFajx7IogzxVYSGdcSI6GFgE="
      },
      "actHash": "44807c4a778adb0ee063225e77d1a0c1f65b1acfb00c67f462d7cd6e1f50a22e",
      "blkHash": "3ecddc0908f6762d8d6978594f5d75529eaac2ca6618524047b5c0b88c4b3124",
      "timestamp": "2019-04-16T23:37:48.925676Z"
    }
  ]
}

Response trailers received:
(empty)
Sent 1 request and received 1 response
```

### GetActions

```
Usage:
  Get Action By Action Hash
Request:
  ByHash: GetActionByHashRequest
    -ActionHash: Hash of Action
    -CheckPending: Wether To Check Pending Actions in Action Pool
Response:
  ActionInfo: Action Info
```

Demo:

```
➜  ~ grpcurl -v -plaintext -d '{"byHash": {"actionHash": "c6f41c716b5c328fc821bd388cb73717785af91abe91c593d821332a8192ff63", "checkPending": false}}' 127.0.0.1:14014 iotexapi.APIService.GetActions

Resolved method descriptor:
rpc GetActions ( .iotexapi.GetActionsRequest ) returns ( .iotexapi.GetActionsResponse );

Request metadata to send:
(empty)

Response headers received:
content-type: application/grpc

Response contents:
{
  "actionInfo": [
    {
      "action": {
        "core": {
          "version": 1,
          "gasPrice": "0",
          "grantReward": {
            "height": 1
          }
        },
        "senderPubKey": "BGP1RCD6FmPHrgmDfKRMgCnTUXT0qp3Vc2lgtLgoYcR3n4bJmJFHv+WZNJqdcnJVH0jTp1rgN2675CIsNXmze7E=",
        "signature": "5LqZitihGMQRLnW++DQ0d7/O3zGbjyKlXGm/i9f3/nx2Z3HHwHRgOCqNAIXDAePZmWlb8ktmn2cyET8WXhowVAE="
      },
      "actHash": "c6f41c716b5c328fc821bd388cb73717785af91abe91c593d821332a8192ff63",
      "blkHash": "9631129b49d5894c738146a735f24982a59ba92bc03fbbf9b194bd51f2639cd2",
      "timestamp": "2019-04-16T23:37:38.925432Z"
    }
  ]
}

Response trailers received:
(empty)
Sent 1 request and received 1 response
```

### GetActions

```
Usage:
  Get Actions By Address
Request:
  ByAddr: GetActionsByAddressRequest
    -Address: Encoded Address
    -Start: Start Index of Actions
    -Count: Number of Actions
Resposne:
  ActionInfo: List of Action Info
```

Demo:

```
➜  ~ grpcurl -v -plaintext -d '{"byAddr": {"address": "io1juvx5g063eu4ts832nukp4vgcwk2gnc5cu9ayd", "start": 0, "count": 1}}' 127.0.0.1:14014 iotexapi.APIService.GetActions

Resolved method descriptor:
rpc GetActions ( .iotexapi.GetActionsRequest ) returns ( .iotexapi.GetActionsResponse );

Request metadata to send:
(empty)

Response headers received:
content-type: application/grpc

Response contents:
{
  "actionInfo": [
    {
      "action": {
        "core": {
          "version": 1,
          "nonce": 1,
          "gasLimit": 10000,
          "gasPrice": "10000000000000",
          "transfer": {
            "amount": "1000000000000000000",
            "recipient": "io1sxm6zl56um2c3ntq5fwqjar4za5ka560x53muy"
          }
        },
        "senderPubKey": "BOk7WxyPumkmNlKkg61VMY5O7VtRIjFMt/2wd9jHKVCXzsku5QsRCNx0lalyDlkh5W0wSON6vmpnFtfJuRPp8uY=",
        "signature": "9mrqFBggiRocZhkRVUswxs83NaEFNdEYYczI8049vlovHEP4YMQz+3Isznc3CrYaJxAbc2PTIz7y2meerJ8bHAA="
      },
      "actHash": "060a93a4784469f9e587da0c90ed20df58b0effb50d6b8ddcd9a4c65ad55fcbd",
      "blkHash": "6344115bcd43b7315ffdf5338d0f97b26caed7734efea034a27208f64670f5e9",
      "timestamp": "2019-04-17T00:10:30.468419Z"
    }
  ]
}

Response trailers received:
(empty)
Sent 1 request and received 1 response
```

### GetActions

```
Usage:
  Get Unconfirmed Actions By Address
Request:
  UnconfirmedByAddr: GetUnconfirmedActionsByAddressRequest
    -Address: Encoded Address
    -Start: Start Index of Unconfirmed Actions
    -Count: Number of Unconfirmed Actions
Resposne:
  ActionInfo: List of Action Info
```

Demo:

```
➜  ~ grpcurl -v -plaintext -d '{"unconfirmedByAddr": {"address": "io1juvx5g063eu4ts832nukp4vgcwk2gnc5cu9ayd", "start": 0, "count": 1}}' 127.0.0.1:14014 iotexapi.APIService.GetActions

Resolved method descriptor:
rpc GetActions ( .iotexapi.GetActionsRequest ) returns ( .iotexapi.GetActionsResponse );

Request metadata to send:
(empty)

Response headers received:
content-type: application/grpc

Response contents:
{

}

Response trailers received:
(empty)
Sent 1 request and received 1 response
```

### GetActions

```
Usage:
  Get Actions By Block
Request:
  ByBlk: GetActionsByBlockRequest
    -BlkHash: Block Hash
    -Start: Start Index of Actions
    -Count: Number of Actions
Resposne:
  ActionInfo: List of ActionInfo
```

Demo:

```
➜  ~ grpcurl -v -plaintext -d '{"byBlk": {"blkHash": "6344115bcd43b7315ffdf5338d0f97b26caed7734efea034a27208f64670f5e9", "start": 0, "count": 1}}' 127.0.0.1:14014 iotexapi.APIService.GetActions

Resolved method descriptor:
rpc GetActions ( .iotexapi.GetActionsRequest ) returns ( .iotexapi.GetActionsResponse );

Request metadata to send:
(empty)

Response headers received:
content-type: application/grpc

Response contents:
{
  "actionInfo": [
    {
      "action": {
        "core": {
          "version": 1,
          "nonce": 1,
          "gasLimit": 10000,
          "gasPrice": "10000000000000",
          "transfer": {
            "amount": "1000000000000000000",
            "recipient": "io1sxm6zl56um2c3ntq5fwqjar4za5ka560x53muy"
          }
        },
        "senderPubKey": "BOk7WxyPumkmNlKkg61VMY5O7VtRIjFMt/2wd9jHKVCXzsku5QsRCNx0lalyDlkh5W0wSON6vmpnFtfJuRPp8uY=",
        "signature": "9mrqFBggiRocZhkRVUswxs83NaEFNdEYYczI8049vlovHEP4YMQz+3Isznc3CrYaJxAbc2PTIz7y2meerJ8bHAA="
      },
      "actHash": "060a93a4784469f9e587da0c90ed20df58b0effb50d6b8ddcd9a4c65ad55fcbd",
      "blkHash": "6344115bcd43b7315ffdf5338d0f97b26caed7734efea034a27208f64670f5e9",
      "timestamp": "2019-04-17T00:10:30.468419Z"
    }
  ]
}

Response trailers received:
(empty)
Sent 1 request and received 1 response
```

### GetBlockMetas

```
Usage:
  Get Block Metadata By Index
Request:
  ByIndex: GetBlockMetasByIndexRequest
    -Start: Start Block Height
    -Count: Number of Blocks
Response:
  BlkMetas: List of Block Metadata
```

Demo:

```
➜  ~ grpcurl -v -plaintext -d '{"byIndex": {"start": 1, "count": 2}}' 127.0.0.1:14014 iotexapi.APIService.GetBlockMetas

Resolved method descriptor:
rpc GetBlockMetas ( .iotexapi.GetBlockMetasRequest ) returns ( .iotexapi.GetBlockMetasResponse );

Request metadata to send:
(empty)

Response headers received:
content-type: application/grpc

Response contents:
{
  "blkMetas": [
    {
      "hash": "b7754977cae0f2a45a4ae2b7f0dfc20487e5acfa93594e5eaa1e93f5ec88800f",
      "height": 1,
      "timestamp": "2019-04-17T00:08:50.466089Z",
      "numActions": 1,
      "producerAddress": "io1sxm6zl56um2c3ntq5fwqjar4za5ka560x53muy",
      "transferAmount": "0",
      "txRoot": "285ff4de28a16dafc49d8c46d24fa99433ac08f24be8962c7a01ade65068a34a",
      "receiptRoot": "60d78681f8e531307e9ef1916f8ff8d387d922e47d0459e14d575f40ac042195",
      "deltaStateDigest": "206c92297a78c59ff6fe3a6351e755fda8ae9bb40b25084e0588b0af43445ca7"
    },
    {
      "hash": "47406baaee6af2775ef61c46373b6d0202b228f11e1a7a2f986f7d617f64f593",
      "height": 2,
      "timestamp": "2019-04-17T00:09:00.465902Z",
      "numActions": 1,
      "producerAddress": "io1sxm6zl56um2c3ntq5fwqjar4za5ka560x53muy",
      "transferAmount": "0",
      "txRoot": "d63be4dc98821a28410f694a4fd71179e79db638496a9510c67e5b1a0fc0dac4",
      "receiptRoot": "89cd1950dc9b51f8cf7078ffb38046d31e421c3add9c06abdd3cbcc99e5bf265",
      "deltaStateDigest": "8a7d0cee0eb6b6010088e0b4a2996668a29eb595ea83533b9e33fdecc15bf758"
    }
  ]
}

Response trailers received:
(empty)
Sent 1 request and received 1 response
```

### GetBlockMetas

```
Usage:
  Get Block Metadata By Block Hash
Request:
  ByHash: GetBlockMetaByHashRequest
    -BlkHash: Block Hash
Response:
  BlkMetas: Block Metadata
```

Demo:

```
➜  ~ grpcurl -v -plaintext -d '{"byHash": {"blkHash": "b7754977cae0f2a45a4ae2b7f0dfc20487e5acfa93594e5eaa1e93f5ec88800f"}}' 127.0.0.1:14014 iotexapi.APIService.GetBlockMetas

Resolved method descriptor:
rpc GetBlockMetas ( .iotexapi.GetBlockMetasRequest ) returns ( .iotexapi.GetBlockMetasResponse );

Request metadata to send:
(empty)

Response headers received:
content-type: application/grpc

Response contents:
{
  "blkMetas": [
    {
      "hash": "b7754977cae0f2a45a4ae2b7f0dfc20487e5acfa93594e5eaa1e93f5ec88800f",
      "height": 1,
      "timestamp": "2019-04-17T00:08:50.466089Z",
      "numActions": 1,
      "producerAddress": "io1sxm6zl56um2c3ntq5fwqjar4za5ka560x53muy",
      "transferAmount": "0",
      "txRoot": "285ff4de28a16dafc49d8c46d24fa99433ac08f24be8962c7a01ade65068a34a",
      "receiptRoot": "60d78681f8e531307e9ef1916f8ff8d387d922e47d0459e14d575f40ac042195",
      "deltaStateDigest": "206c92297a78c59ff6fe3a6351e755fda8ae9bb40b25084e0588b0af43445ca7"
    }
  ]
}

Response trailers received:
(empty)
Sent 1 request and received 1 response
```

### GetChainMeta

```
Usage:
  Get Blockchain Metadata
Request:
  N/A
Response:
  ChainMeta: Blockchain Metadata
```

Demo:

```
➜  ~ grpcurl -v -plaintext 127.0.0.1:14014 iotexapi.APIService.GetChainMeta

Resolved method descriptor:
rpc GetChainMeta ( .iotexapi.GetChainMetaRequest ) returns ( .iotexapi.GetChainMetaResponse );

Request metadata to send:
(empty)

Response headers received:
content-type: application/grpc

Response contents:
{
  "chainMeta": {
    "height": 88,
    "numActions": 90,
    "epoch": {
      "num": 2,
      "height": 49,
      "gravityChainStartHeight": 49
    }
  }
}

Response trailers received:
(empty)
Sent 0 requests and received 1 response
```

### GetServerMeta

```
Usage:
  Get Server Metadata
Request:
  N/A
Reponse:
  ServerMeta: Server Metadata
```

Demo:

```
➜  ~ grpcurl -v -plaintext 127.0.0.1:14014 iotexapi.APIService.GetServerMeta

Resolved method descriptor:
rpc GetServerMeta ( .iotexapi.GetServerMetaRequest ) returns ( .iotexapi.GetServerMetaResponse );

Request metadata to send:
(empty)

Response headers received:
content-type: application/grpc

Response contents:
{
  "serverMeta": {
    "packageVersion": "v0.7.0-35-g3baac429",
    "packageCommitID": "3baac429420ae74a2d1e97a866f745ca796fc192",
    "gitStatus": "clean",
    "goVersion": "go version go1.12.5 darwin/amd64",
    "buildTime": "2019-06-17-PDT/16:32:37"
  }
}

Response trailers received:
(empty)
Sent 0 requests and received 1 response
```

### SendAction

```
Usage:
  Send Action
Request:
  Action: Action
Response:
  ActionHash: Hash of Action
```

Demo:

```
➜  ~ grpcurl -v -plaintext -d '{"action": {"core": {"version": 1, "nonce": 2, "gasLimit": 10000, "gasPrice": "10", "transfer": {"amount": "100", "recipient": "io1sxm6zl56um2c3ntq5fwqjar4za5ka560x53muy"}}, "senderPubKey": "BOk7WxyPumkmNlKkg61VMY5O7VtRIjFMt/2wd9jHKVCXzsku5QsRCNx0lalyDlkh5W0wSON6vmpnFtfJuRPp8uY=", "signature": "9mrqFBggiRocZhkRVUswxs83NaEFNdEYYczI8049vlovHEP4YMQz+3Isznc3CrYaJxAbc2PTIz7y2meerJ8bHAA="}}' 127.0.0.1:14014 iotexapi.APIService.SendAction

Resolved method descriptor:
rpc SendAction ( .iotexapi.SendActionRequest ) returns ( .iotexapi.SendActionResponse );

Request metadata to send:
(empty)

Response headers received:
content-type: application/grpc

Response contents:
{
  "actionHash": "8890dca441898a3d942de05f7514f32c96afbcde1493ddd76aed1aaecb60af06"
}

Response trailers received:
(empty)
Sent 1 request and received 1 response
```

### GetReceiptByAction

```
Usage:
  Get Action Receipt By Action Hash
Request:
  ActionHash: Action Hash
Response:
  Receipt: Action Receipt
```

Demo:

```
➜  ~ grpcurl -v -plaintext -d '{"actionHash": "060a93a4784469f9e587da0c90ed20df58b0effb50d6b8ddcd9a4c65ad55fcbd"}' 127.0.0.1:14014 iotexapi.APIService.GetReceiptByAction

Resolved method descriptor:
rpc GetReceiptByAction ( .iotexapi.GetReceiptByActionRequest ) returns ( .iotexapi.GetReceiptByActionResponse );

Request metadata to send:
(empty)

Response headers received:
content-type: application/grpc

Response contents:
{
  "receiptInfo": {
    "receipt": {
      "status": 1,
      "blkHeight": 106,
      "actHash": "BgqTpHhEafnlh9oMkO0g31iw7/tQ1rjdzZpMZa1V/L0=",
      "gasConsumed": 10000,
      "contractAddress": "io1enfa3p3aysdueq85vvprzzndjs4fp6z32hf7xs"
    },
    "blkHash": "c331e7610109ab2e799b0341a57f926fe130ed6361af320a59dd8520a838e2e1"
  }
}

Response trailers received:
(empty)
Sent 1 request and received 1 response
```

### ReadContract

```
Usage:
  Read Contract State
Request:
  Action: Action (Must Be An Execution)
Response:
  Data: Return Value in Execution Receipt
```

Demo:

```
➜  ~ grpcurl -v -plaintext -d '{"action": {"core": {"version": 1, "nonce": 2, "gasLimit": 10000, "gasPrice": "10", "execution": {"amount": "0", "contract": ""}}, "senderPubKey": "BOk7WxyPumkmNlKkg61VMY5O7VtRIjFMt/2wd9jHKVCXzsku5QsRCNx0lalyDlkh5W0wSON6vmpnFtfJuRPp8uY=", "signature": "9mrqFBggiRocZhkRVUswxs83NaEFNdEYYczI8049vlovHEP4YMQz+3Isznc3CrYaJxAbc2PTIz7y2meerJ8bHAA="}}' 127.0.0.1:14014 iotexapi.APIService.ReadContract

Resolved method descriptor:
rpc ReadContract ( .iotexapi.ReadContractRequest ) returns ( .iotexapi.ReadContractResponse );

Request metadata to send:
(empty)

Response headers received:
content-type: application/grpc

Response contents:
{
  "receipt": {
    "status": 1,
    "blkHeight": 26,
    "actHash": "2bAgDlDdF84K+XNCW95wdjMpmQqVP2b04ghyMXoN6J4=",
    "gasConsumed": 10000,
    "contractAddress": "io18vlvlj0v02yye70kpqtzhu4uek3qqz27zm7g42"
  }
}

Response trailers received:
(empty)
Sent 1 request and received 1 response
```

### ReadState

```
Usage:
  Read State on Blockchain
Request:
  ProtocolID: Protocol ID
  MethodName: Method To Be Invoked To Read State
  Arguments: List of Method Arguments
  Height: BlockHeight of Request // optional, if empty, read from tip
Response:
  Data: State Result
```

Demo:

```
➜  ~ grpcurl -v -plaintext -d '{"protocolID": "cmV3YXJkaW5n", "methodName": "VW5jbGFpbWVkQmFsYW5jZQ==", "arguments": "aW8xanV2eDVnMDYzZXU0dHM4MzJudWtwNHZnY3drMmduYzVjdTlheWQ="}' 127.0.0.1:14014 iotexapi.APIService.ReadState

Resolved method descriptor:
rpc ReadState ( .iotexapi.ReadStateRequest ) returns ( .iotexapi.ReadStateResponse );

Request metadata to send:
(empty)

Response headers received:
content-type: application/grpc

Response contents:
{
  "data": "MA=="
}

Response trailers received:
(empty)
Sent 1 request and received 1 response
```

### SuggestGasPrice

```
Usage:
  Get Suggested Gas Price
Request:
  N/A
Response:
  GasPrice: Gas Price
```

Demo:

```
➜  ~ grpcurl -v -plaintext 127.0.0.1:14014 iotexapi.APIService.SuggestGasPrice

Resolved method descriptor:
rpc SuggestGasPrice ( .iotexapi.SuggestGasPriceRequest ) returns ( .iotexapi.SuggestGasPriceResponse );

Request metadata to send:
(empty)

Response headers received:
content-type: application/grpc

Response contents:
{
  "gasPrice": 1
}

Response trailers received:
(empty)
Sent 0 requests and received 1 response
```

### EstimateGasForAction

```
Usage:
  Get Estimated Gas For Action
Request:
  Action: Action
Response:
  Gas: Gas
```

Demo:

```
➜  ~ grpcurl -v -plaintext -d '{"action": {"core": {"version": 1, "nonce": 2, "gasLimit": 10000, "gasPrice": "10", "execution": {"amount": "0", "contract": ""}}, "senderPubKey": "BOk7WxyPumkmNlKkg61VMY5O7VtRIjFMt/2wd9jHKVCXzsku5QsRCNx0lalyDlkh5W0wSON6vmpnFtfJuRPp8uY=", "signature": "9mrqFBggiRocZhkRVUswxs83NaEFNdEYYczI8049vlovHEP4YMQz+3Isznc3CrYaJxAbc2PTIz7y2meerJ8bHAA="}}' 127.0.0.1:14014 iotexapi.APIService.EstimateGasForAction

Resolved method descriptor:
rpc EstimateGasForAction ( .iotexapi.EstimateGasForActionRequest ) returns ( .iotexapi.EstimateGasForActionResponse );

Request metadata to send:
(empty)

Response headers received:
content-type: application/grpc

Response contents:
{
  "gas": 10000
}

Response trailers received:
(empty)
Sent 1 request and received 1 response
```

### GetEpochMeta

```
Usage:
  Get Epoch Metadata Given an Epoch Number
Request:
  EpochNumber: Epoch Number
Response:
  EpochData: Basic Epoch Information
  TotalBlocks: Number of Blocks in the Epoch
  BlockProducersInfo: List of Block Producer Information
```

Demo:

```
➜  ~ grpcurl -v -plaintext -d '{"epochNumber": 1}' api.iotex.one:80 iotexapi.APIService.GetEpochMeta

Resolved method descriptor:
rpc GetEpochMeta ( .iotexapi.GetEpochMetaRequest ) returns ( .iotexapi.GetEpochMetaResponse );

Request metadata to send:
(empty)

Response headers received:
content-type: application/grpc
date: Wed, 17 Apr 2019 02:31:41 GMT
server: envoy
x-envoy-upstream-service-time: 15

Response contents:
{
  "epochData": {
    "num": 1,
    "height": 1,
    "gravityChainStartHeight": 7502300
  },
  "totalBlocks": 360,
  "blockProducersInfo": [
    {
      "address": "io1gh7xfrsnj6p5uqgjpk9xq6jg9na28aewgp7a9v",
      "votes": "10000000000000000000000000",
      "active": true,
      "production": 15
    },
    {
      "address": "io1scs89jur7qklzh5vfrmha3c40u8yajjx6kvzg9",
      "votes": "10000000000000000000000000",
      "active": true,
      "production": 15
    },
    {
      "address": "io159fv8mu9d5djk8u2t0flgw4yqmt6fg98uqjka8",
      "votes": "10000000000000000000000000",
      "active": true,
      "production": 15
    },
    {
      "address": "io1cup9k8hl8fp40vrj29ex8djc346780dk223end",
      "votes": "10000000000000000000000000",
      "active": true,
      "production": 15
    },
    {
      "address": "io1wv5m0xyermvr2n0wjx2cjsqwyk863drdl5qfyn",
      "votes": "10000000000000000000000000",
      "active": true,
      "production": 15
    },
    {
      "address": "io1gf08snppu2a2wfd50pjas2j6q2kcxjzqph3pep",
      "votes": "10000000000000000000000000",
      "active": true,
      "production": 15
    },
    {
      "address": "io1u5ff879gg2dw9vfpxr2tsmuaz07e2rea6gvl7s",
      "votes": "10000000000000000000000000",
      "active": true,
      "production": 15
    },
    {
      "address": "io1ar5l5s268rtgzshltnqv88mua06ucm58dx678y",
      "votes": "10000000000000000000000000",
      "active": true,
      "production": 15
    },
    {
      "address": "io1xsx5n94kg2zv64r7tm8vyz9mh86amfak9ka9xx",
      "votes": "10000000000000000000000000",
      "active": true,
      "production": 15
    },
    {
      "address": "io1x9kjkr0qv2fa7j4t2as8lrj223xxsqt4tl7xp7",
      "votes": "10000000000000000000000000",
      "active": true,
      "production": 15
    },
    {
      "address": "io1fks575kklxafq4fwjccmz5d3pmq5ynxk5h6h0v",
      "votes": "10000000000000000000000000",
      "active": true,
      "production": 15
    },
    {
      "address": "io1vtm2zgn830pn6auc2cvnchgwdaefa9gr4z0s86",
      "votes": "10000000000000000000000000",
      "active": true,
      "production": 15
    },
    {
      "address": "io12yxdwewry70gr9fs6fphyfaky9c7gurmzk8f4f",
      "votes": "10000000000000000000000000",
      "active": true,
      "production": 15
    },
    {
      "address": "io1c3r4th3zrk4uhv83a9gr4gvn3y6pzaj6mc84ea",
      "votes": "10000000000000000000000000",
      "active": true,
      "production": 15
    },
    {
      "address": "io15fqav3tugm96ge7anckx0k4gukz5m4mqf0jpv3",
      "votes": "10000000000000000000000000",
      "active": true,
      "production": 15
    },
    {
      "address": "io14vmhs9c75r2ptxdaqrtk0dz7skct30pxmt69d9",
      "votes": "10000000000000000000000000",
      "active": true,
      "production": 15
    },
    {
      "address": "io1v0q5g2f8z6l3v25krl677chdx7g5pwt9kvqfpc",
      "votes": "10000000000000000000000000",
      "active": true,
      "production": 15
    },
    {
      "address": "io1z7mjef7w528nasnsafan0rp6yuvkvq405l6r8j",
      "votes": "10000000000000000000000000",
      "active": true,
      "production": 15
    },
    {
      "address": "io1xsdegzr2hdj5sv5ad4nr0yfgpsd98e40u6svem",
      "votes": "10000000000000000000000000",
      "active": true,
      "production": 15
    },
    {
      "address": "io1nyjs526mnqcsx4twa7nptkg08eclsw5c2dywp4",
      "votes": "10000000000000000000000000",
      "active": true,
      "production": 15
    },
    {
      "address": "io1du4eq4f88n4wyc026l3gamjwetlgsg4jz7j884",
      "votes": "10000000000000000000000000",
      "active": true,
      "production": 15
    },
    {
      "address": "io127ftn4ry6wgxdrw4hcd6gdwqlq70ujk98dvtw5",
      "votes": "10000000000000000000000000",
      "active": true,
      "production": 15
    },
    {
      "address": "io1jafqlvntcxgyp6e0uxctt3tljzc3vyv5hg4ukh",
      "votes": "10000000000000000000000000",
      "active": true,
      "production": 16
    },
    {
      "address": "io15npzu93ug8r3zdeysppnyrcdu2xssz0lcam9l9",
      "votes": "10000000000000000000000000",
      "active": true,
      "production": 14
    }
  ]
}

Response trailers received:
(empty)
Sent 1 request and received 1 response
```

### GetRawBlocks

```
Usage:
  Get A List of Raw Block Data
Request:
  StartHeight: Start Block Height
  Count: Block Count
  WithReceipts: Whether to Include Action Receipts in Each Returned Block
Response:
  Blocks: A List of Raw Block Data
```

Demo:

```
➜  ~ grpcurl -v -plaintext -d '{"startHeight": 1, "count": 2, "withReceipts": true}' 127.0.0.1:14014 iotexapi.APIService.GetRawBlocks

Resolved method descriptor:
rpc GetRawBlocks ( .iotexapi.GetRawBlocksRequest ) returns ( .iotexapi.GetRawBlocksResponse );

Request metadata to send:
(empty)

Response headers received:
content-type: application/grpc

Response contents:
{
  "blocks": [
    {
      "block": {
        "header": {
          "core": {
            "version": 1,
            "height": 1,
            "timestamp": "2019-06-17T23:33:04.755448Z",
            "prevBlockHash": "N9XWktUXQo60gwwqV17n5trTKkbUp/Ob6UY841g+AtA=",
            "txRoot": "5Pn9BOMAgzj0LX9o6AD8O/FbDueiA5eS+9MUMzQ6QwY=",
            "deltaStateDigest": "tE9Ywa/2MvNDO7F8scFh9/4ijrGXTClVunKbp5eeU8M=",
            "receiptRoot": "EbGK2TCBJbVMEn04tBRy0PdceJ1O2N3IxnU7Fggjl2o="
          },
          "producerPubkey": "BB5cvAz6DM+BTzw9RADTmMqz0WPDofHDEGQ2kNl20p49+i0O2b5yH6Xc7EeqethWkyI8nw1BrrRleRkqfsHU9m8=",
          "signature": "oZxrQvUteVeq+SMCxg6I+MwJ4IkKWFzDhFi3hIQ9j9IYL69RRWsRc+pxXAjdfRCiLuCXGnkaP+nUXnR3Atm8EwA="
        },
        "body": {
          "actions": [
            {
              "core": {
                "version": 1,
                "gasPrice": "0",
                "grantReward": {
                  "height": 1
                }
              },
              "senderPubKey": "BB5cvAz6DM+BTzw9RADTmMqz0WPDofHDEGQ2kNl20p49+i0O2b5yH6Xc7EeqethWkyI8nw1BrrRleRkqfsHU9m8=",
              "signature": "gE9H+i0EZNTVHhoX7fq4xn6H8FqBrFKK0YyfcH16mrFT0rSvgVDb/ov2hAwgMh5kJVHaD8TG6UX7fayK5lpCXQA="
            }
          ]
        },
        "footer": {
          "timestamp": "0001-01-01T00:00:00Z"
        }
      },
      "receipts": [
        {
          "blkHeight": 1,
          "actHash": "5Pn9BOMAgzj0LX9o6AD8O/FbDueiA5eS+9MUMzQ6QwY=",
          "contractAddress": "io154mvzs09vkgn0hw6gg3ayzw5w39jzp47f8py9v"
        }
      ]
    },
    {
      "block": {
        "header": {
          "core": {
            "version": 1,
            "height": 2,
            "timestamp": "2019-06-17T23:33:14.756354Z",
            "prevBlockHash": "7bI37oyjBvl+TTx5Fw089xCe8AJb7YneCsmqOLiJ88k=",
            "txRoot": "qQZkW9iZ+xsl0SjVJmsIDDpQ9RcWyge/sBcvHOZFgKQ=",
            "deltaStateDigest": "S7dJ9+p/BUNaiRFQLl6+Lc/u5B5s4jlJ5LldIFwof9c=",
            "receiptRoot": "S2ZBa1FtEUSDmBqTbnS4w4RfhHfyyDJofaxL1U36+9I="
          },
          "producerPubkey": "BB5cvAz6DM+BTzw9RADTmMqz0WPDofHDEGQ2kNl20p49+i0O2b5yH6Xc7EeqethWkyI8nw1BrrRleRkqfsHU9m8=",
          "signature": "s/JZHbuZaMKOqWACHsGbezciRBSS7XYU9QuY2w3BgM8pEYWtYXZYWVJiHU3r0Z1Z7PXFMKc1glpONXkLiXwReQA="
        },
        "body": {
          "actions": [
            {
              "core": {
                "version": 1,
                "gasPrice": "0",
                "grantReward": {
                  "height": 2
                }
              },
              "senderPubKey": "BB5cvAz6DM+BTzw9RADTmMqz0WPDofHDEGQ2kNl20p49+i0O2b5yH6Xc7EeqethWkyI8nw1BrrRleRkqfsHU9m8=",
              "signature": "gMlB2v2RwSHnNuilZX89K+EOtCKDfmfouI97GO+DcU82VHm9LE4NG1TVgUQe6z94aOSHrEwyUKtINuv5QOmNIgA="
            }
          ]
        },
        "footer": {
          "timestamp": "0001-01-01T00:00:00Z"
        }
      },
      "receipts": [
        {
          "blkHeight": 2,
          "actHash": "qQZkW9iZ+xsl0SjVJmsIDDpQ9RcWyge/sBcvHOZFgKQ=",
          "contractAddress": "io154mvzs09vkgn0hw6gg3ayzw5w39jzp47f8py9v"
        }
      ]
    }
  ]
}

Response trailers received:
(empty)
Sent 1 request and received 1 response
```

### StreamBlocks

```
Usage:
  Subscribe to Block Creations
Request:
  N/A
Response:
  Block: Newly Created Block Data
```

Demo:

```
➜  ~ grpcurl -v -plaintext 127.0.0.1:14014 iotexapi.APIService.StreamBlocks

Resolved method descriptor:
rpc StreamBlocks ( .iotexapi.StreamBlocksRequest ) returns ( stream .iotexapi.StreamBlocksResponse );

Request metadata to send:
(empty)

Response headers received:
content-type: application/grpc

Response contents:
{
  "block": {
    "block": {
      "header": {
        "core": {
          "version": 1,
          "height": 365,
          "timestamp": "2019-06-18T00:36:41.655617Z",
          "prevBlockHash": "p3qrdtYuIfan08r8ZB4JFdpjaYAWUMGLrsxxn/nGO6g=",
          "txRoot": "F484nSOb8CVSNZiOETu1eEfgbwW9kGjX+zFv/OXaAvI=",
          "deltaStateDigest": "z9zsiQmR7MZh6uEBPMgPGO5snxq1YJW9ESCoZun/fD4=",
          "receiptRoot": "8Xb+12FYKrbN2mM4UiFd3htkyagI8U5xX8mtUJegmgY="
        },
        "producerPubkey": "BB5cvAz6DM+BTzw9RADTmMqz0WPDofHDEGQ2kNl20p49+i0O2b5yH6Xc7EeqethWkyI8nw1BrrRleRkqfsHU9m8=",
        "signature": "7qJKGnbCDJsfSWxuE9NYsFiqwxr6Urgz6NNu6KUZuWhygPDrEpD6uC4qgqplwFXXF7Zhlclwh7UQlaEcL0i5ZAE="
      },
      "body": {
        "actions": [
          {
            "core": {
              "version": 1,
              "gasPrice": "0",
              "grantReward": {
                "height": 365
              }
            },
            "senderPubKey": "BB5cvAz6DM+BTzw9RADTmMqz0WPDofHDEGQ2kNl20p49+i0O2b5yH6Xc7EeqethWkyI8nw1BrrRleRkqfsHU9m8=",
            "signature": "WWDGUs/EbG1mvTc2MAD06YSZ71bnXK9BBCzTezn2aQBKZCB2PiKbuzQM43dB7AZVmmY0Q7A/JOHqgq/TyZyi1wA="
          }
        ]
      },
      "footer": {
        "timestamp": "0001-01-01T00:00:00Z"
      }
    },
    "receipts": [
      {
        "blkHeight": 365,
        "actHash": "F484nSOb8CVSNZiOETu1eEfgbwW9kGjX+zFv/OXaAvI=",
        "contractAddress": "io154mvzs09vkgn0hw6gg3ayzw5w39jzp47f8py9v"
      }
    ]
  }
}
```

### StreamLogs

```
Usage:
  Get Logs filtered by contract address and Topics in stream
Request:
  Filter: LogsFilter
    -Address: List of Addresses
    -Topics: List of Topics

Response:
  Logs: List of Logs
```

Demo:

```
➜  ~ grpcurl -v -plaintext -d '{"filter": {}}'  127.0.0.1:14014 iotexapi.APIService.StreamLogs

Resolved method descriptor:
rpc StreamLogs ( .iotexapi.StreamLogsRequest ) returns ( stream .iotexapi.StreamLogsResponse );

Request metadata to send:
(empty)

Response headers received:
content-type: application/grpc

Response contents:
{
  "log": {
    "contractAddress": "io154mvzs09vkgn0hw6gg3ayzw5w39jzp47f8py9v",
    "data": "EilpbzEybWd0dG1mYTJmZm45dXF2bjB5bjM3ZjRuejQzZDI0OGwyZ2E4NRoTODAwMDAwMDAwMDAwMDAwMDAwMA==",
    "blkHeight": "4861831",
    "actHash": "f4P6zde4DcxSG+zLP8LsBXR/gwsXA8ZzMsrDI38swkw="
  }
}

```

### EstimateActionGasConsumption

```
Usage:
  Get Estimated Action Gas Consumption By Transfer
Request:
  Transfer: iotextypes.Transfer
    -Amount: Transfer Amount
    -Recipient: Recipient Address
    -Payload: Payload
  CallerAddress: Address of Caller

Response:
  Gas: Estimated Gas Amount
```

Demo:

```
➜  ~ grpcurl -v -plaintext -d '{"transfer": {"amount":"100000", "recipient":"io1juvx5g063eu4ts832nukp4vgcwk2gnc5cu9ayd"}, "callerAddress": "io1juvx5g063eu4ts832nukp4vgcwk2gnc5cu9ayd"}'  127.0.0.1:14014 iotexapi.APIService.EstimateActionGasConsumption

Resolved method descriptor:
rpc EstimateActionGasConsumption ( .iotexapi.EstimateActionGasConsumptionRequest ) returns ( .iotexapi.EstimateActionGasConsumptionResponse );

Request metadata to send:
(empty)

Response headers received:
content-type: application/grpc

Response contents:
{
  "gas": "10000"
}
```

### EstimateActionGasConsumption

```
Usage:
  Get Estimated Action Gas Consumption By Execution
Request:
  Execution: iotextypes.Execution
    -Amount: Execution Amount
    -Contract: Contract Address
    -Data: Data
  CallerAddress: Address of Caller

Response:
  Gas: Estimated Gas Amount
```

Demo:

```
➜  ~ grpcurl -v -plaintext -d '{"execution": {"amount":"0", "contract":"io154mvzs09vkgn0hw6gg3ayzw5w39jzp47f8py9v"}, "callerAddress": "io1juvx5g063eu4ts832nukp4vgcwk2gnc5cu9ayd"}' 127.0.0.1:14014 iotexapi.APIService.EstimateActionGasConsumption

Resolved method descriptor:
rpc EstimateActionGasConsumption ( .iotexapi.EstimateActionGasConsumptionRequest ) returns ( .iotexapi.EstimateActionGasConsumptionResponse );

Request metadata to send:
(empty)

Response headers received:
content-type: application/grpc

Response contents:
{
  "gas": "10000"
}
```

### GetLogs

```
Usage:
  Get Logs filtered by contract address and Topics with given Block hash
Request:
  Filter: LogsFilter
    -Address: List of Addresses
    -Topics: List of Topics
  ByBlock: GetLogsByBlock
    -BlockHash: blockhash

Response:
  Logs: List of Logs
```

Demo:

```
➜  ~ grpcurl -v -plaintext -d '{"filter": {}, "byBlock": {"blockHash": "221e7f14dddd57a739975b943bfffb1cbfcffa1ee043cf693b92af987e42ed93"}}' 127.0.0.1:14014 iotexapi.APIService.GetLogs

Resolved method descriptor:
rpc GetLogs ( .iotexapi.GetLogsRequest ) returns ( .iotexapi.GetLogsResponse );

Request metadata to send:
(empty)

Response headers received:
(empty)

```

### GetLogs

```
Usage:
  Get Logs filtered by contract address and Topics with given Range
Request:
  Filter: LogsFilter
    -Address: List of Addresses
    -Topics: List of Topics
  ByRange: GetLogsByRange
    -FromBlock: Start Block Height
    -Count: Count of Blocks

Response:
  Logs: List of Logs
```

Demo:

```
➜  ~ grpcurl -v -plaintext -d '{"filter": {}, "byRange": {"fromBlock": "12000", "count": "2"}}' 127.0.0.1:14014 iotexapi.APIService.GetLogs

Resolved method descriptor:
rpc GetLogs ( .iotexapi.GetLogsRequest ) returns ( .iotexapi.GetLogsResponse );

Request metadata to send:
(empty)

Response headers received:
content-type: application/grpc

Response contents:
{
  "logs": [
    {
      "contractAddress": "io154mvzs09vkgn0hw6gg3ayzw5w39jzp47f8py9v",
      "data": "EilpbzFjNXp3aDI0cGM0ejg3dHF3NG02ejZjNHk1NDRwd3N2OG5ycm02NhoUMTYwMDAwMDAwMDAwMDAwMDAwMDA=",
      "blkHeight": "12000",
      "actHash": "NDSsKbgjqU5jP4LWr2xoq/kpu9s8g0C4tpF/PiDTFkI="
    },
    {
      "contractAddress": "io154mvzs09vkgn0hw6gg3ayzw5w39jzp47f8py9v",
      "data": "EilpbzFjNXp3aDI0cGM0ejg3dHF3NG02ejZjNHk1NDRwd3N2OG5ycm02NhoUMTYwMDAwMDAwMDAwMDAwMDAwMDA=",
      "blkHeight": "12001",
      "actHash": "6+RK0qv5kZ3nJ014NqLlEadmnMaMS1KPWkE5mZLmSGA="
    }
  ]
}

```

### GetEvmTransfersByActionHash

```
Usage:
  Get EVM Transfer By Action Hash
Request:
  ActionHash: Action Hash

Response:
  ActionEvmTransfers: Action EVM transfer
```

Demo: TBD (will deploy soon)

### GetEvmTransfersByBlockHeight

```
Usage:
  Get EVM Transfer By Block Height
Request:
  BlockHeight: Block Height

Response:
  BlockEvmTransfers: Block EVM transfer
```

Demo: TBD (will deploy soon)
