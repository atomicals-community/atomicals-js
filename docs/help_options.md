# Help for options

This is first formating of `cat list_commands.txt | xargs -I CMD yarn cli CMD --help`

*Note: The list of all commands is into [list_commands](./list_commands.txt)*

## server-version
Usage: Atomicals CLI Utility server-version [options]

Get electrumx server version info

Options:
  -h, --help  display help for command
  
## wallet-create
Usage: Atomicals CLI Utility wallet-create [options]

Creates and displays new 12-word secret mnemonic phrase along with the primary
and funding addresses

Options:
  -h, --help  display help for command
  
## wallet-decode
Usage: Atomicals CLI Utility wallet-decode [options] <phrase>

Decode secret mnemonic phrase to display derive address and key at provided
path

Arguments:
  phrase                 string

Options:
  -p, --path <string>    Derivation path to use (default: "m/86'/0'/0'/0/0")
  --passphrase <string>  Passphrase for the wallet
  -h, --help             display help for command
  
## wallet-init
Usage: Atomicals CLI Utility wallet-init [options]

Initializes a new wallet at wallet.json

Options:
  --phrase <string>      Provide a wallet phrase
  --path <string>        Provide a path base (default: "m/86'/0'/0'")
  --passphrase <string>  Provide a passphrase for the wallet
  --n <number>           Provider number of alias
  -h, --help             display help for command
  
## wallet-import
Usage: Atomicals CLI Utility wallet-import [options] <wif> <alias>

Import a wallet by WIF and assign it to provided alias

Arguments:
  wif         string
  alias       string

Options:
  -h, --help  display help for command
  
## address-script
Usage: Atomicals CLI Utility address-script [options] <addressOrAlias>

Encodes an address or wallet alias as the hex output script

Arguments:
  addressOrAlias  string

Options:
  -h, --help      display help for command
  
## script-address
Usage: Atomicals CLI Utility `script-address [options] <script>`

Decodes a script as an address

Arguments:
  script      string

Options:
  -h, --help  display help for command
  
## outpoint-compact
Usage: Atomicals CLI Utility outpoint-compact [options] <hex>

Decodes hex outpoint to compact location id form

Arguments:
  hex         string

Options:
  -h, --help  display help for command
  
## compact-outpoint
Usage: Atomicals CLI Utility compact-outpoint [options] <compactId>

Encodes the compact id to outpoint hex format

Arguments:
  compactId   string

Options:
  -h, --help  display help for command
  
## address
Usage: Atomicals CLI Utility address [options] <address>

Get balances and Atomicals stored at an address

Arguments:
  address     string

Options:
  --history   Verbose output to include history or not
  -h, --help  display help for command
  
## wallets
Usage: Atomicals CLI Utility wallets [options]

Get balances and atomicals stored at internal wallets

Options:
  --history            Shows history of txids for each wallet if enabled
  --all                Shows all loaded wallets and not just the primary and
                       funding
  --extra              Show extended wallet information such as specific utxos.
                       Default is to only show a summary.
  --balances           Show FT token balances
  --noqr               Hide QR codes
  --alias <string>     Restrict to only showing one of the imported wallets
                       identified by the alias
  --type <string>      Show NFT or FT types only. By default shows both. Not
                       compatible with --balances and --extra
  --identify <string>  Restrict to only showing one of the imported wallets
                       identified by the address (if it is found)
  --address <string>   Show the data and a QR code for an arbitrary address.
                       Not expected to be loaded into local wallets.
  -h, --help           display help for command
. 
## balances
Usage: Atomicals CLI Utility balances [options]

Get balances and atomicals stored at internal wallets

Options:
  --noqr              Hide QR codes
  --utxos             Show utxos too
  --all               Shows all loaded wallets and not just the primary and
                      funding
  --alias <string>    Restrict to only showing one of the imported wallets
                      identified by the alias
  --address <string>  Restrict to only showing by address. Using this option
                      with --alias has no effect.
  -h, --help          display help for command
  
## address-utxos
Usage: Atomicals CLI Utility address-utxos [options] <address>

List all utxos owned by an address

Arguments:
  address     string

Options:
  -h, --help  display help for command
  
## address-history
Usage: Atomicals CLI Utility address-history [options] <address>

List address history of an address

Arguments:
  address     string

Options:
  -h, --help  display help for command
  
## tx
Usage: Atomicals CLI Utility tx [options] <txid>

Get any transaction

Arguments:
  txid        string

Options:
  --verbose   Verbose output
  -h, --help  display help for command
  
## get-ticker
Usage: Atomicals CLI Utility get-ticker [options] <ticker>

Get Atomical by ticker name

Arguments:
  ticker      string

