# liquidswap-example

First, init Aptos account.

```
$ aptos init
```

Compile the module.

```
$ aptos move compile --named-addresses example=default
{
  "Result": [
    "DEF4FD6D729DF63138266827E5428BD621099F2ADE0AC62B2B18786B884E61C7::example"
  ]
}
```

Publish the module.

```
$ aptos move publish --named-addresses example=default
```

Run entry function.

```
$ aptos move run --function-id DEF4FD6D729DF63138266827E5428BD621099F2ADE0AC62B2B18786B884E61C7::example::get_aptos_usdt_exchange_rate --args u64:100000
{
  "Result": {
    "changes": [
      {
        "address": "def4fd6d729df63138266827e5428bd621099f2ade0ac62b2b18786b884e61c7",
        "data": {
          "authentication_key": "0xdef4fd6d729df63138266827e5428bd621099f2ade0ac62b2b18786b884e61c7",
          "coin_register_events": {
            "counter": "1",
            "guid": {
              "id": {
                "addr": "0xdef4fd6d729df63138266827e5428bd621099f2ade0ac62b2b18786b884e61c7",
                "creation_num": "0"
              }
            }
          },
          "sequence_number": "4"
        },
        "event": "write_resource",
        "resource": "0x1::account::Account"
      },
      {
        "address": "def4fd6d729df63138266827e5428bd621099f2ade0ac62b2b18786b884e61c7",
        "data": {
          "coin": {
            "value": "9970"
          },
          "deposit_events": {
            "counter": "1",
            "guid": {
              "id": {
                "addr": "0xdef4fd6d729df63138266827e5428bd621099f2ade0ac62b2b18786b884e61c7",
                "creation_num": "1"
              }
            }
          },
          "withdraw_events": {
            "counter": "0",
            "guid": {
              "id": {
                "addr": "0xdef4fd6d729df63138266827e5428bd621099f2ade0ac62b2b18786b884e61c7",
                "creation_num": "2"
              }
            }
          }
        },
        "event": "write_resource",
        "resource": "0x1::coin::CoinStore<0x1::aptos_coin::AptosCoin>"
      }
    ],
    "gas_used": 27,
    "success": true,
    "version": 24316001,
    "vm_status": "Executed successfully"
  }
}
```