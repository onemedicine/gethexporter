# Geth Server Prometheus Exporter
Monitor your Ethereum Geth server with Prometheus and Grafana.

<p align="center"><img width="90%" src="https://github.com/onemedicine/gethexporter/blob/master/etclabscore-gethexporter/img.png"></p>

## Docker
Run this Prometheus Exporter in a [Docker container](https://hub.docker.com/r/devfdn/gethexporter/builds/)! Include your Geth server endpoint as `GETH` environment variable.
```bash
docker run -it -d -p 9090:9090 \
  -e "GETH="http://mygethserverhere.com:8545" \
  devfdn/gethexporter
```


## Environment Variables
You can add the environment variable `ADDRESSES` with a comma delimited list of ethereum addresses.

- `GETH` = `http://eth.mygethserver.com:8545` Ethereum node endpoint
- `ADDRESSES` = `0x867fFB5a3871b500f65BdFafe0136f9667Deae06,0xF008E2c7A7F16ac706C2E0EBD3F015D442016420`
- `DELAY` = `500` millisecond delay between requests
- `METRICSADDR` = `:6061` set the server listener endpoint. Use `0.0.0.0` to make public.

## Prometheus Response
```
geth_block 7042028
geth_seconds_last_block 0.50
geth_block_transactions 48
geth_block_value 59.48321713266354
geth_block_gas_used 1243863
geth_block_gas_limit 8000000
geth_block_nonce 7516583072599285197
geth_block_difficulty 2606288773636567
geth_block_uncles 0
geth_block_size_bytes 6680
geth_gas_price 2000000000
geth_pending_transactions 136
geth_network_id 1
geth_contracts_created 0
geth_token_transfers 10
geth_eth_transfers 35
geth_load_time 0.5302
geth_address_balance{address="0x867fFB5a3871b500f65BdFafe0136f9667Deae06"} 86.99212193
geth_address_nonce{address="0x867fFB5a3871b500f65BdFafe0136f9667Deae06"} 1
geth_address_balance{address="0xF008E2c7A7F16ac706C2E0EBD3F015D442016420"} 0.1605609476
geth_address_nonce{address="0xF008E2c7A7F16ac706C2E0EBD3F015D442016420"} 95623
```