Options:
  --verbose   Verbose to show extended information.
  -h, --help  display help for command
  
## get-container
Usage: Atomicals CLI Utility get-container [options] <container>

Get Atomical by container name

Arguments:
  container   string

Options:
  --verbose   Verbose to show extended information.
  -h, --help  display help for command
  
## get-container-items
Usage: Atomicals CLI Utility get-container-items [options] <container> <limit> <offset>

Get the items in the container

Arguments:
  container   string
  limit       number
  offset      number

Options:
  --verbose   Verbose output
  -h, --help  display help for command
  
## get-container-item
Usage: Atomicals CLI Utility get-container-item [options] <container> <itemId>

Get an item in the container

Arguments:
  container   string
  itemId      string

Options:
  --verbose   Verbose output
  -h, --help  display help for command
  
## validate-container-item
Usage: Atomicals CLI Utility validate-container-item [options] <containerName> <itemName> <manifestFile>

Validate a container item from the manifest

Arguments:
  containerName         string
  itemName              string
  manifestFile          string

Options:
  --sealed --no-sealed  Validate the item without checking if the container is
                        sealed.
  -h, --help            display help for command
  
## resolve
Usage: Atomicals CLI Utility resolve [options] <realm_or_subrealm>

Resolve a realm or subrealm. Alias for 'get-realm'

Arguments:
  realm_or_subrealm  string

Options:
  --verbose          Verbose to show extended information.
  -h, --help         display help for command
  
## get-realm
Usage: Atomicals CLI Utility get-realm [options] <realm_or_subrealm>

Resolve a realm or subrealm. Alias for 'resolve'

Arguments:
  realm_or_subrealm  string

Options:
  --verbose          Verbose to show extended information.
  -h, --help         display help for command
  
## realm-info
Usage: Atomicals CLI Utility realm-info [options] <atomicalIdAlias>

Get realm and subrealm information of an atomical

Arguments:
  atomicalIdAlias  string

Options:
  --verbose        Verbose output
  -h, --help       display help for command
  
## summary-subrealms
Usage: Atomicals CLI Utility summary-subrealms [options]

Show summary of owned subrealms by wallet

Options:
  --owner <string>   Provide alternate wallet alias to query
  --filter <string>  Filter by status
  -h, --help         display help for command
  
## summary-containers
Usage: Atomicals CLI Utility summary-containers [options]

Show summary of owned containers by wallet

Options:
  --owner <string>   Provide alternate wallet alias to query
  --filter <string>  Filter by status
  -h, --help         display help for command
  
## summary-realms
Usage: Atomicals CLI Utility summary-realms [options]

Show summary of owned realms by wallet

Options:
  --owner <string>   Provide alternate wallet alias to query
  --filter <string>  Filter by status
  -h, --help         display help for command
  
## summary-tickers
Usage: Atomicals CLI Utility summary-tickers [options]

Show summary of owned tokens by tickers by wallet

Options:
  --owner <string>   Provide alternate wallet alias to query
  --filter <string>  Filter by status
  -h, --help         display help for command
  
## find-tickers
Usage: Atomicals CLI Utility find-tickers [options]

Search tickers

Options:
  --q <string>    Search query
  --asc <string>  Sort by ascending (default: "true")
  -h, --help      display help for command
  
## find-realms
Usage: Atomicals CLI Utility find-realms [options]

Search realms

Options:
  --q <string>    Search query
  --asc <string>  Sort by ascending (default: "true")
  -h, --help      display help for command
  
## find-containers
Usage: Atomicals CLI Utility find-containers [options]

Search containers

Options:
  --q <string>    Search query
  --asc <string>  Sort by ascending (default: "true")
  -h, --help      display help for command
  
## await-utxo
Usage: Atomicals CLI Utility await-utxo [options] <address> <amount>

Finds utxo by address

Arguments:
  address     string
  amount      number

Options:
  -h, --help  display help for command
  
## diff
Usage: Atomicals CLI Utility diff [options]

Options:
  -h, --help  display help for command
  
## set
Usage: Atomicals CLI Utility set [options] <atomicalIdAlias> <jsonFilename>

Set (update) an existing Atomical with data.

Arguments:
  atomicalIdAlias        string
  jsonFilename           string

Options:
  --rbf                  Whether to enable RBF for transactions.
  --funding <string>     Use wallet alias WIF key to be used for funding
  --owner <string>       Use wallet alias WIF key to move the Atomical
  --satsbyte <number>    Satoshis per byte in fees (default: "-1")
  --satsoutput <number>  Satoshis to put into output (default: "1000")
  --disableautoencode    Disables auto encoding of $b variables
  --bitworkc <string>    Whether to add any bitwork proof of work to the commit
                         tx
  -h, --help             display help for command
  
