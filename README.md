# blockchair-dash-mirror

An ad-hoc mirror of blockchair's dash data for faster retrieval.

Source data: <https://gz.blockchair.com/dash/blocks/>

# Prerequisites

This project does use a hard-coded directory. Sorry.

```sh
mkdir -p ~/Projects/Dash/
git clone https://github.com/dashhive/blockchair-dash-mirror.git ./dashblockchair
```

# Setup

1. Download new data (5m-10m per year)
2. Edit the quartering file to include the latest
3. Enjoy the quarter files, and the latest tab file

```sh
pushd ~/Projects/Dash/dashblockchair/
./bin/blockchair_dash_quarter

./bin/blockchair_dash_download
./bin/blockchair_dash_quarter
```

```txt
blockchair_dash_latest.txt          # list of all files
./gz/                               # all the gz files
./tsv/                              # all the tsv (gz files unzipped)
blockchair_dash_blocks_20xx_qX.tsv  # bundled quarters
blockchair_dash_blocks_latest.tsv   # most recent daily file
```

# Verifying

To start from scratch and re-download everything:

```sh
rm -rf ./gz/
./bin/blockchair_dash_download

git status
```

If any files show up as modified, something went wrong.
