
# DESTINATECH HEARTBEAT

## DESCRIPTION

*Destinatech Heartbeat* ("Heartbeat") is a piece of software which, in essence,
provides two core programs. The first, a server (daemon) which services clients
and the second, a client which interfaces with the aforementioned heartbeat
server.

## LICENSE

GNU GPL (**version 2 only**)

## INSTALLATION

### Installing the server

```bash
(
  instance_dir=/usr/local/destinatech/heartbeat-server
  mkdir -p "$(dirname "$instance_dir")" &&
  git clone https://github.com/destinatech/heartbeat "$instance_dir" &&
  cd "$instance_dir" &&
  install -d -m 0700 etc/secrets &&
  heartbeat init --server
)
```

The `init --server` command to `heartbeat(1)` will ask a minimal number of
questions requiring input from the user. Most can be skipped and sane defaults
will be used, but the password required to administer the server instance
(including: adding, updating and removing *Heartbeat* client certificates) must
be defined for initialisation to succeed.

### Instaling the client

```bash
(
  instance_dir=/usr/local/destinatech/heartbeat-server
  mkdir -p "$(dirname "$instance_dir")" &&
  git clone https://github.com/destinatech/heartbeat "$instance_dir" &&
  cd "$instance_dir" &&
  install -d -m 0700 etc/secrets &&
  heartbeat init --client
)
```

The `init --cient` command to `heartbeat(1)` also asks a minimal number of
questions requiring user-input. Most can be skipped and sane defaults will be
used, but at least one *Heartbeat* server endpoint must be defined for
initialisation to succeed.

## METADATA

**Last-Update**: 2024/06/11
**Project-Status**: Prototyped

<!--
vim: ts=2 sw=2 et fdm=marker :
-->