## set-container-data
Usage: Atomicals CLI Utility set-container-data [options] <containerName> <jsonFilename>

Update container data with json file contents

Arguments:
  containerName          string
  jsonFilename           string

Options:
  --rbf                  Whether to enable RBF for transactions.
  --funding <string>     Use wallet alias WIF key to be used for funding
  --owner <string>       Use wallet alias WIF key to move the Atomical
  --satsbyte <number>    Satoshis per byte in fees (default: "-1")
  --satsoutput <number>  Satoshis to put into output (default: "1000")
  --disableautoencode    Disables auto encoding of $b variables
  --bitworkc <string>    Whether to add any bitwork proof of work to the commit
                         tx
  -h, --help             display help for command
  
## prepare-dmint-items
Usage: Atomicals CLI Utility prepare-dmint-items [options] <folder> <outputFolderName>

Prepare the dmint config and item manifest from a folder of images

Arguments:
  folder            string
  outputFolderName  string

Options:
  -h, --help        display help for command
  
## prepare-dmint
Usage: Atomicals CLI Utility prepare-dmint [options] <folder> <mintHeight> <bitworkc>

Prepare the dmint config and item manifest from a folder of images

Arguments:
  folder      string
  mintHeight  number
  bitworkc    string

Options:
  -h, --help  display help for command
  
## enable-dmint
Usage: Atomicals CLI Utility enable-dmint [options] <container> <jsonFilename>

Enable dmint for a container with the dmint config file produced from the
prepare-dmint command

Arguments:
  container              string
  jsonFilename           string

Options:
  --rbf                  Whether to enable RBF for transactions.
  --funding <string>     Use wallet alias WIF key to be used for funding
  --owner <string>       Use wallet alias WIF key to move the Atomical
  --satsbyte <number>    Satoshis per byte in fees (default: "-1")
  --satsoutput <number>  Satoshis to put into output (default: "1000")
  --bitworkc <string>    Whether to add any bitwork proof of work to the commit
                         tx
  -h, --help             display help for command
  
## mint-item
Usage: Atomicals CLI Utility mint-item [options] <containerName> <itemName> <manifestFile>

Mint item non-fungible token (NFT) Atomical from a decentralized container

Arguments:
  containerName            string
  itemName                 string
  manifestFile             string

Options:
  --rbf                    Whether to enable RBF for transactions.
  --owner <string>         Owner of the parent Atomical. Used for direct
                           subrealm minting.
  --initialowner <string>  Initial owner wallet alias to mint the Atomical into
  --satsbyte <number>      Satoshis per byte in fees (default: "-1")
  --satsoutput <number>    Satoshis to put into the minted atomical (default:
                           "1000")
  --funding <string>       Use wallet alias WIF key to be used for funding and
                           change
  --container <string>     Name of the container to request
  --bitworkc <string>      Whether to put any bitwork proof of work into the
                           token mint. Applies to the commit transaction.
  --bitworkr <string>      Whether to put any bitwork proof of work into the
                           token mint. Applies to the reveal transaction.
  --disablechalk           Whether to disable the real-time chalked logging of
                           each hash for mining. Improvements mining
                           performance to set this flag
  -h, --help               display help for command
  
## emit
Usage: Atomicals CLI Utility emit [options] <atomicalIdAlias> <data...>

Emit an event for an existing Atomical with data.

Arguments:
  atomicalIdAlias        string
  data                   string

Options:
  --rbf                  Whether to enable RBF for transactions.
  --funding <string>     Use wallet alias WIF key to be used for funding
  --owner <string>       Use wallet alias WIF key to move the Atomical
  --satsbyte <number>    Satoshis per byte in fees (default: "-1")
  --satsoutput <number>  Satoshis to put into output (default: "1000")
  -h, --help             display help for command
  
## set-relation
Usage: Atomicals CLI Utility set-relation [options] <atomicalId> <relationName> <relationValues...>

Set relationship an existing Atomical with data.

Arguments:
  atomicalId             string
  relationName           string
  relationValues         string

Options:
  --rbf                  Whether to enable RBF for transactions.
  --funding <string>     Use wallet alias WIF key to be used for funding
  --owner <string>       Use wallet alias WIF key to move the Atomical
  --satsbyte <number>    Satoshis per byte in fees (default: "15")
  --satsoutput <number>  Satoshis to put into output (default: "1000")
  -h, --help             display help for command
  
## delete
Usage: Atomicals CLI Utility delete [options] <atomicalIdAlias> <filesWithDeleteKeys>

Delete keys for existing Atomical.

