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
      <img alt="Repo size" src="https://img.shields.io/github/repo-size/nodetec/relays?color=%23DDB6F2&label=SIZE&logo=codesandbox&style=for-the-badge&logoColor=D9E0EE&labelColor=302D41" />
    </a>
</div>

Relays is used to host Nostr relay binaries.

The binaries have been tested with and are used by [Relay Wizard](https://github.com/nodetec/relaywizard "Relay Wizard") which is a CLI tool that helps you bootstrap a [Nostr](https://nostr.com/ "Nostr") relay.

## Download

To download a relay binary navigate to the [Releases](https://github.com/nodetec/relays/releases "Releases") page and click on the binary you want to download.

Alternatively, you can use Relay Wizard which will download the binary for your preferred relay implementation as well as bootstrap the rest of the relay.

## Verification

Before running the binaries, you should first verify their authenticity. This will minimize the possibility of the binaries being compromised. To perform the verification you'll need to have `gnupg` and `curl` installed which are most likely already installed on your system, but if not here's how to install them on some operating systems:

### gnupg

#### Arch

```sh
sudo pacman -S gnupg
```

#### Debian/Ubuntu

```sh
sudo apt install -y gnupg
```

### curl

#### Arch

```sh
sudo pacman -S curl
```

#### Debian/Ubuntu

```sh
sudo apt install -y curl
```

Now you need to import the public key that signed the manifest file which you can do by running the following command:

```sh
curl https://keybase.io/nodetec/pgp_keys.asc | gpg --import
```

You're now ready to verify the manifest file. You will need to have the `relays-x.x.x-manifest.sha512sum` and the `relays-x.x.x-manifest.sha512sum.asc` files in the same directory as the binaries you downloaded where the `x.x.x` is replaced by whatever version of `relays` you're verifying.

To verify the manifest file run the following command:

```sh
gpg --verify relays-x.x.x-manifest.sha512sum.asc
```

Here's the command to run for the latest version of `relays`:

```sh
gpg --verify relays-0.1.0-manifest.sha512sum.asc
```

You should see output similar to the following if the verification was successful:

```sh
gpg: assuming signed data in 'relays-0.1.0-manifest.sha512sum'
gpg: Signature made Sat Sep 14 21:12:34 2024 EDT
gpg:                using RSA key 252F57B9DCD920EBF14E6151A8841CC4D10CC288
gpg: Good signature from "NODE-TEC Devs <devs@node-tec.com>" [unknown]
gpg:                 aka "[jpeg image of size 5143]" [unknown]
Primary key fingerprint: 04BD 8C20 598F A5FD DE19  BECD 8F24 69F7 1314 FAD7
     Subkey fingerprint: 252F 57B9 DCD9 20EB F14E  6151 A884 1CC4 D10C C288
```

> Unless you tell GnuPG to trust the key, you'll see a warning similar to the following:

```sh
gpg: WARNING: This key is not certified with a trusted signature!
gpg:          There is no indication that the signature belongs to the owner.
```

This warning means that the key is not certified by another third party authority. If the downloaded file was a fake, then the signature verification process would fail and you would be warned that the fingerprints don't match.

When you get a warning like this it's also good practice to check the key against other sources, e.g., the [NODE-TEC Keybase](https://keybase.io/nodetec "NODE-TEC Keybase") or the [NODE-TEC GitHub](https://github.com/nodetec "NODE-TEC GitHub").

You have now verified the signature of the manifest file which ensures the integrity and authenticity of the file but not of the binaries.

To verify the binaries you'll need to recompute the SHA512 hashes of the files, compare them with the corresponding hashes in the manifest file, and ensure they match exactly which you can do by running the following command:

```sh
sha512sum --check relays-x.x.x-manifest.sha512sum
```

Here's the command to run for the latest version of `relays`:

```sh
sha512sum --check relays-0.1.0-manifest.sha512sum
```

If the verification was successful you should see the output similar to the following:

```sh
khatru29-0.4.0-x86_64-linux-gnu.tar.gz: OK
khatru-pyramid-0.0.5-x86_64-linux-gnu.tar.gz: OK
strfry-0.9.7-x86_64-linux-gnu.tar.gz: OK
```

By completing the above steps you will have successfully verified the integrity of the binaries.

> The `relays-x.x.x-manifest.sha512sum` file contains checksums for multiple relay implementations, and you may not have downloaded all of them. This is why you may see output showing `No such file or directory` for the missing files. Unless you’re using one of those files, you can ignore the output associated with them.

## Learn More

If you want to learn more about how to setup a relay from scratch, check out [Relay Runner](https://relayrunner.org "Relay Runner")

If you just want to know enough to get started, read the following sections to get a server, hook up a domain name and setup remote access:

- [Get a server](https://relayrunner.org/server/get-a-server "Get a server")

- [Get a domain](https://relayrunner.org/server/domain-name "Get a domain")

- [Remote access](https://relayrunner.org/server/remote-access "Remote access")

You should then be able to run Relay Wizard:

```bash
curl -sL https://relayrunner.org/relaywizard.sh | bash
```

## Contribute

If you want to contribute consider testing the binaries by setting up your own relays, by following the Relay Runner guides, and by using Relay Wizard.
