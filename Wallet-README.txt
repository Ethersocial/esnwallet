ESN Wallet

The ESN wallet, which allows you to create simple and multisig wallets to manage your esn.

The wallet contains its own node, but can also use an already running one, if the IPC path of that node is the standard path.
(See below)

## Running on a testnet

When you start the wallet on a testnet (e.g. different `--datadir`) you need to make sure to set the `--ipcpath` back to the original one.

On OSX its `~/Library/Ethersocial/geth.ipc` on linux `~/.esn/geth.ipc` and on windows it uses a named pipe, which doesn't need to be renamed.

Example:

    $ geth --datadir /my/chain/ --networkid 23 --ipcpath ~/Library/Ethersocial/geth.ipc



### Original contract

Once you start the app while running a testnet, the wallet need to deploy an original contract,
which will be used by the wallet contracts you create.

The point of the original wallet is that wallet contract creation is cheaper,
as not the full code has to be deployed for every wallet.

You need to make sure that the account displayed for the original wallet creation is unlocked and has at least 1 esn.


## Paths

The paths which store your wallets database and node are different:

The wallet stores its data at:
- Mac: ~/Library/Application Support/Ethersocial
- Windows: %APPDATA%\Roaming\Ethersocial
- Linux: ~/.config/Ethersocial

The nodes data is stored at:
- Mac: ~/Library/ESN
- Windows: %APPDATA%\Roaming\ESN
- Linux: ~/.esn


## Issues

If you find issues or have suggestion, please report them at  
https://github.com/ethersocial/meteor-dapp-wallet/issues



## Repository

The wallet code can be found at   
https://github.com/ethersocial/meteor-dapp-wallet

And the binary application code, which wraps the wallet app can be found at   
https://github.com/ethersocial/esnwallet/tree/wallet



## Bundling the wallet

To bundle the binaries yourself follow the instructions on the mist#wallet readme  
https://github.com/ethersocial/esnwallet/tree/wallet#deployment