Arguments:
  atomicalIdAlias        string
  filesWithDeleteKeys    string

Options:
  --rbf                  Whether to enable RBF for transactions.
  --funding <string>     Use wallet alias WIF key to be used for funding
  --owner <string>       Use wallet alias WIF key to move the Atomical
  --satsbyte <number>    Satoshis per byte in fees (default: "-1")
  --satsoutput <number>  Satoshis to put into output (default: "1000")
  --bitworkc <string>    Whether to add any bitwork proof of work to the commit
                         tx
  --bitworkr <string>    Whether to add any bitwork proof of work to the reveal
                         tx.
  --disablechalk         Whether to disable the real-time chalked logging of
                         each hash for mining. Improvements mining performance
                         to set this flag
  -h, --help             display help for command
  
## seal
Usage: Atomicals CLI Utility seal [options] <atomicalIdAlias>

Seal any NFT Atomical type permanently so that it can never be updated or
transferred ever again.

Arguments:
  atomicalIdAlias      string

Options:
  --rbf                Whether to enable RBF for transactions.
  --funding <string>   Use wallet alias WIF key to be used for funding
  --owner <string>     Use wallet alias WIF key to move the Atomical
  --satsbyte <number>  Satoshis per byte in fees (default: "-1")
  --bitworkc <string>  Whether to add any bitwork proof of work to the commit
                       tx
  -h, --help           display help for command
  
## splat
Usage: Atomicals CLI Utility splat [options] <locationId>

Extract an NFT Atomical from a UTXO which contains multiple Atomicals

Arguments:
  locationId             string

Options:
  --rbf                  Whether to enable RBF for transactions.
  --funding <string>     Use wallet alias WIF key to be used for funding
  --owner <string>       Use wallet alias WIF key to move the Atomical
  --satsbyte <number>    Satoshis per byte in fees (default: "-1")
  --satsoutput <number>  Satoshis to put into each output (default: "1000")
  --bitworkc <string>    Whether to add any bitwork proof of work to the commit
                         tx
  -h, --help             display help for command
  
## split
Usage: Atomicals CLI Utility split [options] <locationId>

Split operation to separate the FT Atomicals at a single UTXOs.

Arguments:
  locationId           string

Options:
  --rbf                Whether to enable RBF for transactions.
  --funding <string>   Use wallet alias wif key to be used for funding
  --owner <string>     Use wallet alias WIF key to move the Atomical
  --satsbyte <number>  Satoshis per byte in fees (default: "15")
  -h, --help           display help for command
  
## custom-color
Usage: Atomicals CLI Utility custom-color [options] <locationId>

custom color operation to separate the FT Atomicals at a single UTXOs.

Arguments:
  locationId           string

Options:
  --rbf                Whether to enable RBF for transactions.
  --funding <string>   Use wallet alias wif key to be used for funding
  --owner <string>     Use wallet alias WIF key to move the Atomical
  --satsbyte <number>  Satoshis per byte in fees (default: "15")
  -h, --help           display help for command
  
## get
Usage: Atomicals CLI Utility get [options] <atomicalAliasOrId>

Get the status of an Atomical

Arguments:
  atomicalAliasOrId  string

Options:
  --verbose          Verbose output
  -h, --help         display help for command
  
## global
Usage: Atomicals CLI Utility global [options]

Get global status

Options:
  --hashes <number>  How many atomicals block hashes to retrieve (default:
                     "10")
  -h, --help         display help for command
  
## dump
Usage: Atomicals CLI Utility dump [options]

dump

Options:
  -h, --help  display help for command
  
## location
Usage: Atomicals CLI Utility location [options] <atomicalAliasOrId>

Get locations of an Atomical

Arguments:
  atomicalAliasOrId  string

Options:
  --verbose          Verbose output
  -h, --help         display help for command
  
## ftinfo
Usage: Atomicals CLI Utility ftinfo [options] <atomicalAliasOrId>

Get FT specific info for an FT atomical

Arguments:
  atomicalAliasOrId  string

Options:
  -h, --help         display help for command
  
## state
Usage: Atomicals CLI Utility state [options] <atomicalAliasOrId>

Get the state of an Atomical

Arguments:
  atomicalAliasOrId  string

Options:
  --verbose          Verbose output
  -h, --help         display help for command
  
## state-history
Usage: Atomicals CLI Utility state-history [options] <atomicalAliasOrId>

Get the state history of an Atomical

Arguments:
  atomicalAliasOrId  string

Options:
  --verbose          Verbose output
  -h, --help         display help for command
  
## events
Usage: Atomicals CLI Utility events [options] <atomicalAliasOrId>

Get the event state history of an Atomical

Arguments:
  atomicalAliasOrId  string

