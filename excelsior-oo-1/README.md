## WalletShell - GUI wallet for Woolong.

### Precompiled binaries
You can download the precompiled binaries [here](https://github.com/Woolong-coin/woolong-wallet-electron/releases/latest).

### Features:

This wallet contains the basic functions required to manage your Woolong assets:

* Wallet creation:
  * Create new wallet.
  * Import/recover from private keys OR mnemonic seed.
* Basic wallet operation/transactions:
  * Open an existing  wallet
  * Display wallet address & balance
  * Display & Backup private keys/seed
  * Sending/transferring. Integrated Address or Payment ID are supported. Also provides address lookup from your addressbook.
  * Transactions history listing/sorting/searching/detail.
  * Incoming transaction notification.
  * Export incoming, outgoing, or all transactions to csv file.
  * Rescan wallet from specific block height.
  * Perform wallet optimization.
  * Utilities: generate payment id and integrated address.
* Address book:
  * Add/Edit/Delete address entry.
  * Listing/sorting/searching existing entries.
  * Allow to store same wallet address with different payment id.
  * Autosave address after sending to new/unknown recipient
  * Allow to optionally create password protected address book.
* Misc:
  * Option to use system tray (on closing/minimizing wallet)
  * Provides list of public nodes, fetch/updated daily from [woolong-nodes-json](https://github.com/Woolong-coin/woolong-wallet-electron) repo.
  * Allow to add custom node address.
  * Theme: Dark & Light Mode
  * [Keyboard shortcuts](docs/shortcut.md)
  
### Building/Packaging WalletShell from source
You need to have `Node.js` and `npm` installed, go to https://nodejs.org and find out how to get it installed on your platform.

Once you have Node+npm installed:
```
# assuming you're building it on GNU/Linux
# first, download turtle-service binary for each platform
# from Woolong official repo
# https://github.com/Woolong-coin/woolong-coin/releases
# extract the turtle-service executable somewhere

# clone the repo
$ git clone https://github.com/Woolong-coin/woolong-wallet-electron
$ cd woolong-wallet-electron

# install dependencies
$ npm install

# create build+dist directory
$ mkdir -p ./build && mkdir -p ./dist

# copy/symlink icons from assets, required for packaging
$ cp ./src/assets/icon.* ./build/

# build GNU/Linux package
$ mkdir -p ./bin/lin
$ cp /path/to/linux-version-of/woolong-service ./bin/lin/
$ npm run dist-lin

# build Windows package (you need to have wine 2.0+ installed)
$ mkdir -p ./bin/win
$ cp /path/to/win-version-of/woolong-service.exe ./bin/win/
$ npm run dist-win

# build OSX package
$ mkdir -p ./bin/osx
$ cp /path/to/linux-version-of/woolong-service ./bin/osx/
$ npm run dist-mac
```

Resulting packages or installer can be found inside `dist/` directory.

