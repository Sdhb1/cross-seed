# Writing code

1. Download VS Code. it has typescript support out of the box, but any ide will
   do. recommend downloading a typescript plugin if needed
2. clone repo
3. open repo in vs code
4. run npm install
5. start coding :)

the code is in /src cmd.js is the entrypoint pipeline.js is the interesting high
level functions (doRss, etc...)

# Build and Run

`npm run build` will compile the typescript files into javascript files in /dist
`npm run watch` will compile, then incrementally compile when files change the
`cross-seed` command is an alias for `node dist/cmd.js`, as in
`node dist/cmd.js daemon` but it's annoying to use the cross-seed alias while
developing so i use a lot of ctrl-R with fzf

# Testing

I keep a `config.js` that points to
`{ torrentDir: "./input", outputDir: "./output" }` and put some torrent files in
`./input` I usually run in search mode because it's the simplest form of
cross-seed and most work applies to it.

## testing daemon mode

have three terminals open, one for npm run watch, one for keeping the cross-seed
daemon open, and one for curling to localhost:2468

## testing direct injection

mostly i stick with `--save` (the default i think) usually i use docker to run
whichever client. you could install it yourself though I have a gitignored
docker_compose.yml that keeps track of all of the clients but i only run them
one at a time