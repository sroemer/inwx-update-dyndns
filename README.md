# inwx-update-dyndns

This is a slightly modified version of [nroi/inwx_update_dyndns](https://github.com/nroi/inwx_update_dyndns).

A python script which checks at regular intervals if your IPs (IPv4 and IPv6) have changed. If changes are
detected, an HTTP POST request is sent to inwx.com in order to update the A and AAAA record.
To use this script, you need to have created at least one DynDNS account on [inwx.com](https://www.inwx.com).


# Configuration

The script by default expects a TOML file `/etc/inwx_update_dyndns.toml` where your credentials are set. Have
a look at the [example file](example_config.toml), which should be self-explanatory. At the very least, you
need to update the username and password for the `[[account]]`. If you don't have an IPv6, `ipv6_enabled`
should be set to `false`. The config file used can be overridden by passing the command line argument '-c CONFIG'
with a different filename to the script (example: '-c ./example_config.toml').


# Requirements

* [requests](https://pypi.python.org/pypi/requests)
* [toml](https://pypi.python.org/pypi/toml)
