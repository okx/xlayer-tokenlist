# X Layer Token List

A standards-compliant Uniswap Token List for the X Layer network, used by wallets (e.g., MetaMask) and dApps to discover tokens and logos.

- Token list file: `xlayer.tokenlist.json`
- Schema: Uniswap Token List (validated)

## Chains

- 196 — X Layer Mainnet (`chainId: 196`)

Chain metadata can also be found in ethereum-lists/chains.

## Current Release — v1.0.0

- Scope: Initial release of core token list for X Layer Mainnet
- Tokens (196): WOKB, WETH, USD₮0, USDC, USDG
  - **WOKB** (Wrapped OKB) — Primary wrapped token for X Layer
  - **WETH** (Wrapped Ether) — Ethereum wrapped token
  - **USD₮0** — Stablecoin
  - **USDC** (USD Coin) — USD stablecoin
  - **USDG** (Global Dollar) — Global dollar stablecoin
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
| WOKB   | Wrapped OKB   | `0xe538905cf8410324e03a5a23c1c177a474d59b2b` | 18       |
| WETH   | Wrapped Ether | `0x5a77f1443d16ee5761d310e38b62f77f726bc71c` | 18       |
| USD₮0  | USD₮0         | `0x779ded0c9e1022225f8e0630b35a9b54be713736` | 6        |
| USDC   | USD Coin      | `0x74b7f16337b8972027f6196a17a631ac6de26d22` | 6        |
| USDG   | Global Dollar | `0x4ae46a509f6b1d9056937ba4500cb143933d2dc8` | 6        |

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

---

# X Layer 代币列表

这是一个符合标准的 Uniswap 代币列表，用于 X Layer 网络，供钱包（例如 MetaMask）和 dApps 发现代币和 logo。

- 代币列表文件：`xlayer.tokenlist.json`
- 架构：Uniswap Token List（已验证）

## 链网络

- 196 — X Layer 主网（`chainId: 196`）

链元数据也可以在 ethereum-lists/chains 中找到。

## 当前版本 — v1.0.0

- 范围：X Layer 主网核心代币列表初始版本
- 代币 (196)：WOKB、WETH、USD₮0、USDC、USDG
  - **WOKB** (Wrapped OKB) — X Layer 的主要包装代币
  - **WETH** (Wrapped Ether) — 以太坊包装代币
  - **USD₮0** — 稳定币
  - **USDC** (USD Coin) — 美元稳定币
  - **USDG** (Global Dollar) — 全球美元稳定币
- Logo：
  - 所有 logo 均从 OKLink 引用，确保高可用性和加载速度

## 使用方法

### 钱包/dApp 集成

支持 Uniswap 代币列表的钱包和 dApps 可以直接导入此列表文件。

### 程序化验证

```bash
# 架构验证
npx ajv-cli validate -s token-lists/src/tokenlist.schema.json -d xlayer.tokenlist.json

# 地址校验和验证
node -e "const {toChecksumAddress}=require('web3-utils');const l=require('./xlayer.tokenlist.json');for(const t of l.tokens){if(t.address!==toChecksumAddress(t.address))throw new Error('Bad checksum '+t.address)}console.log('OK')"
```

## 版本控制与验证

### 语义化版本控制

版本控制遵循 Uniswap 的语义化版本指南：

- **Major（主版本）**：删除代币或更改代币地址/chainId（针对以前发布的代币）
- **Minor（次版本）**：添加代币
- **Patch（补丁版本）**：元数据更新（名称、符号、logo、小数位）

### 验证覆盖

- Uniswap JSON 架构
- EIP-55 地址校验和
- 重复代币检测
- Logo 链接可用性验证（HTTP 200）

## 代币列表详情

| 符号  | 名称          | 地址                                         | 小数位 |
| ----- | ------------- | -------------------------------------------- | ------ |
| WOKB  | Wrapped OKB   | `0xe538905cf8410324e03a5a23c1c177a474d59b2b` | 18     |
| WETH  | Wrapped Ether | `0x5a77f1443d16ee5761d310e38b62f77f726bc71c` | 18     |
| USD₮0 | USD₮0         | `0x779ded0c9e1022225f8e0630b35a9b54be713736` | 6      |
| USDC  | USD Coin      | `0x74b7f16337b8972027f6196a17a631ac6de26d22` | 6      |
| USDG  | Global Dollar | `0x4ae46a509f6b1d9056937ba4500cb143933d2dc8` | 6      |

## Logo 资源

- 所有 logo 均从 OKLink 官方 CDN 托管
- Logo 链接格式遵循 OKLink 标准
- 确保在所有平台上的一致显示

## 贡献指南

欢迎社区贡献！如需添加新代币或更正现有信息：

1. **Fork 本仓库**
2. **提交 Pull Request**，包含以下信息：
   - 代币名称（name）
   - 代币符号（symbol）
   - 小数位（decimals）
   - 合约地址（address，必须是 EIP-55 校验和格式）
   - 链 ID（chainId: 196）
   - Logo URI（logoURI，推荐使用 OKLink CDN 或其他稳定的图像托管服务）
3. **确保所有信息准确无误**，特别是合约地址

### 添加新代币要求

- 代币必须已在 X Layer 主网上部署
- 提供有效的合约地址（已验证）
- Logo 必须可公开访问且符合尺寸要求
- 代币信息必须准确（名称、符号、小数位）

## 相关链接

- X Layer 官网：`https://www.okx.com/xlayer`
- X Layer 区块浏览器：`https://www.oklink.com/xlayer`
- OKLink：`https://www.oklink.com`
- Chain ID：196

---

**注意**：使用本代币列表时，请务必进行自己的研究（DYOR）。本列表仅供参考，不构成投资建议。
