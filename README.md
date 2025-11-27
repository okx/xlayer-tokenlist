# X Layer Token List

A standards-compliant Uniswap Token List for the X Layer network, used by wallets (e.g., MetaMask) and dApps to discover tokens and logos.

- Token list file: `https://raw.githubusercontent.com/okx/xlayer-tokenlist/refs/heads/main/xlayer.tokenlist.json`
- Schema: Uniswap Token List (validated)

## Chains

- 196 — X Layer Mainnet (`chainId: 196`)

Chain metadata can also be found in ethereum-lists/chains.

## Current Release — v1.0.0

- Scope: Initial release of core token list for X Layer Mainnet
- Tokens (196): WOKB, WETH, USD₮0, USDC
  - **WOKB** (Wrapped OKB) — Primary wrapped token for X Layer
  - **WETH** (Wrapped Ether) — Ethereum wrapped token
  - **USD₮0** — Stablecoin
  - **USDC** (USD Coin) — USD stablecoin
- Logos:
  - All logos are referenced from OKLink to ensure high availability and fast loading

## Usage

### Wallet/dApp Integration

Wallets and dApps that support Uniswap Token Lists can directly import this list file.

### Programmatic Validation

```bash
# Schema validation
npx ajv-cli validate -s token-lists/src/tokenlist.schema.json -d xlayer.tokenlist.json

# Checksum validation
node -e "const {toChecksumAddress}=require('web3-utils');const l=require('./xlayer.tokenlist.json');for(const t of l.tokens){if(t.address!==toChecksumAddress(t.address))throw new Error('Bad checksum '+t.address)}console.log('OK')"
```

## Versioning & Validation

### Semantic Versioning

Versioning follows Uniswap's SemVer guidance:

- **Major**: Remove tokens or change token address/chainId (for previously published tokens)
- **Minor**: Add tokens
- **Patch**: Metadata updates (name, symbol, logo, decimals)

### Validation Coverage

- Uniswap JSON schema
- EIP-55 address checksums
- Duplicate token detection
- Logo link availability verification (HTTP 200)

## Token List Details

| Symbol | Name          | Address                                      | Decimals |
| ------ | ------------- | -------------------------------------------- | -------- |
| WOKB   | Wrapped OKB   | `0xe538905cf8410324e03A5A23C1c177a474D59b2b` | 18       |
| WETH   | Wrapped Ether | `0x5A77f1443D16ee5761d310e38b62f77f726bC71c` | 18       |
| USD₮0  | USD₮0         | `0x779Ded0c9e1022225f8E0630b35a9b54bE713736` | 6        |
| USDC   | USD Coin      | `0x74b7F16337b8972027F6196A17a631aC6dE26d22` | 6        |

## Logo Resources

- All logos are hosted on OKLink's official CDN
- Logo link format follows OKLink standards
- Ensures consistent display across all platforms

## Contributing

Community contributions are welcome! To add new tokens or correct existing information:

1. **Fork this repository**
2. **Submit a Pull Request** with the following information:
   - Token name (name)
   - Token symbol (symbol)
   - Decimals (decimals)
   - Contract address (address, must be in EIP-55 checksum format)
   - Chain ID (chainId: 196)
   - Logo URI (logoURI, recommend using OKLink CDN or other stable image hosting services)
3. **Ensure all information is accurate**, especially the contract address

### Requirements for Adding New Tokens

- Token must be deployed on X Layer Mainnet
- Provide valid contract address (verified)
- Logo must be publicly accessible and meet size requirements
- Token information must be accurate (name, symbol, decimals)

## Links

- X Layer Website: `https://www.okx.com/xlayer`
- X Layer Block Explorer: `https://www.oklink.com/xlayer`
- OKLink: `https://www.oklink.com`
- Chain ID: 196

---

**Disclaimer**: When using this token list, please do your own research (DYOR). This list is for reference only and does not constitute investment advice.
