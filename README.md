# ns8-tailscale

[Tailscale](https://tailscale.com/) is a zero-config VPN service that simplifies secure network access.

## Install

Install via Software Center by adding my repo as explained [here](https://repo.mrmarkuz.com)

Instantiate the module with:

    add-module ghcr.io/nethserver/tailscale:latest 1

The output of the command will return the instance name.
Output example:

    {"module_id": "tailscale1", "image_name": "tailscale", "image_url": "ghcr.io/nethserver/tailscale:latest"}

## Configure

A server is needed, you could use the [ns8-headscale](https://github.com/mrmarkuz/ns8-headscale) app.

Configure the server URL and the client name for the tailscale node. If you want to use an authentication key, create a preauth key in the Headscale UI (under a user) and enter it in the advanced settings in the NS8 tailscale app settings. This way you'll get connected immediately after the configuration.

If you start tailscale without the key, follow the logs to catch the Auth URL, it looks like `https://headscale.domain.tld/register/vIdg_q09ZstDyt6bNzY-xBtT`
Browse to the auth URL, copy the key and enter it in Headscale UI to get connected.

## Uninstall

To uninstall the instance:

    remove-module --no-preserve tailscale1
