# Help details
## Command  line  utility  for  interacting  with  Atomicals

The first line will contains your yarn version and the second line prints the command ran by yarn.

**Disclaimer**: With this tool you interact DIRECTLY with Bitcoin! Take care of each command you run, use the `--help` option before your command to be sure that you are doing what you want to do. **There is no reverse on Bitcoin.**


Usage:  Atomicals  CLI  Utility  `yarn cli command [options] <params>`
**yarn cli wallet == yarn cli**

Above there is a classification for the help output command. 

<--!
How to make this as a package to have `atomicals-cli` from npm install. 
We need to have a folder into the cli user where we store wallets and config, can be an env variable as well. 
-->


For all commands `-V, --version` and `-h --help` are valid options.
The full list of options with its command is at: [List Options](./help_options.md)

As there are a lot of commands they can be classified different if you are a **builder**, a **user** or a **maintainer** for Atomicals project.

**Builders** will use commands like `init-dmint`, `init-dft`, `mint-realm`,.... Commands to create Atoms.
**Maintainer** will use monitoring commands like `list`, `tx`, `resolve`, `events`,... Commands to monitor the network and give fresh data. 
**User** will use more `mint-dft`, `mint-item`, `mint-subrealm`,... Commands to interact with **builders** outputs. 


server-version  Get  electrumx  server  version  info

## Important commands

**SET**
`set  [options]  <atomicalIdAlias> <jsonFilename>`  Set  (update)  an  existing  Atomical  with  data.
`set-relation  [options]  <atomicalId> <relationName>  <relationValues...>`  Set  relationship  an  existing  Atomical  with  data.

**Utils**
`emit  [options]  <atomicalIdAlias> <data...>`  Emit  an  event  for  an  existing  Atomical  with  data.
`delete  [options]  <atomicalIdAlias> <filesWithDeleteKeys>`  Delete  keys  for  existing  Atomical.

`seal  [options]  <atomicalIdAlias>` Seal  any  NFT  Atomical  type  permanently  so  that  it  can  never  be  updated  or  **transferred**  ever  again. *You won't be able TO MOVE IT again!*

*Not sure it works*
`splat  [options]  <locationId>` Extract  an  NFT  Atomical  from  a  UTXO  which  contains  multiple  Atomicals

##  Wallet
`wallets  [options]` Get  balances  and  atomicals  stored  at  internal  wallets

`wallet-create` Creates  and  displays  new  12-word  secret  mnemonic  phrase  along  with  the  primary  and  funding  addresses  
`wallet-decode  [options]  <phrase>` Decode  secret  mnemonic  phrase  to  display  derive  address  and  key  at  provided  path
`wallet-init  [options]`  Initializes  a  new  wallet  at  wallet.json
`wallet-import  <wif> <alias>` Import  a  wallet  by  WIF  and  assign  it  to  provided  alias
### Address
`address  [options]  <address>`  Get  balances  and  Atomicals  stored  at  an  address
`address-history  <address>`  List  address  history  of  an  address
`address-utxos  <address>` List  all  utxos  owned  by  an  address
**Script management**
`address-script  <addressOrAlias>` Encodes  an  address  or  wallet  alias  as  the  hex  output  script
`script-address  <script>`  Decodes  a  script  as  an  address

`balances  [options]` Get  balances  and  atomicals  stored  at  internal  wallets

### Transactions/UTXO
`tx  [options]  <txid>` Get  any  transaction
`outpoint-compact  <hex>` Decodes  hex  outpoint  to  compact  location  id  form
`compact-outpoint  <compactId>` Encodes  the  compact  id  to  outpoint  hex  format
`await-utxo  <address>` <amount>  Finds  utxo  by  address

## Token
`get-ticker  [options]  <ticker>` Get  Atomical  by  ticker  name
`summary-tickers  [options]` Show  summary  of  owned  tokens  by  tickers  by  wallet
`find-tickers  [options]` Search  tickers
`ftinfo  <atomicalAliasOrId>` Get  FT  specific  info  for  an  FT  atomical
`mint-ft  [options]  <ticker> <supply>  <file>`  Mint  fungible  token  (FT)  Atomical  in  direct  issuance  mode

`split  [options]  <locationId>` Split  operation  to  separate  the  FT  Atomicals  at  a  single  UTXOs.

`custom-color  [options]  <locationId>` custom  color  operation  to  separate  the  FT  Atomicals  at  a  single  UTXOs.

### Decentralised Fungible Token (DFT)
`init-dft-perpetual  [options]  <ticker>` Initialize  perpetual  bitwork  mineable  fungible  token  (FT)  atomical  in  decentralized  issuance  mode
`init-dft-fixed  [options]  <ticker> <mintbitworkc>`  Initialize  fixed  bitwork  mineable  fungible  token  (FT)  atomical  in  decentralized  issuance  mode

