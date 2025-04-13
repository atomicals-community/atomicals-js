# Util commands

As `atomicals-js` produces a cli with `yarn cli` it's useful to have a list of useful commands.

**JSON Output from most of commands**: If you want to run a *`full-command`* and get the output in JSON format.
`full-command | awk '/^\{|^\[/{f=1} f; /^\}|^\]/{f=0; exit}'`
- With `jq` installed: 
`full-command | awk '/^\{|^\[/{f=1} f; /^\}|^\]/{f=0; exit}' | jq '.'`

**List all available commands**: 
`yarn cli --help | grep -A 1000 '^Commands:' | sed '1d' | awk '/^[[:space:]]+[a-zA-Z-]+/{print }'`

**Run all the commands from command_list.txt**(Change the name if you saved yourself with another name): 
`cat command_list.txt | xargs -I CMD yarn cli CMD --help`