Options:
  --verbose          Verbose output
  -h, --help         display help for command
  
## enable-subrealms
Usage: Atomicals CLI Utility enable-subrealms [options] <realmOrSubRealm> <file>

Set and enable subrealm minting rules for a realm or subrealm

Arguments:
  realmOrSubRealm        string
  file

Options:
  --rbf                  Whether to enable RBF for transactions.
  --funding <string>     Use wallet alias WIF key to be used for funding
  --owner <string>       Use wallet alias WIF key to move the Atomical
  --satsbyte <number>    Satoshis per byte in fees (default: "-1")
  --satsoutput <number>  Satoshis to put into output (default: "1000")
  --bitworkc <string>    Whether to add any bitwork proof of work to the commit
                         tx
  --bitworkr <string>    Whether to add any bitwork proof of work to the reveal
                         tx.
  --disablechalk         Whether to disable the real-time chalked logging of
                         each hash for mining. Improvements mining performance
                         to set this flag
  -h, --help             display help for command
  
## disable-subrealms
Usage: Atomicals CLI Utility disable-subrealms [options] <realmOrSubRealm>

Delete the subrealm minting rules for a realm or subrealm

Arguments:
  realmOrSubRealm        string

Options:
  --rbf                  Whether to enable RBF for transactions.
  --funding <string>     Use wallet alias WIF key to be used for funding
  --owner <string>       Use wallet alias WIF key to move the Atomical
  --satsbyte <number>    Satoshis per byte in fees (default: "-1")
  --satsoutput <number>  Satoshis to put into output (default: "1000")
  --bitworkc <string>    Whether to add any bitwork proof of work to the commit
                         tx
  --bitworkr <string>    Whether to add any bitwork proof of work to the reveal
                         tx.
  --disablechalk         Whether to disable the real-time chalked logging of
                         each hash for mining. Improvements mining performance
                         to set this flag
  -h, --help             display help for command
  
## pending-subrealms
Usage: Atomicals CLI Utility pending-subrealms [options]

Display pending subrealm Atomical requests and make payments

Options:
  --rbf                Whether to enable RBF for transactions.
  --owner <string>     Show pending subrealms for an address or wallet
  --display            Show pending subrealms for an address or wallet
  --verbose            Show verbose raw output
  --funding <string>   Use wallet alias WIF key to be used for funding and
                       change
  --satsbyte <number>  Satoshis per byte in fees (default: "-1")
  -h, --help           display help for command
  
## mint-ft
Usage: Atomicals CLI Utility mint-ft [options] <ticker> <supply> <file>

Mint fungible token (FT) Atomical in direct issuance mode

Arguments:
  ticker                   string
  supply                   number
  file                     string

Options:
  --rbf                    Whether to enable RBF for transactions.
  --initialowner <string>  Initial owner wallet alias to mint the Atomical into
  --satsbyte <number>      Satoshis per byte in fees (default: "-1")
  --funding <string>       Use wallet alias WIF key to be used for funding and
                           change
  --bitworkc <string>      Whether to put any bitwork proof of work into the
                           token mint. Applies to the commit transaction.
  --bitworkr <string>      Whether to put any bitwork proof of work into the
                           token mint. Applies to the reveal transaction.
  --parent <string>        Whether to require a parent atomical to be spent
                           along with the mint.
  --parentowner <string>   Wallet owner of the parent to spend along with the
                           mint.
  --disablechalk           Whether to disable the real-time chalked logging of
                           each hash for mining. Improvements mining
                           performance to set this flag
  -h, --help               display help for command
. 
## init-dft-perpetual
Usage: Atomicals CLI Utility init-dft-perpetual [options] <ticker>

Initialize perpetual bitwork mineable fungible token (FT) atomical in
decentralized issuance mode

Arguments:
  ticker                           string

Options:
  --mintbitworkvec <string>        The base bitwork prefix vector to use
  --mintbitworkcinc <number>       The amount of bitworkc to increase for each
                                   phase of max_mints (default: "1")
  --mintbitworkrinc <number>       The amount of bitworkr to increase for each
                                   phase of max_mints
  --mintbitworkcincstart <number>  The starting amount of bitworkc to increase
                                   for each phase of max_mints
  --mintbitworkrincstart <number>  The starting amount of bitworkr to increase
                                   for each phase of max_mints
  --max_mints <number>             The number of mints allowed per mint phase
                                   of max_mints (default: "2000")
  --mint_height <number>           The starting mint height (default: "0")
  --maxglobalmints <number>        The global max mints
  --metadata <string>              File to include for metadata
  --mint_amount <number>           The number of tokens per mint (default:
                                   "10000")
  --funding <string>               Use wallet alias wif key to be used for
                                   funding and change
  --noimage <boolean>              Whether to allow no image when using
                                   --metadata file
  --satsbyte <number>              Satoshis per byte in fees (default: "-1")
  --bitworkc <string>              Whether to put any bitwork proof of work
                                   into the token mint. Applies to the commit
                                   transaction.
  --bitworkr <string>              Whether to put any bitwork proof of work
                                   into the token mint. Applies to the reveal
                                   transaction.
  -h, --help                       display help for command