## Container
`get-container  [options]  <container>` Get  Atomical  by  container  name
`get-container-items  [options]  <container> <limit>  <offset>`  Get  the  items  in  the  container
`get-container-item  [options]  <container> <itemId>`  Get  an  item  in  the  container
`validate-container-item  [options]  <containerName> <itemName>  <manifestFile>`  Validate  a  container  item  from  the  manifest
`summary-containers  [options]` Show  summary  of  owned  containers  by  wallet 
`find-containers  [options]` Search  containers
`set-container-data  [options]  <containerName>` <jsonFilename>  Update  container  data  with  json  file  contents

### DMINT
`prepare-dmint-items  <folder> <outputFolderName>`  Prepare  the  dmint  config  and  item  manifest  from  a  folder  of  images
`prepare-dmint  <folder> <mintHeight>  <bitworkc>`  Prepare  the  dmint  config  and  item  manifest  from  a  folder  of  images

`enable-dmint  [options]  <container>` <jsonFilename>  Enable  dmint  for  a  container  with  the  dmint  config  file  produced  from  the  prepare-dmint  command


## REALM
### Info
`resolve  [options]  <realm_or_subrealm>` Resolve  a  realm  or  subrealm.*Alias  for  'get-realm'*

`get-realm  [options]  <realm_or_subrealm>` Resolve  a  realm  or  subrealm.  *Alias  for  'resolve'* 
`realm-info  [options]  <atomicalIdAlias>` Get  realm  and  subrealm  information  of  an  atomical
`summary-subrealms  [options]` Show  summary  of  owned  subrealms  by  wallet 
`summary-realms  [options]` Show  summary  of  owned  realms  by  wallet
`find-realms  [options]` Search  realms
### Management 
`enable-subrealms  [options]  <realmOrSubRealm>` <file>  Set  and  enable  subrealm  minting  rules  for  a  realm  or  subrealm
`disable-subrealms  [options]  <realmOrSubRealm>` Delete  the  subrealm  minting  rules  for  a  realm  or  subrealm
`pending-subrealms  [options]` Display  pending  subrealm  Atomical  requests  and  make  payments



## General info
`get  [options]  <atomicalAliasOrId>` Get  the  status  of  an  Atomical
`location  [options]  <atomicalAliasOrId>` Get  locations  of  an  Atomical
`state  [options]  <atomicalAliasOrId>` Get  the  state  of  an  Atomical
`state-history  [options]  <atomicalAliasOrId>` Get  the  state  history  of  an  Atomical
`events  [options]  <atomicalAliasOrId>` Get  the  event  state  history  of  an  Atomical
`tx-history  [options]  <atomicalAliasOrId>` Get  the  history  of  an  Atomical
`list  [options]` List  feed  of  Atomicals  minted  globally
`address-atomicals  <address>` List  all  atomicals  owned  by  an  address
`at-location  <location>` Get  Atomicals  at  a  utxo  location

### [Bitcoin utils]
`decodetx  [options]` Decode  a  tx
`broadcast  [options]` broadcast  a  rawtx

### MINT
`mint-nft  [options]  <file>` Mint  non-fungible  token  (NFT)  Atomical
`mint-nft-json  [options]  <jsonFile>` Mint  non-fungible  token  (NFT)  Atomical  with  JSON  only  data
`mint-realm  [options]  <realm>` Mint  top  level  Realm  non-fungible  token  (NFT)  Atomical
`mint-subrealm  [options]  <realm>` Mint  subrealm  non-fungible  token  (NFT)  Atomical
`mint-container  [options]  <container>` Mint  container  non-fungible  token  (NFT)  Atomical
`mint-item  [options]  <containerName> <itemName>  <manifestFile>`  Mint  item  non-fungible  token  (NFT)  Atomical  from  a  decentralized  container
`mint-dft  [options]  <ticker>` Mint  coins  for  a  decentralized  fungible  token  (FT)

### TRANSFER
`transfer-nft  [options]  <atomicalId> <address>`  Transfer  Atomical  NFT  to  new  address
`transfer-ft  [options]  <atomicalId>` Transfer  Atomical  FT  to  other  addresses
`transfer-builder  [options]` Transfer  plain  regular  UTXOs  to  another  addresses
`transfer-utxos  [options]` Transfer  plain  regular  UTXOs  to  another  addresses

### Merge
`merge-atomicals  [options]` Merge  Atomicals  UTXOs  together  for  test  purposes

## FILE MANAGEMENT
`store-file  [options]  <filepath> <givenFileName>`  Store  general  immutable  data  transaction  that  is  not  an  NFT  or  FT
`download  [options]  <locationIdOrTxId>` Download  a  file  from  a  locationId  or  atomicalId

`help  [command]` display  help  for  command
