<div align="center"><p>
    <h1>Relays 📡</h1>
    <a href="https://github.com/nodetec/relays/releases/latest">
      <img alt="Latest release" src="https://img.shields.io/github/v/release/nodetec/relays?style=for-the-badge&logo=starship&color=C9CBFF&logoColor=D9E0EE&labelColor=302D41" />
    </a>
    <a href="https://github.com/nodetec/relays/pulse">
      <img alt="Last commit" src="https://img.shields.io/github/last-commit/nodetec/relays?style=for-the-badge&logo=starship&color=8bd5ca&logoColor=D9E0EE&labelColor=302D41"/>
    </a>
    <a href="https://github.com/nodetec/relays/stargazers">
      <img alt="Stars" src="https://img.shields.io/github/stars/nodetec/relays?style=for-the-badge&logo=starship&color=c69ff5&logoColor=D9E0EE&labelColor=302D41" />
    </a>
    <a href="https://github.com/nodetec/relays/issues">
      <img alt="Issues" src="https://img.shields.io/github/issues/nodetec/relays?style=for-the-badge&logo=bilibili&color=F5E0DC&logoColor=D9E0EE&labelColor=302D41" />
    </a>
    <a href="https://github.com/nodetec/relays">
      <img alt="Repo Size" src="https://img.shields.io/github/repo-size/nodetec/relays?color=%23DDB6F2&label=SIZE&logo=codesandbox&style=for-the-badge&logoColor=D9E0EE&labelColor=302D41" />
    </a>
</div>

Relays is used to host Nostr relay binaries.

The binaries have been tested with and are used by [Relay Wizard](https://github.com/nodetec/relaywizard) which is a CLI tool that helps you bootstrap a [Nostr](https://nostr.com/) relay.

## Download

To download a relay binary navigate to the [Releases](https://github.com/nodetec/relays/releases) page and click on the binary you want to download.

Alternatively, you can use Relay Wizard which will download the binary for your preferred relay implementation as well as bootstrap the rest of the relay.

## Learn More

If you want to learn more about how to setup a relay from scratch, check out [Relay Runner](https://relayrunner.org)

If you just want to know enough to get started, read the following sections to get a server, hook up a domain name and setup remote access:

- [Get a server](https://relayrunner.org/server/get-a-server)

- [Get a domain](https://relayrunner.org/server/domain-name)

- [Remote access](https://relayrunner.org/server/remote-access)

You should then be able to run Relay Wizard:

```bash
curl -sL https://relayrunner.org/relaywizard.sh | bash
```

## Contribute

If you want to contribute consider testing the binaries by setting up your own relays, by following the Relay Runner guides, and by using Relay Wizard.