. 
## init-dft-fixed
Usage: Atomicals CLI Utility init-dft-fixed [options] <ticker> <mintbitworkc>

Initialize fixed bitwork mineable fungible token (FT) atomical in decentralized
issuance mode

Arguments:
  ticker                   string
  mintbitworkc             string

Options:
  --mintbitworkr <number>  The amount of bitworkr to add for each mint
  --max_mints <number>     The max number of mints allowed (default: "100000")
  --mint_height <number>   The starting mint height (default: "0")
  --metadata <string>      File to include for metadata
  --mint_amount <number>   The number of tokens per mint (default: "10000")
  --funding <string>       Use wallet alias wif key to be used for funding and
                           change
  --noimage <boolean>      Whether to allow no image when using --metadata file
  --satsbyte <number>      Satoshis per byte in fees (default: "200")
  --bitworkc <string>      Whether to put any bitwork proof of work into the
                           token mint. Applies to the commit transaction.
  --bitworkr <string>      Whether to put any bitwork proof of work into the
                           token mint. Applies to the reveal transaction.
  -h, --help               display help for command
. 
## mint-dft
Usage: Atomicals CLI Utility mint-dft [options] <ticker>

Mint coins for a decentralized fungible token (FT)

Arguments:
  ticker                   string

Options:
  --rbf                    Whether to enable RBF for transactions.
  --initialowner <string>  Assign claimed tokens into this address
  --funding <string>       Use wallet alias wif key to be used for funding and
                           change
  --current                Mine the current bitwork. If disabled mines the
                           next.
  --satsbyte <number>      Satoshis per byte in fees (default: "-1")
  --disablechalk           Whether to disable the real-time chalked logging of
                           each hash for Bitwork mining. Improvements mining
                           performance to set this flag
  -h, --help               display help for command
. 
## mint-nft
Usage: Atomicals CLI Utility mint-nft [options] <file>

Mint non-fungible token (NFT) Atomical

Arguments:
  file                     string

Options:
  --rbf                    Whether to enable RBF for transactions.
  --initialowner <string>  Initial owner wallet alias to mint the Atomical into
  --satsbyte <number>      Satoshis per byte in fees (default: "-1")
  --satsoutput <number>    Satoshis to put into the minted atomical (default:
                           "1000")
  --funding <string>       Use wallet alias WIF key to be used for funding and
                           change
  --container <string>     Name of the container to request
  --bitworkc <string>      Whether to put any bitwork proof of work into the
                           token mint. Applies to the commit transaction.
  --bitworkr <string>      Whether to put any bitwork proof of work into the
                           token mint. Applies to the reveal transaction.
  --parent <string>        Whether to require a parent atomical to be spent
                           along with the mint.
  --parentowner <string>   Wallet owner of the parent to spend along with the
                           mint.
  --disablechalk           Whether to disable the real-time chalked logging of
                           each hash for mining. Improvements mining
                           performance to set this flag
  -h, --help               display help for command
. 
## mint-nft-json
Usage: Atomicals CLI Utility mint-nft-json [options] <jsonFile>

Mint non-fungible token (NFT) Atomical with JSON only data

Arguments:
  jsonFile                 string

Options:
  --rbf                    Whether to enable RBF for transactions.
  --initialowner <string>  Initial owner wallet alias to mint the Atomical into
  --satsbyte <number>      Satoshis per byte in fees (default: "-1")
  --satsoutput <number>    Satoshis to put into the minted atomical (default:
                           "1000")
  --funding <string>       Use wallet alias WIF key to be used for funding and
                           change
  --container <string>     Name of the container to request
  --bitworkc <string>      Whether to put any bitwork proof of work into the
                           token mint. Applies to the commit transaction.
  --bitworkr <string>      Whether to put any bitwork proof of work into the
                           token mint. Applies to the reveal transaction.
  --parent <string>        Whether to require a parent atomical to be spent
                           along with the mint.
  --parentowner <string>   Wallet owner of the parent to spend along with the
                           mint.
  --disablechalk           Whether to disable the real-time chalked logging of
                           each hash for mining. Improvements mining
                           performance to set this flag
  -h, --help               display help for command
