# sign-release

Easy automated release signing.

## Install

### Homebrew

```
brew install lukechilds/tap/sign-release
```

### Git

```
git clone https://github.com/lukechilds/sign-release.git ~/.sign-release
```

Then add to your shell profile:

```shell
export PATH="$PATH:$HOME/.sign-release/bin"
```

## Usage

```
$ sign-release
sign-release 0.0.0

Easy automated release signing.

Usage: sign-release <git-tag> <pgp-key>

Examples:
    sign-release v0.1.2 Umbrel
    sign-release v0.1.3-beta pgp@getumbrel.com

GitHub: https://github.com/lukechilds/sign-release
```

## Example

```
umbrel $ git tag v0.1.3-beta

umbrel $ sign-release v0.1.3-beta pgp@getumbrel.com
Using the following key:
pub   rsa2048 2020-07-17 [SC] [expires: 2022-07-17]
      63BEF6269923AF3AA19DD1D3F445BE6C381EC0C0
uid           [ultimate] Umbrel <pgp@getumbrel.com>
sub   rsa2048 2020-07-17 [E] [expires: 2022-07-17]

Building release archives for v0.1.3-beta...
Building umbrel-v0.1.3-beta.tar.gz...
Building umbrel-v0.1.3-beta.zip...
Calculating shasums...
Signing shasums...
Done!

Release assets at:
/tmp/sign-release/1594999454-12893-umbrel-v0.1.3-beta

-----BEGIN PGP SIGNED MESSAGE-----
Hash: SHA256

1830f01356bc7dcebb1f2487b91d1a31cb14c6de806896dea40154e57c74db51  umbrel-v0.1.3-beta.tar.gz
73851fe2143036420590774f0ef4a82a8dc91e4d84d28d4fa0697cdc7ced8c05  umbrel-v0.1.3-beta.zip
-----BEGIN PGP SIGNATURE-----

iQFGBAEBCAAwFiEEY772JpkjrzqhndHT9EW+bDgewMAFAl8Rwp4SHHBncEBnZXR1
bWJyZWwuY29tAAoJEPRFvmw4HsDAZmAH/2ZU6IfQ//7SKM89Rr+K+bsRMcJ95FQ4
3yMeSwKjwODk3ImIq54lTN2G/tBIh3//dIv0pWQLBBIEeF3fT1uVZKIDBDwf6O6H
3rVSjev0BgzqIUnp+cjYvCRbtm/CiVU45IFqEtT7LrnPKUD+MEoOsuagJGVM8sH4
alTx0NNG1PfGUOhVrppBKE8sWmPHJWFKelBTx6yfr4XTRzpZGukI4RAMhamhhW79
Grkv64UYTO7MJBxMhIrsEwaFu4nelNj0n0vSy2c/wfxk/EBYHhpBec/VTTBTaeXs
EgRhCs9iGCmhRtuOS5eF+mtKfl9FUs7wtKkuxQmP2MM/drzLYJjLME8=
=VsKf
-----END PGP SIGNATURE-----

umbrel $ ls /tmp/sign-release/1594999454-12893-umbrel-v0.1.3-beta
SHASUMS256.asc
umbrel-v0.1.3-beta.tar.gz
umbrel-v0.1.3-beta.zip
```

## License

MIT © Luke Childs
