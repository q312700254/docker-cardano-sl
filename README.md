# Build

Execute from git repository root

## Mainnet
```
docker build \
  --build-arg CARDANO_NET=mainnet \
  -t emurgo/cardano-sl:mainnet .
```
## Testnet
```
docker build \
  --build-arg CARDANO_NET=testnet \
  -t emurgo/cardano-sl:testnet .
```
## Both at once
```
for network in testnet mainnet
do
  docker build \
    --build-arg CARDANO_NET=${network} \
    -t emurgo/cardano-sl:${network} .
done
```

# Run

```
CARDANO_NET=mainnet
docker run -it \
  -p 8000:8000 \
  -p 8100:8100 \
  -p 8110:8110 \
  emurgo/cardano-sl:${CARDANO_NET}
```

You'll be able to access to:

* webui: http://localhost:8000
* api: http://localhost:8100
* websocket: http://localhost:8110