. 
## mint-realm
Usage: Atomicals CLI Utility mint-realm [options] <realm>

Mint top level Realm non-fungible token (NFT) Atomical

Arguments:
  realm                    string

Options:
  --rbf                    Whether to enable RBF for transactions.
  --initialowner <string>  Initial owner wallet alias to mint the Atomical into
  --satsbyte <number>      Satoshis per byte in fees (default: "-1")
  --satsoutput <number>    Satoshis to put into the minted atomical (default:
                           "1000")
  --funding <string>       Use wallet alias WIF key to be used for funding and
                           change
  --container <string>     Name of the container to request
  --bitworkc <string>      Whether to put any bitwork proof of work into the
                           token mint. Applies to the commit transaction.
  --bitworkr <string>      Whether to put any bitwork proof of work into the
                           token mint. Applies to the reveal transaction.
  --parent <string>        Whether to require a parent atomical to be spent
                           along with the mint.
  --parentowner <string>   Wallet owner of the parent to spend along with the
                           mint.
  --disablechalk           Whether to disable the real-time chalked logging of
                           each hash for mining. Improvements mining
                           performance to set this flag
  -h, --help               display help for command
. 
## mint-subrealm
Usage: Atomicals CLI Utility mint-subrealm [options] <realm>

Mint subrealm non-fungible token (NFT) Atomical

Arguments:
  realm                    string

Options:
  --rbf                    Whether to enable RBF for transactions.
  --owner <string>         Owner of the parent Atomical. Used for direct
                           subrealm minting.
  --initialowner <string>  Initial owner wallet alias to mint the Atomical into
  --satsbyte <number>      Satoshis per byte in fees (default: "200")
  --satsoutput <number>    Satoshis to put into the minted atomical (default:
                           "1000")
  --funding <string>       Use wallet alias WIF key to be used for funding and
                           change
  --container <string>     Name of the container to request
  --bitworkc <string>      Whether to put any bitwork proof of work into the
                           token mint. Applies to the commit transaction.
  --bitworkr <string>      Whether to put any bitwork proof of work into the
                           token mint. Applies to the reveal transaction.
  --disablechalk           Whether to disable the real-time chalked logging of
                           each hash for mining. Improvements mining
                           performance to set this flag
  -h, --help               display help for command
. 
## mint-container
Usage: Atomicals CLI Utility mint-container [options] <container>

Mint container non-fungible token (NFT) Atomical

Arguments:
  container                string

Options:
  --rbf                    Whether to enable RBF for transactions.
  --initialowner <string>  Initial owner wallet alias to mint the Atomical into
  --satsbyte <number>      Satoshis per byte in fees (default: "-1")
  --satsoutput <number>    Satoshis to put into the minted atomical (default:
                           "1000")
  --funding <string>       Use wallet alias WIF key to be used for funding and
                           change
  --container <string>     Name of the container to request to be a member of.
                           Not to be confused with the 'mint-container' command
                           to create a new container
  --bitworkc <string>      Whether to put any bitwork proof of work into the
                           token mint. Applies to the commit transaction.
  --bitworkr <string>      Whether to put any bitwork proof of work into the
                           token mint. Applies to the reveal transaction.
  --parent <string>        Whether to require a parent atomical to be spent
                           along with the mint.
  --parentowner <string>   Wallet owner of the parent to spend along with the
                           mint.
  --disablechalk           Whether to disable the real-time chalked logging of
                           each hash for mining. Improvements mining
                           performance to set this flag
  -h, --help               display help for command
. 
## transfer-nft
Usage: Atomicals CLI Utility transfer-nft [options] <atomicalId> <address>

Transfer Atomical NFT to new address

Arguments:
  atomicalId             string
  address                string

Options:
  --rbf                  Whether to enable RBF for transactions.
  --owner <string>       Use wallet alias WIF key to move the Atomical
  --funding <string>     Use wallet alias WIF key to be used for funding and
                         change
  --satsbyte <number>    Satoshis per byte in fees (default: "15")
  --satsoutput <number>  Satoshis to put into the transferred atomical
                         (default: "546")
  -h, --help             display help for command
. 
## transfer-ft
Usage: Atomicals CLI Utility transfer-ft [options] <atomicalId>

Transfer Atomical FT to other addresses

Arguments:
  atomicalId                  string

Options:
  --rbf                       Whether to enable RBF for transactions.
  --owner <string>            Use wallet alias WIF key to move the Atomical
  --funding <string>          Use wallet alias WIF key to be used for funding
                              and change
  --satsbyte <number>         Satoshis per byte in fees (default: "15")
  --nofunding                 Do not ask for separate funding, use existing
                              utxo
  --atomicalreceipt <string>  Attach an atomical id to a pay receipt
  -h, --help                  display help for command
  
