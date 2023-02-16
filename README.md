# quickpoc

thanks [zobront](https://github.com/zobront) for sharing your repo.

Please checkout https://github.com/zobront/quickpoc for the original.

I updated this version to have the ability to use quickpoc for all evm-chains, added some flags to also handle wrongly implemented eip-1967 proxies and run slither.

Its inspired and very similar to this [PR](https://github.com/zobront/quickpoc/pull/4) - as soon as it's merged I will contribute some additions from here back.

## Usage
```bash
-c = chain-name
-r = rpc-url
-a = api endpoint
-k = api key
-p = storage location if proxy and not default eip-1967 slot 0x360894a13ba1a3210667c828492db98dca3e2076cc3735a920a3ca505d382bbc
-o = output folder - Default: current folder
```

## Helpers
For your .zshrc file
```bash
# quickpoc
export PATH="$PATH:/local_path_to_quickpoc"
alias poc-mainnet="quickpoc -c mainnet -r https://rpc.ankr.com/eth -a https://api.etherscan.io/api -k 862Y3WJ4JB4B34PZQRFEV3IK6SZ8GNR9N5 "
alias poc-bsc="quickpoc -c bsc -r https://rpc.ankr.com/bsc -a https://api.bscscan.com/api -k HFUM7BBA5MRUQCN5UMEQPUZBUPPRHIQT3Y "
alias poc-polygon="quickpoc -c polygon -r https://rpc.ankr.com/polygon -a https://api.polygonscan.com/api -k RV4YXDXEMIHXMC7ZXB8T82G4F56FRZ1SZQ "
alias poc-fantom="quickpoc -c fantom -r https://rpc.ankr.com/fantom -a https://api.ftmscan.com/api -k EH9NPZVF1HMNAQMAUZKA4VF7EC23X37DGS "
alias poc-arbitrum="quickpoc -c arbitrum -r https://rpc.ankr.com/arbitrum -a https://api.arbiscan.io/api -k X3ZWJBXC14HTIR3B9DNYGEUICEIKKZ9ENZ "
alias poc-optimism="quickpoc -c optimism -r https://rpc.ankr.com/optimism -a https://api-optimistic.etherscan.io/api -k 862Y3WJ4JB4B34PZQRFEV3IK6SZ8GNR9N5 "
```

## Known issues
- **remappings**
    depending on the implementation and verified code, you need to remove some remappings in remappings.txt and rerun the slither run
- **libraries**
    if the contract address is a Library, the created test will not work

## Examples
Thanks to [ankr](https://www.ankr.com/rpc/) and [ethereum-sources-downloader](https://github.com/SergeKireev/ethereum-sources-downloader/blob/main/src/explorer/networks.ts) we can share examples here. 
Still, it's better to just use your own rpc-endpoints and api keys.

### mainnet

```bash
quickpoc -c mainnet -r https://rpc.ankr.com/eth -a https://api.etherscan.io/api -k 862Y3WJ4JB4B34PZQRFEV3IK6SZ8GNR9N5 0xADDRESS
```

### bsc
```bash
quickpoc -c bsc -r https://rpc.ankr.com/bsc -a https://api.bscscan.com/api -k HFUM7BBA5MRUQCN5UMEQPUZBUPPRHIQT3Y 0xADDRESS
```

### polygon
```bash
quickpoc -c polygon -r https://rpc.ankr.com/polygon -a https://api.polygonscan.com/api -k RV4YXDXEMIHXMC7ZXB8T82G4F56FRZ1SZQ 0xADDRESS
```

### fantom
```bash
quickpoc -c fantom -r https://rpc.ankr.com/fantom -a https://api.ftmscan.com/api -k EH9NPZVF1HMNAQMAUZKA4VF7EC23X37DGS 0xADDRESS
```

### arbitrum
```bash
quickpoc -c arbitrum -r https://rpc.ankr.com/arbitrum -a https://api.arbiscan.io/api -k X3ZWJBXC14HTIR3B9DNYGEUICEIKKZ9ENZ 0xADDRESS
```

### optimism
```bash
quickpoc -c optimism -r https://rpc.ankr.com/optimism -a https://api-optimistic.etherscan.io/api -k 862Y3WJ4JB4B34PZQRFEV3IK6SZ8GNR9N5 0xADDRESS
```