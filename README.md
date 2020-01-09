## Retrieve key

### Keyserver

https://keys.openpgp.org/vks/v1/by-fingerprint/10D696027B29E96576F9EB6A30C1B8AAF9FFABDF

#### Restraints

* [Kuketz 2019-06](https://www.kuketz-blog.de/keys-openpgp-org-gnupg-schluesselserver-mit-e-mail-verifikation/)
* [Heise 2019-07](https://www.heise.de/security/meldung/Angriff-auf-PGP-Keyserver-demonstriert-hoffnugslose-Situation-4458354.html)
* [Heise 2019-06](https://www.heise.de/security/meldung/Neuer-OpenPGP-Keyserver-liefert-endlich-verifizierte-Schluessel-4450814.html)

### GitHub

The connection between GitHub's CDN ["Fastly"](https://www.fastly.com/) (*.githubusercontent.com, *.github.io) and GitHub's origin server is not encrypted!
```
wget https://github.com/m3t/id/archive/master.zip
```
```
git clone https://github.com/m3t/id.git
```

### DNS record OPENPGPKEY

> It would be better to retrieve my OpenPGP key from a DNS record which is validated [using DNSSEC](https://github.com/m3t/integrity-trust#dnssec).

```
gpg2 --no-default-keyring --keyring /tmp/gpg-temp --auto-key-locate dane --locate-keys "<e-mail address>"
```

```
openpgp-fetch "<e-mail address>" | gpg2 --with-fingerprint
```


## `0xF9FFABDF`
Manually merged details about my OpenPGP key:
```
gpg2 --with-fingerprint --with-fingerprint --list-secret-keys 0xF9FFABDF
gpg2 --edit-key 0xF9FFABDF
```

```
sec#  4096R/0xF9FFABDF  created: 2016-01-22  usage: SCE
      Key fingerprint = 10D6 9602 7B29 E965 76F9  EB6A 30C1 B8AA F9FF ABDF
uid   mlt posteo de (offline master key w/ subkeys on smartcard; see policy url) <mlt posteo de>
ssb>  2048R/0x6D8AF299  created: 2016-01-22  usage: S
      Key fingerprint = 8E89 A514 F835 DCB6 1503  DEE7 ACED 06F5 6D8A F299
ssb>  2048R/0x5AE7402E  created: 2016-01-22  usage: E
      Key fingerprint = 02A4 FE3F CD9E B1A0 901F  3586 4284 6DA1 5AE7 402E
ssb>  2048R/0xB2ACE772  created: 2016-01-22  usage: A
      Key fingerprint = 0DC8 A2A5 D687 BD9A A22A  536A E4EE 6458 B2AC E772

(E=encryption, S=signing, C=certification, A=authentication)
```

Show policy URL and notations:
```
gpg2 --list-options show-policy-urls,show-notations --list-sigs 0xF9FFABDF
```
