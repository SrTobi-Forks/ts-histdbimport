Imports a `.zsh_history` file into a [zsh-histdb](https://github.com/larkery/zsh-histdb) sqlite database.

Like [go-histdbimport](https://github.com/drewis/go-histdbimport), but 6000x faster.

### Usage

Make sure you have node installed, then run

```sh
npx histdbimport
```

Alternatively, get the source from this repo and run it from here:

```sh
git clone https://github.com/phiresky/ts-histdbimport
cd ts-histdbimport
npm install
npm run insert-all
```

Will import `~/.zsh_history` into `~/.histdb/zsh-history.db`.

You can set env vars to change the input / output filename:

`$ history_file=zh database=x.db npm run insert-all`

### Benchmark

Importing a history file with 299k entries:

-   go-histdbimport: 9.08 inserts/s (would take 9 hours)
-   ts-histdbimport: 56500 inserts/s (5.29s total)

With ([#3](https://github.com/phiresky/ts-histdbimport/pulls/3)) it should be even faster, though it now uses more memory. Thanks [@Adk9p](https://github.com/Adk9p)!
