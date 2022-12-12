# sshx

`ssh` into servers by typing part of the server names, based on configuration.

The full server names are read from either the `SSHX_SERVERS` environment variable or the `-s` switch.
Patterns are matched against those server names, to choose one or more servers to connect to. Or connect to them all using the -a switch.

## Profile example

Example setup in your profile script:

```bash
# Read a list of servers from ~/.servers
export SSHX_SERVERS=$(cat $HOME/.servers | grep -v '^#')
```

or

```bash
# Define a shell alias, connect to all with `myssh -a`
# or one with `myssh host2`
alias myssh='sshx -d example.com -s "host1 host2 host3"'
```

## Users

Set a default user to connect with using the `SSHX_USER` environment variable, which defaults to `root`.

You can also include a username in the server definition, e.g. `user@host`.