## transfer-builder
Usage: Atomicals CLI Utility transfer-builder [options]

Transfer plain regular UTXOs to another addresses

Options:
  --rbf                           Whether to enable RBF for transactions.
  --owner <string>                Use wallet alias WIF key to move the Atomical
  --funding <string>              Use wallet alias WIF key to be used for
                                  funding and change
  --satsbyte <number>             Satoshis per byte in fees (default: "15")
  --nofunding                     Do not ask for seperate funding, use existing
                                  utxo
  --skipvalidation                Do not do FT transfer validation on broadcast
                                  (danger)
  --atomicalreceipt <string>      Attach an atomical id to a pay receipt
  --atomicalreceipttype <string>  Attach receipt type p or d
  -h, --help                      display help for command
  
## transfer-utxos
Usage: Atomicals CLI Utility transfer-utxos [options]

Transfer plain regular UTXOs to another addresses

Options:
  --rbf                       Whether to enable RBF for transactions.
  --owner <string>            Use wallet alias WIF key to move the Atomical
  --funding <string>          Use wallet alias WIF key to be used for funding
                              and change
  --satsbyte <number>         Satoshis per byte in fees (default: "15")
  --nofunding                 Do not ask for separate funding, use existing
                              utxo
  --atomicalreceipt <string>  Attach an atomical id to a pay receipt
  -h, --help                  display help for command
  
## merge-atomicals
Usage: Atomicals CLI Utility merge-atomicals [options]

Merge Atomicals UTXOs together for test purposes

Options:
  --rbf                Whether to enable RBF for transactions.
  --owner <string>     Use wallet alias WIF key to move the Atomicals
  --funding <string>   Use wallet alias WIF key to be used for funding and
                       change
  --satsbyte <number>  Satoshis per byte in fees (default: "15")
  -h, --help           display help for command
  
## tx-history
Usage: Atomicals CLI Utility tx-history [options] <atomicalAliasOrId>

Get the history of an Atomical

Arguments:
  atomicalAliasOrId  string

Options:
  --verbose          Verbose output
  -h, --help         display help for command
  
## list
Usage: Atomicals CLI Utility list [options]

List feed of Atomicals minted globally

Options:
  --limit <number>   Limit the number of results (default: "20")
  --offset <number>  Offset for pagination (default: "-20")
  --asc <string>     Whether to sort by ascending or descending (default:
                     "true")
  -h, --help         display help for command
  
## address-atomicals
Usage: Atomicals CLI Utility address-atomicals [options] <address>

List all atomicals owned by an address

Arguments:
  address     string

Options:
  -h, --help  display help for command
  
## at-location
Usage: Atomicals CLI Utility at-location [options] <location>

Get Atomicals at a utxo location

Arguments:
  location    string

Options:
  -h, --help  display help for command
  
## store-file
Usage: Atomicals CLI Utility store-file [options] <filepath> <givenFileName>

Store general immutable data transaction that is not an NFT or FT

Arguments:
  filepath                string
  givenFileName           string

Options:
  --rbf                   Whether to enable RBF for transactions.
  --funding <string>      Use wallet alias WIF key to be used for funding and
                          change
  --satsbyte <number>     Satoshis per byte in fees (default: "-1")
  --satsoutput <number>   Satoshis to put into output (default: "1000")
  --bitworkc <string>     Whether to put any bitwork proof of work into the
                          token mint. Applies to the commit transaction.
  --bitworkr <string>     Whether to put any bitwork proof of work into the
                          token mint. Applies to the reveal transaction.
  --parent <string>       Whether to require a parent atomical to be spent
                          along with the mint.
  --parentowner <string>  Wallet owner of the parent to spend along with the
                          mint.
  --disablechalk          Whether to disable the real-time chalked logging of
                          each hash for mining. Improvements mining performance
                          to set this flag
  -h, --help              display help for command
  
## download
Usage: Atomicals CLI Utility download [options] <locationIdOrTxId>

Download a file from a locationId or atomicalId

Arguments:
  locationIdOrTxId  string

Options:
  --body            Whether to include the body bytes in the print out or
                    suppress it
  -h, --help        display help for command
  
## broadcast
Usage: Atomicals CLI Utility broadcast [options]

broadcast a rawtx

Options:
  --rawtx <string>      Rawtx
  --rawtxfile <string>  File path to the rawtx
  -h, --help            display help for command
  
## decodetx
Usage: Atomicals CLI Utility decodetx [options]

Decode a tx

Options:
  --rawtx <string>      Rawtx
  --rawtxfile <string>  File path to the rawtx
  -h, --help            display help for command
