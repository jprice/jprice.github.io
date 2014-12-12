#Needs fixing

# GPG Tutorial

This was once just a page that contained my public encryption key.  It has
now grown to become an introduction to how and why to use the GNU Privacy
Guard encryption software (GPG) to protect your privacy.  It is continually
growing.  If you have questions, corrections, suggestions, software
recommendations, or want to exchange encrypted e-mails, please contact [Alan Eliasen](mailto:eliasen@mindspring.com).  I'm also on the
Twitter thingy as [aeliasen](https://twitter.com/aeliasen). Thanks!

## <a name="TOC">Table of Contents</a>

*   [Public Key for Alan Eliasen](https://futureboy.us/pgp.html#PublicKey)
*   [What is Public-Key Cryptography?](https://futureboy.us/pgp.html#PublicKeyCrypto)
*   [What I Use](./GPG tutorial and PGP Public Key for Alan Eliasen_files/GPG tutorial and PGP Public Key for Alan Eliasen.html)

*   [On Android](https://futureboy.us/pgp.html#OnAndroid)
*   [gpg or gpg2 ?](https://futureboy.us/pgp.html#gpgorgpg2)

*   [Importing A Key](https://futureboy.us/pgp.html#ImportingAKey)

*   [Importing from Enigmail](https://futureboy.us/pgp.html#ImportingFromEnigmail)
*   [Importing from GPG](https://futureboy.us/pgp.html#ImportingFromEnigmail)

*   [Getting Help](https://futureboy.us/pgp.html#GettingHelp)
*   [Getting Started](https://futureboy.us/pgp.html#GettingStarted)
*   [Generating a Revocation Key](https://futureboy.us/pgp.html#RevocationKey)

*   [Procedure for
Verification](https://futureboy.us/pgp.html#ProcedureForVerification)

*   [Fingerprint](https://futureboy.us/pgp.html#Fingerprint)

*   [Fingerprints in
Enigmail](https://futureboy.us/pgp.html#FingerprintsInEnigmail)

*   [Signing a Key](https://futureboy.us/pgp.html#SigningAKey)

*   [Signing Keys in
Enigmail](https://futureboy.us/pgp.html#SigningKeysInEnigmail)
*   [Signing Keys in GPG](https://futureboy.us/pgp.html#SigningKeysInGPG)

*   [Publishing your Public Key](https://futureboy.us/pgp.html#Publishing)

*   [Manual Exporting](https://futureboy.us/pgp.html#ManualExporting)
*   [Uploading a Public Key via
GPG](https://futureboy.us/pgp.html#UploadingViaGPG)
*   [Uploading a Public Key via Enigmail](https://futureboy.us/pgp.html#UploadingViaEnigmail)

*   [Manually Decrypting](https://futureboy.us/pgp.html#ManuallyDecrypting)
*   [Manually Encrypting](https://futureboy.us/pgp.html#ManuallyEncrypting)

*   [Encrypting for E-mail](https://futureboy.us/pgp.html#EncryptingForEmail)
*   [Encrypting Files](https://futureboy.us/pgp.html#EncryptingFiles)

*   [Attachments and PGP/MIME](https://futureboy.us/pgp.html#Attachments)

*   [Attachments in Enigmail](https://futureboy.us/pgp.html#AttachmentsInEnigmail)

*   [Disabling PGP/MIME in Enigmail](https://futureboy.us/pgp.html#DisablingPGPMIME)

*   [Signing Messages](https://futureboy.us/pgp.html#SigningMessages)

*   [Configuring Enigmail
for Automatic Signing](https://futureboy.us/pgp.html#EnigmailAutomaticSigning)
*   [Signing a Plaintext
Message](https://futureboy.us/pgp.html#SigningPlaintext)
*   [Verifying Signatures](https://futureboy.us/pgp.html#VerifyingSignatures)
*   [Detached Signature](https://futureboy.us/pgp.html#DetachedSignature)
*   [Proving You Wrote Something but Remaining Temporarily Anonymous](https://futureboy.us/pgp.html#ProvingAnonymous)

*   [Updating Keys](https://futureboy.us/pgp.html#UpdatingKeys)

*   [Updating Keys in
Enigmail](https://futureboy.us/pgp.html#UpdatingKeysEnigmail)
*   [Listing your Keys](https://futureboy.us/pgp.html#ListingKeys)
*   [Who Signed My Key?](https://futureboy.us/pgp.html#WhoSigned)

*   [Building a Web of Trust](https://futureboy.us/pgp.html#WebOfTrust)
*   [Good Encryption Practices](https://futureboy.us/pgp.html#GoodPractices)
*   [Symmetric Encryption/Decryption](https://futureboy.us/pgp.html#Symmetric)
*   [Symmetric Encryption/Decryption](https://futureboy.us/pgp.html#Symmetric)
*   [Why Public-Key Encryption is Cool](https://futureboy.us/pgp.html#Cool)

*   [Tips and Tricks](https://futureboy.us/pgp.html#TipsAndTricks)

*   [Using Stronger Algorithms](https://futureboy.us/pgp.html#StrongerAlgorithms)
*   [Verbose Information](https://futureboy.us/pgp.html#VerboseInformation)
*   [Requiring Multiple
Decrypts](https://futureboy.us/pgp.html#MultipleDecrypts)
*   [Hidden Recipients](https://futureboy.us/pgp.html#HiddenRecipients)
*   [Encrypting Messages You
Can't Decrypt](https://futureboy.us/pgp.html#OneWayEncryption)

*   [In GPG](https://futureboy.us/pgp.html#OneWayGPG)
*   [In Enigmail](https://futureboy.us/pgp.html#OneWayEnigmail)
*   [Migrating to a New Key](https://futureboy.us/pgp.html#Migrating)

*   [Creating Your Own New Key](https://futureboy.us/pgp.html#OwnNewKey)
*   [Using Someone Else's New
Public Key](https://futureboy.us/pgp.html#OthersNewKey)
*   [Keysigning Party](https://futureboy.us/pgp.html#KeysigningParty)

*   [Technical Notes](https://futureboy.us/pgp.html#TechnicalNotes)

*   [Short Key IDs Are Bad News](https://futureboy.us/pgp.html#ShortKeyID)
*   [Finding Your Longer Key ID](https://futureboy.us/pgp.html#LongerKeyID)
*   [Key IDs and Hash Algorithms](https://futureboy.us/pgp.html#KeyIDsHash)
*   [Enigmail, gpg-agent, and Gnome
keyring bugs](https://futureboy.us/pgp.html#BadGnome)
*   [Automating GPG](https://futureboy.us/pgp.html#Automating)
*   [Forcing Different
Algorithms](https://futureboy.us/pgp.html#ForcingAlgorithms)
*   [Protecting your Secret
Keys](https://futureboy.us/pgp.html#ProtectingSecretKeys)
*   [Backing Up Your
Secret Key](https://futureboy.us/pgp.html#BackingUpYourSecretKey)
*   ["Creating the perfect GPG
keypair"](https://futureboy.us/pgp.html#PerfectKeypair)
*   [OpenPGP Specification](https://futureboy.us/pgp.html#OpenPGPSpecification)

## <a name="PublicKey">Public Key for Alan Eliasen</a>

Below is the public encryption key for Alan Eliasen,
([eliasen@mindspring.com](mailto:eliasen@mindspring.com)) in
armored OpenPGP format.  This lets you write encrypted messages that only I
can read!

**Note:**  I have recently upgraded to a stronger 4096-bit RSA key.
If you were previously using the old key, please see my [key migration document](https://futureboy.us/gpgmigration.txt) for more information on
the reasons for this change and how to migrate to the new key.

<pre>-----BEGIN PGP PUBLIC KEY BLOCK-----
  Version: GnuPG v1

  mQINBFPOzTUBEADT1kIEMY1Ix+9DyNfGHE9HPjLSI/Ybnsn/bbx8cWmeAktoYjBS
  q29mJ0tchjyG8KP38vlkvfNYKn80985a/p7ZKupxOm1dDyAn5TZguDG2fEgCYxcB
  FxfMjGKLEFOS6hlPVh/3bm7xEvRuB5P/5Wdch9/UK11qLE3hlDlhnT1zq82Sk4G8
  OWnH8BLA8XuRAdwAdri7U2OmNPqCldlmpIsTy68MXJQk7tYi0Rwc55c65U4gGSuY
  qw3QzQ6X4TecFO/jUPBnnVb5YcYKxVw75PYF6NnKbbsnDYJoNg8bpEP2SVC0FWNK
  2rKYsGsbcco2/ruJuQsThVcuH3l07cAKaSzt+eb5+FWWzsojbSeXwD8yZocfPvEL
  eaa0/Jr2220sV6OdSpWBa8mhBI5oTAbD9PDX3C5gyPj78mzDlhytLTCsdtL1Uqgm
  DTbIqgDPQBEnGr9Ny2XlIQ6AjuyuahBDl+ElmLnz0jI9bjt0vgAUGjmCCp71aioo
  MXZALwVBsdQH3w2BHQ8wU9sYtMlBPBMZz++oIQthmJ+Gb6myvMZCQ34M9TfpIv5i
  utAK2xBP/XfBl5BMYl6xNUHOxGhtBj/Pbzcwu/+Sk3mKkC4E2+aUKEjyzs6rDdDs
  pT+2B4A1nNXLU1PA+AfabdLnlvm7lMgzr30Waejcz4FbSdwCX8oN9UabBQARAQAB
  tCVBbGFuIEVsaWFzZW4gPGVsaWFzZW5AbWluZHNwcmluZy5jb20+iQI+BBMBAgAo
  AhsDAh4BAheABQJTzs3fCgsJDQoIDAcLAwIHFQoJCAsCAwUWAgMBAAAKCRBfK0dW
  7Yc9IyHnD/9+eGTV9TwtSaafDyoqUiLSX3MBwJ6np5jCiYlIeq6AMtaQ/idemtu5
  +sJcT6XH+dkZwd+e8LZfT536lmC593jhNEdNs80Yx7q0vtv0UCGf+xk4y16ldjPQ
  qYN6F3J6z7/7Uo3oiF6f30aJ5YpxzT2dUGhAbQNSUIPZLMLbHg79+yDMy8djIsmv
  z6N+GzVkEFjw0wF6M46To0p7tqwu7FMkUPJv/oHZdfW43/QAlaiYjDPjOHwWwqEb
  bOTpW4hoxwbmGOnM+nuZP8fcGc//1Fvurwl37K4bg72YQ3PPb/bMHXHxZGQXWw2K
  iPt9jneAMrT2+92MZ8kk8tiwc3Pv+k9wOWbkn01zw2Cn1cO1Ib/EGcnCUVMcVg4c
  JBX6G07Ey37EQvm9RGcNrRoKuBqcObjjg1S1ABxe1Wm+geFSkcG10mdrqPP2lYMS
  xS7byJn9zM8oSCwr5XggaqHuMuxz3sFw5rU8nQAWmjC4rNEJ0wuU2FjsPHF5KmbA
  HKUup30jkE308Sjtdvz6+YoZEHOFyotOcxlUwmnYos6S+CO3u5euVKXJ871+i3Wd
  A0Fb5wz4R5U3SE8RgdpzKY10IN6bwCSgGUflKh9hKpkT5aLY1EcUK2zumMwmaJ9c
  IMsxI2iDmAa1Xpbof7h2KNOIfrGz3n1UrHnAZEqX6OzftKp8+5WugIhGBBARAgAG
  BQJTzuGrAAoJEOSBhLWwVnaxj7EAoMxh7ycVIU2xEee0kkNzif299NXvAKCpFnts
  iNcSu34mmQeGhikf10LaprkCDQRTzs01ARAA8jMbb8iyvIQJPjYg96ifkwNd1Usq
  WQqbjgmxHQ93b27FWzJEr9DrTxFnlHE1Xp/7XbRD83xpVzBhr/0O758HmM14oJFu
  5pyao4y2xJMz/Y4CSmi650kixhrJefZz7vZ4SEEo2xMbLPnFwQG1h6L3ixw6UYUG
  uF+YZ42ClDlnTshR8npeWax4x+wnWFK3rsfKXMh442IJFIExLhzWlS8amj/Ir6kQ
  USeRNdry5CRhwPdFwVl9Tj/Nf/H+keMdvar43KzgFNJ/DHh8yshIQBB96ja763gX
  XH5wJ/mf7CChdbgZqKXU9RD0t+zumvb+jGTgSrIfdI/D6Lc4r+iC4N1aXhaleH2P
  UC5vMN1VxvnrUPPFU1O7O4jZjX3SRPiprmkwqjzfiPYhgLOGT+ejWjOjYuuKBXH7
  YNzYMc7HUV6p3BHEylgCmJ96yRzxNDouI1PAgVatu4/d5ZFFj6ibtqObo4UAZQ+8
  At4Ys5zOjxHXFst7CtodUWotl8B6ZWv5yHW07qGZ0xdRpwduHWj7mqAUEot+2YLM
  Gry2fSdCbpcguTWIvKQQnF0tQq8sEuuVpQ2MNosm3hm+u0kajzjltwP/W0TVg96R
  t03mZ3IAdYclVPgoxHIVKOa+pNQLmC0eZk1dZ3X9EFr1D5M3CSdG8VH7HZqKk4N3
  dzpQ3oBoAkmKor8AEQEAAYkCHwQYAQIACQUCU87NNQIbDAAKCRBfK0dW7Yc9I8ai
  D/9YS+IgcZlaHVrN/H7sewqyNEUa5T4wz6F3QvT44+QxJBKCW/NQuUrnqv7hn2DI
  mXMXeG8/99WPKM3tHf0mxq2/uLOMqi92SzuSP2Qefbp3P/VviaBzqkIEIQWGCczQ
  //Dg8sWX/UbAxhZ5he/PESjRx0PmWSsPvhGOisxcZV7BVmmpICd9W6l6i55oHWXn
  pVivVBmAK3+XInQ4ybCJ0+jAZ5FlOmoGuwq1OXX0h97P0h4Hzb3u7jEwdkVsSx4B
  vtlIwld9+alC0izsCC6fCHpjrK31nTffFJ/PhvojLGiRla6f7qNKFRHabY7U0ldY
  MfSgsGInICTvt2py2SdBWQh+SO/K3Y6Pb96Y/tDQUHLay31dmXCoTslcebseZCW+
  WPOGKehlBFWdhDGuP/2HqJbU/HG1k8OKIqPYIFVFbtzX0rzuq7M4pRlJ1fSg08QM
  TOQjhfrbm46GNT2xwaAIpHnDBD7BC7R+xrY60wiEqqAPISJsUDJFK7cRQjZV0L7+
  k9+IjspuzYYvXr2mKKIAojUE/KLxbd6KuXIk07P+vKse66oC8XVpbn6ckMypftid
  YyyyH5jej2NP0FuP9jjl8eYgSZl9tqaU6Y9vDyXzE0h6F4SUPiBx3hEIrVzFJym0
  d6/t562bstQOpIPGkZxLOFm59msUf9mBqw7rJEs/EqhQ2w==
  =YGTe
  -----END PGP PUBLIC KEY BLOCK-----
</pre>

<table border="0" summary="Key IDs and Fingerprints">
  <tbody><tr><th>Fingerprint:</th><td class="litr">EC2392F2EDE74488680DA3CF5F2B4756ED873D23
  </td></tr><tr><th>Long Key ID:</th><td class="litr">5F2B4756ED873D23
  </td></tr><tr><th>Short Key ID:</th><td class="litr">ED873D23
  </td></tr></tbody></table>

  _(Did you notice that the long and short key IDs (of any key) are just
  the last 16 or 8 digits of its fingerprint respectively?  I didn't know
  that for a long time, but it's obvious when displayed this way.  See the [Finding your longer key ID](https://futureboy.us/pgp.html#LongerKeyID) section of this document
  for more.)_

  This is also available in a [plaintext file](https://futureboy.us/pgp.txt).

  ## <a name="PublicKeyCrypto">What is Public-Key Cryptography?</a>

  In short, public-key cryptography solves the age-old problem "how do I
  communicate with someone securely without somehow exchanging a secret
  password first?"  Exchanging a shared password securely is a hard problem.
  You may have no way to do so if your communications are monitored.

  With public-key encryption, instead of sharing a password, each party
  generates a "keypair" consisting of a "public" key and a "secret/private"
  key.  Each party can then publish their "public" key to the world or send
  it directly to the other party, while keeping their secret key private and
  safe.

  If you have Person B's public key, you can do a few things with it:

  *   Encrypt a message that only that Person B can decrypt.  (They need their
  secret key to decrypt it.)

  *   Validate that Person B signed a message with their secret key. This
  also lets you verify strongly that the message was not corrupted nor
  modified in transmission.

  With your secret key, you can do a few things:

  *   Decrypt messages encrypted with your public key.

  *   Sign messages that others can verify came from you (they need your
  public key to verify the signature.)

  ## <a name="WhatIUse">What I Use</a>

  I accept and transmit all messages using the OpenPGP format, which is an
  open standard, ([RFC 4880](http://www.ietf.org/rfc/rfc4880.txt))
  and the most widely used standard for public encryption, so communication
  should work with any OpenPGP-compatible program.

  For encryption and signing of e-mail (on Windows, Linux, and Mac) you can
  use a combination of:

  *   [GNU Privacy Guard](http://www.gnupg.org/) (GPG)

  *   [Thunderbird](http://www.mozilla.org/products/thunderbird/),
  mozilla.org's stand-alone mail client.

  *   The Mozilla [Enigmail](http://enigmail.mozdev.org/) add-on.

  If you're on Fedora, you will have infinitely better luck installing
  Enigmail from the Fedora distribution rather than obtaining the plug-in
  elsewhere.  Install all three packages it by doing the following as root:

  `yum install gnupg thunderbird thunderbird-enigmail`

  After installing or updating in Fedora, you may not see the OpenPGP menus
  in Thunderbird until going to `Tools | Add-ons` and then
  disabling Enigmail, restarting Thunderbird, re-enabling Enigmail, and
  restarting Thunderbird.

  My main gripe is that Thunderbird changes version numbers rapidly and
  Enigmail sometimes doesn't keep up, which makes Enigmail claim that it's
  incompatible with your Fedora version.  This is an important reason to use
  a package-manager like `yum` on Fedora which tends to keep them
  in sync.  This is another reason it's good to know how to use the gpg
  executable manually.

  The first thing you want to do in Enigmail is to make all of its settings
  visible. You can do this from the menu items `Enigmail | Preferences |
  Display Expert Settings and Menus`.  The basic settings are
  inadequate.

  **Note:** As of the latest update of Enigmail, around July 2014, the
  text used in several menu items has changed.  The old top-level menu item
  was called `OpenPGP` and the new one is called
  `Enigmail`.  You may need to mentally correct these examples if
  you're using an old version of Enigmail.

  In Enigmail, I've had the best luck setting the keyserver to default to
  `pgp.mit.edu`, but this may no longer be necessary
  as it now contains a list of default keyservers which are more stable than
  they used to be.  (But often still down.)

  The Gnu Privacy Guard
  [FAQ](http://www.gnupg.org/faq/GnuPG-FAQ.html#which-email-client-can-i-use-with-gnupg) lists some of the other e-mail programs compatible
  with GPG.  Note that you can use _any_ e-mail program (that doesn't
  corrupt messages) along with the `gpg` executable on the
  command-line.

  For Macintosh, you can obtain GPG from the [GPGTools](https://gpgtools.org/) website.  (I haven't personally
  used these, but others have recommended them.)

  Alternately, I sometimes use the `pgg` package in Emacs/XEmacs
  which is a wrapper around the `gpg` executable's functions.  You
  can do something like highlight a region and do:
  `M-x pgg-encrypt-region` and encrypt directly within your
  documents.

  For encrypting files, or doing anything more interesting, I just use the
  `gpg` program on the command-line.  If you're security-paranoid,
  the fewer executables, the better.  Most of this document teaches you the
  fun and important things you can do with the `gpg` program to be
  secure.

  ### <a name="OnAndroid">On Android</a>

  On Android, you may want to experiment with [R2Mail2](http://r2mail2.com/).  I haven't used it and can't vouch
  for it.  There is also [Android
  Privacy Guard (APG)](https://play.google.com/store/apps/details?id=org.thialfihar.android.apg&hl=en), which integrates with the [K-9
  Mail](https://play.google.com/store/apps/details?id=com.fsck.k9&hl=en) program, but I do not vouch for it.  APG was not updated for
  a few years, but has seen activity more recently.

  ## <a name="gpgorgpg2">gpg or gpg2 ?</a>

  GPG version 2 may be on your system with the executable name
  `gpg2` .  Either executable can be used for these
  demonstrations.  Both are very compatible with each other.  (If you want to
  know a million different opinions on which you should be using, do a web
  search.)  Version 1 is more tested, and is usually a single monolithic
  executable.  Version 2 is compiled with crypto libraries like
  `libgcrypt` externally linked, and is designed to work better
  with external password entry tools.  That is, `gpg2` is designed
  for graphical environments, while `gpg` works better for
  automated and command-line use.  From the command-line, I use version 1.

  ## <a name="ImportingAKey">Importing A Key</a>

  ### <a name="ImportingFromEnigmail">Importing From Enigmail</a>

  The simplest way to import my key from an e-mail client (like Enigmail) is
  to import it from a keyserver.  In Enigmail, you can search for keys using
  the menu items `Enigmail | Key Management | Keyserver | Search for
  Keys`, and then searching for my name or my e-mail
  address `eliasen@mindspring.com` or my key ID, which is
  `5F2B4756ED873D23` or the shorter `ED873D23`.  Then
  select its checkbox from the list and click "OK."

  A lazier and more dangerous way to import my public key from Enigmail is
  to try and send me an encrypted e-mail.  (When composing a message, choose
  the menu item `Enigmail` and select both `Sign
  Message` and `Encrypt message`.)  Then, when you try to
  send, Enigmail will realize that it doesn't have my public key, and will
  bring up the Key Management window.  From there, you can
  choose `Download Missing Keys`.

  Another way to import my key is to e-mail
  [the plaintext version of my key](https://futureboy.us/pgp.txt) to your own e-mail
  address and choose the option like "Import PGP Key."

  ### <a name="ImportingFromGPG">Importing From GPG</a>

  If your e-mail client doesn't allow automatic import of keys from an e-mail
  message, you will need to save the plaintext file listed above key to a
  file, then import the key manually.  From GNU Privacy Guard, this is:

  `gpg --import _[filename]_`

  My key is available from `pgp.mit.edu` (all the major
  keyservers mirror each other, so you could probably get it from the
  keyserver of your choice, but this one seems to be pretty reliable.)

  You can browse the keys available on keyservers
  at [pgp.mit.edu](http://pgp.mit.edu/) or the
  often-slow [sks-keyservers.net](https://sks-keyservers.net/).
  Who do you know who has a posted public key?

  From GNU Privacy Guard, you could import my key using the following (but
  read on to be more secure.)

  `gpg --keyserver pgp.mit.edu --search-keys eliasen@mindspring.com`

  Note that in all of these examples, whenever you see an e-mail address,
  you can usually substitute part of a name or part of an e-mail address, or
  a key ID.  Most of these commands perform a substring search.

  Or, even more directly, my full key fingerprint is
  `EC2392F2EDE74488680DA3CF5F2B4756ED873D23`, (it's more common
  but less secure to use the last 16 or 8 characters of a key, so
  `ED873D23` will work too. (Note that the shorter key IDs are
  just the last 16 or 8 characters of the fingerprint!)  Read the technical
  note on [Short Key IDs](https://futureboy.us/pgp.html#ShortKeyID) below for interesting
  attack ideas using short keys.)  The following gpg command will import my
  key from a keyserver, using my full fingerprint (you can also use the last
  8 or 16 hexadecimal digits of the fingerprint as the short or long key
  IDs.)

  `gpg --keyserver pgp.mit.edu --recv-keys EC2392F2EDE74488680DA3CF5F2B4756ED873D23`

  Read on, though, and see why just importing some key off a keyserver isn't
  enough to be sure that you're talking with _me_.

  You may not have to specify a keyserver in the lines above.  Later versions
  of GPG have a more reliable keyserver list built in.

  [sks-keyservers.net](http://sks-keyservers.net/status/) monitors
  the status of keyservers in real-time.  (But it's often down.)  If you're
  having trouble importing signatures from a specific keyserver, or want a
  list of available keyservers, you might want to look there.

  ## <a name="GettingHelp">Getting Help</a>

  `gpg --help`

  is your friend.  It will list the most common options to GPG (but not all
  of them.)  Other complete documents are available:

  *   [GPG
  Manual](http://www.gnupg.org/documentation/manuals.en.html)
  *   [Using the
  GNU Privacy Guard](http://www.gnupg.org/documentation/manuals/gnupg/)
  *   [The GNU Privacy Handbook](http://www.gnupg.org/gph/en/manual.html)

  ## <a name="GettingStarted">Getting Started</a>

  I long resisted the temptation to give an overly-simplified "Getting
  Started" section here because that may falsely lead you to believe that
  you're being secure.  As this document has expanded greatly, it's becoming
  a better guide.  However, the best way to get started with encryption is to
  go to the home site for [GNU Privacy
  Guard](http://www.gnupg.org/) and read the "GNU Privacy Handbook" (available in lots of formats
  and languages) under the "Guides" section.  This will walk you through
  setting up GPG on your system, including creating your secret keys.

  Creating your secret key will start with:

  `gpg --gen-key`

  You should probably use the default settings, except it doesn't hurt to
  make the key size as large as allowed (4096 bits currently.)  The larger
  the key size, the longer it will take to initially generate your key (and
  encryption/decryption will be slightly slower.  That is a Good Thing, as
  anyone attempting to break your encryption will also need to spend more
  time too.)

  ## <a name="RevocationKey">Generating a Revocation Key</a>

  After generating your key, one of the first things you should do is create
  a revocation certificate:

  `gpg --gen-revoke --armor --output=RevocationCertificate.asc _your@email.address_`

  This certificate can be used to revoke your key if it is ever lost or
  compromised.  _Do not neglect this step!_ Print it out, save it on a
  disk, and store it safely.  It will be short enough that you can type it
  back in by hand without much effort if you just print it out.

  If you lose your secret key or it is compromised, you will want to revoke
  your key by uploading the revocation certificate to a public keyserver
  (assuming you uploaded your public key to a public keyserver in the first
  place.  See below.)

  If you have multiple unrevoked public keys and you have messages that say
  something like "I lost that one, this new key supersedes the other ones,"
  (and I've seen this from people who like to claim crypto experience) then I
  know _instantly_ that I can't trust you to follow good practice and
  maintain your secret information, and that I shouldn't trust you with my
  secrets.  So protect your revocation key like you protect your secret
  keys.  Read on to see why the "this key is my new key, ignore the others"
  excuse is an immediate "red flag" that should make you suspect either
  cryptographical incompetence or warn you that the person's being
  impersonated.

  ## Using Stronger Algorithms

  This section is optional but important.

  By default, gpg uses weaker encryption algorithms than it could.  This is
  to ensure compatibility with older versions.

  If you want to start using stronger algorithms from the beginning, jump to
  the [Using Stronger Algorithms](https://futureboy.us/pgp.html#StrongerAlgorithms) section
  below to see how to use stronger algorithms by default.  It may be
  important to do this from the start, as the algorithms that you want to use
  are specified in your public key.  (To be more specific, your public key
  lists the algorithms that you request _other people_ to use when they
  encrypt messages to you.)

  ## <a name="ProcedureForVerification">Procedure for Verification</a>

  Now, since you have my public key, are we secure?  Well, no, not at all.
  Lots of people just getting started with cryptography don't realize that
  they have to somehow _verify_ that this key belongs to me.  To me,
  Alan Eliasen.  The one who wrote this message.   How do you know that the
  public key posted above is the one I posted?  After all, the bad guys could
  have replaced it somehow.

  Listen carefully.  This is important.  _Anyone_ can generate a
  public key for _any_ e-mail address.  _Anyone_ can post that
  key to _any_ key server.  _Only by verifying that the key really
  belongs to the person you think it does does it give you any security._
  Without this crucial verification, all that your cryptographic software
  does is ensures that bits weren't corrupted during transmission, and
  prevents casual observers from reading the message.  It does _not_
  mean that you're talking to who you think you are.  You could be talking to
  someone else entirely (a bad guy,) or you could be subject to a
  man-in-the-middle attack.

  **Update:** As proof of the above paragraph, after I posted this
  document widely, on 2013-07-12, somebody generated a fake public key with
  my e-mail address and uploaded it to a key server!  _This is why you
  need to validate the key directly with the person to make sure you have the
  right key and the right person!_ That is, however, an unavoidable
  problem with public key servers.  I thus can't be mad about it, but I
  _can_ try to educate people to recognize this possibility and do the
  right thing by validating my public key with me personally!  Note that
  picking a key from multiple options on a keyserver based on which is newest
  or largest or by comments about "this is my newest key" _is dangerous
  and wrong._

  Still, if you want to send me encrypted e-mail, that may prevent other
  people from reading it.  That's good, and sometimes that's all you need.
  Just understand why I don't have any reason to trust that you're who you
  say you are, and you don't have any reason to trust that you're really
  talking to _me_ unless you've verified my key with me.  Before I
  trust you with any secrets, I'll validate your identity.

  ### <a name="Fingerprint">Fingerprint</a>

  A key could be verified in many ways (such as, I could read you my whole
  public key, which is really time-consuming and error-prone.  It's also bad
  because the key you see above can get longer and longer as other people
  sign it.)  The usual alternative is to compare the _fingerprint_ of
  what _you_ think my public key is with the fingerprint of what I
  _know_ my public key is.

  A fingerprint is a shorter number (usually expressed as a
  40-hexadecimal-digit number) that contains a cryptographically strong hash
  of my public key.  It's shorter than my full key, so it's not an unfoolable
  test, but the probability of finding another key with this fingerprint is
  very small indeed.  Infinitesimally small.  So small you don't have to
  worry about it.  If someone else can find a matching fingerprint, they have
  enough power and money that they could make you vanish from the face of the
  earth.  So, after you've imported my key, type:

  `gpg --fingerprint eliasen@mindspring.com`

  This will produce output that looks something like below (I have put the
  fingerprint in bold.)

  `
  pub   4096R/ED873D23 2014-07-22

  Key fingerprint = **EC23 92F2 EDE7 4488 680D  A3CF 5F2B 4756 ED87 3D23**

  uid                  Alan Eliasen <eliasen@mindspring.com>

  sub   4096R/5314E70B 2014-07-22

  `

  Then, you need to verify this fingerprint with me.  It's best to do it
  face-to-face, but if it's someone you know by voice, you can do it on the
  phone.  If you don't know the person, check their driver's license.  Ask
  other people (that you trust) who know them.  Even if you don't know them,
  at least you're verifying that the key belongs to the person you're talking
  to.

  The other person will need to verify that their (unverified) copy of your
  public key matches what you know your public key to be.  So bring a copy of
  your own fingerprint to the exchange:

  `gpg --fingerprint _your@email.address_`

  Of course, change the e-mail address above to the e-mail address you're
  confirming.

  _Corollary:_ If someone puts the fingerprint of their key in their
  e-mail signature, or in a web page, they really aren't proving their
  identity.  Think about it.  If someone's pretending to be you, and
  forging your e-mail or your web site, they'd certainly replace the
  fingerprint too.  It's not enough to rely on.  If you see someone with
  their key fingerprint in their e-mail signature, it's not a reliable sign
  that the key with that fingerprint truly belongs to them.

  #### <a name="FingerprintsInEnigmail">Fingerprints in Enigmail</a>

  If you want to view a person's fingerprint or key ID in Enigmail, you can
  view that in the "Key Management" dialog, which is the place where you can
  view and manage public and private keys for everyone in your keyring.

  The steps to view the fingerprint are to follow the menu items:
  `Enigmail` | `Key Management` | Search for a name |
  Right-click the name | `Key Properties`.  This will bring up a
  dialog containing lots of information about the key, including its key ID
  and fingerprint (unfortunately, it's not easily printable.)

  ### My Key Verification Protocol

  If you wish to verify this key, please contact me and I will verify its
  fingerprint in a public meeting-place.  I will be wearing a trenchcoat and
  a navy blue ascot.  You must wear or carry a yellow tulip.  Any other
  flower signifies that contact should be aborted, even if the exchange below
  is executed correctly.  I must not underestimate the necessity of having an
  adequate stock of proper yellow tulips on hand for this purpose.

  I will say "The adobe is filled with an excess of straw this season."

  You must reply "The straw is for the young lambs which roam the heaths
  near Glasgow in the green, green spring."

  If I am satisfied with your response, I will reply "The greens at Saint
  Andrew's are boiled with ham and contain an excess of bitter kale."

  Do not make eye contact or show signs of recognition.  If necessary, I will
  read the hexadecimal digits of the fingerprint while feigning a book order
  on my cell phone.

  Okay, I'm sort of kidding about this section.  But you
  _must verify keys with the other person to be truly secure._

  If you have verified my key, and trust me (and trust your own
  verification,) be sure to sign it.

  ## <a name="SigningAKey">Signing a Key</a>

  Now that you've verified my identity, and my public key, you need to tell
  your cryptographical software that you trust my key.  Otherwise, your
  cryptographical software should do the right thing and warn you that you're
  communicating with someone that you haven't verified.  It's telling you
  that it has no reason to believe that the key you're using is the one that
  actually belongs to that person.

  Below are tips for signing and trusting keys using both GPG and Enigmail.

  ### <a name="SigningKeysInEnigmail">Signing Keys in Enigmail</a>

  I'm a bit reticent to recommend using Enigmail to sign keys because some
  of its dialogs are deceptive and wrong.  Read the next part very carefully.

  In Enigmail, you can sign keys by going to the menu
  item `Enigmail | Key Management`.

  Search for the key, and then right-click it.  You'll get the option to
  sign the key.

  After signing the key, you should assign a trust level to the
  _person_ signing the key.  Right-click the key name and choose "Set
  Owner Trust".  **Warning:** This currently pops up a dialog that asks
  "how much do you trust the key?" but that's _not the right
  question_!  The meaning of trust in the GPG software is _how much
  you trust the **person** to validate **other** people's keys_,
  not how much you trust the key itself!  In GPG, the question is stated as:

  > "Please decide how far you trust this user to correctly verify other
  >     users' keys (by looking at passports, checking fingerprints from different
  >     sources, etc.)"

  As you can see, that's a totally different question.  This is why I
  encourage you to learn by using GPG on the command-line.  It tends to be
  more rigorous and correct.  Also GPG gives you more warnings about
  selecting dangerous choices like "trust ultimately."  Read the next section
  to find out more.

  ### <a name="SigningKeysInGPG">Signing keys in GPG</a>

  To sign my key from gpg, you'll do something like:

  `gpg --sign-key eliasen@mindspring.com`

  (but see below for a better option.)

  This will give you some options for signing the key.  Even better would be
  to edit your signature _and_ trust settings for this user using the
  interactive menu:

  `gpg --interactive --edit-key eliasen@mindspring.com`

  _Hint:_ Type `help` for the interactive commands.  The
  commands `sign` and `trust` are the ones you're
  looking for.  These allow you to both sign a key and indicate how much you
  trust me to verify _other_ peoples' keys.  If you think I'm stupid
  and lax when verifying and signing other peoples' keys, you'd assign me a
  low trust rating.

  After you've signed someone's key, you should send it back to them so
  they can show other people that you've signed it.  You can export their key
  using:

  `gpg --export --armor _their@email.address_`

  and then sending that output to them.  They can then import the changes
  using

  `gpg --import`

  In Enigmail, you can also attach any of the public keys in your keyring to
  an e-mail.  As you're composing the email, select `Enigmail | Attach
  Public Key...` and select the e-mail addresses to attach.  Note that
  these will not show up in the body of the message, but as a
  (possibly-encrypted) attachment, possibly using PGP/MIME.  For maximum
  portability, I recommend attaching using the `--export` method
  above and including the public key in the body of the message.  My reasons
  are stated in the [Attachments](https://futureboy.us/pgp.html#Attachments) section.

  You can also upload that signature to a keyserver, which makes that
  signature available to the world.  See the [Publishing
  your Public Key](https://futureboy.us/pgp.html#Publishing) section below for how to do this.

  If you're really not sure about my identity, and don't want to vouch for me
  publicly, you can _locally_ sign my key, which means that you
  trust it for your own use only:

  `gpg --lsign-key eliasen@mindspring.com`

  _Hint:_ If you publicly sign my key without actually verifying it
  with me, I'm going to assign you a very low trust rating.

  ## <a name="Publishing">Publishing your Public Key</a>

  Sure, you can manually send your public key to people you want to
  communicate with, but what if someone needs to communicate with you
  securely and you haven't sent them your public key?  The usual way is that
  you publish your public key to a keyserver so that anyone can import your
  key.  Most of the keyservers in the world mirror each
  other, so a short time after you have posted your key to one server, it will
  be propagated to the others.  As I have said above, I've had good luck for
  the past decade with `pgp.mit.edu`.

  You have some responsibilities before publishing your public key (or
  someone else's) to a keyserver, though.  As mentioned above in the [Getting Started](https://futureboy.us/pgp.html#GettingStarted) and [Procedure for Verification](https://futureboy.us/pgp.html#ProcedureForVerification) sections,
  you better have generated a revocation certificate for your key and put it
  somewhere very safe.  Otherwise, if you lose your secret key, or it becomes
  compromised, the corresponding public key will sit _forever_ on
  public keyservers, mocking you and demonstrating that you don't know how to
  protect your secrets properly.  If you think you can delete a key from a
  keyserver, rather than revoking it, read the [FAQ at MIT's keyserver.](http://pgp.mit.edu/faq.html) (I think
  it's funny and awesome that they have a fake "delete a key" field on their
  website that just redirects to that FAQ no matter what key you enter.)

  If someone has your public key, they can basically do a few things with it:

  1.  Encrypt messages that only you can decrypt.

  2.  Validate that messages were signed by your secret key with a strong
  guarantee of certainty, and ensure that those messages were not tampered
  with or corrupted in transmission.

  These are good things.  You _want_ people to have your public key.
  So below are a few methods of publishing your public key to a
  keyserver.  All achieve the same results.

  ### <a name="ManualExporting">Manual Exporting and Uploading</a>

  Now that you have generated a secret key and a public key, how do people
  find your public key so that can send encrypted mail to you?  You can
  send someone your public key directly by, say, putting it in an email.  To
  generate a copy of your public key that is easily e-mailed, you can do:

  `gpg --armor --export _your@email.address_`

  This will generate a nicely-formatted "ASCII armored" version of your
  public key which is suitable for e-mailing.  "ASCII armor" is just a way of
  turning raw binary data (which will probably get corrupted if you try to
  send it through most e-mail programs) into a format using only limited
  ASCII characters, line-wrapped, with appropriate headers, and suitable for
  e-mailing.  (Hint:  It'll look something like my public key at the top of
  the page.)

  Note that the lines that begin

  `-----BEGIN PGP PUBLIC KEY BLOCK----`

  and end with

  `-----END PGP PUBLIC KEY BLOCK----`

  _are_ a necessary part of the message.  Don't forget to include
  them!

  Once you have this ASCII-armored public key, you can manually paste it into
  a form at a public key server like [pgp.mit.edu](http://pgp.mit.edu/)

  Again, just because someone seems to have sent you their public key,
  there's no reason to trust that it's from that person unless you have
  validated it with them using the instructions in the [Procedure for Verification](https://futureboy.us/pgp.html#ProcedureForVerification) section
  above.  Make sure you verify any keys before trusting them!

  ### <a name="UploadingViaGPG">Uploading a Public Key via GPG</a>

  One way to publish your key to a keyserver is the manual approach from the
  previous section:  export an ASCII-armored key and manually paste it in to
  a form like the one at [pgp.mit.edu](http://pgp.mit.edu/).

  The other way is to let your `gpg` program upload the key.  You
  can't do this by specifying the e-mail address; you need to specify the
  public key's hexadecimal ID number.  So how do you find this for the key
  you want to upload?

  `gpg --list-keys _your@email.address_`

  `
  pub   4096R/**ED873D23** 2014-07-22

  uid                  Alan Eliasen <eliasen@mindspring.com<

  sub   4096R/5314E70B 2014-07-22

  `

  In the above, my public key id is displayed on a line that says
  `pub` and contains an 8-character hexadecimal code
  (`ED873D23` in the sample above.)  You will need to know this
  code to upload to the server.

  `gpg --send-keys _keyID_`

  `gpg: sending key ED873D23 to hkp server subkeys.pgp.net`

  You may want/need to insert `--keyserver pgp.mit.edu` as options
  to the above if you want a specific keyserver.  (These options have to go
  _before_ commands like `--send-keys`.  Again, most
  keyservers mirror each other, but it will take time for keys to propagate
  across all servers.

  Note that after you've signed _someone else's_ public key,
  indicating that you've verified their key and identity and vouch that the
  key is theirs, you can use this same procedure to upload your signed
  version of their public key to a keyserver, so people can see you've
  vouched for them.  See the [Web of Trust](https://futureboy.us/pgp.html#WebOfTrust) section
  below for more information about this.

  ### <a name="UploadingViaEnigmail">Uploading a Public Key via Enigmail</a>

  Again, in Enigmail, everything you do with keys is accessed through the
  menu item `Enigmail | Key Management`.  Search for the key you
  want to upload, right-click it, and you have the option to upload it to a
  keyserver.  Couldn't be easier!  You still have the same responsibilities
  to be very careful with signing other people's keys, though.

  ## <a name="ManuallyDecrypting">Manually Decrypting</a>

  So you've received a file or message encrypted with GPG, but you don't have
  a fancy e-mail plugin to help you decode it.  So how do you decode
  manually?  Simple.  From the command-line, if you just run `gpg`
  it will prompt you for input:

  `gpg`

  `gpg: Go ahead and type your message ...`

  From there, you can just cut-and-paste your message directly into gpg, and
  it will decrypt it, or import keys, or whatever is appropriate to the
  message.  When you're done pasting, you may need to send your operating
  system's "end-of-file" character.  This is `Ctrl-D` in most
  Unixlike systems and `Ctrl-Z` in Windows-like systems.

  If the encrypted data is in a file, you can automatically process it by
  just passing the filename to gpg on the command-line.

  `gpg _myfilename_`

  The gpg executable will generally just do the right thing with it,
  prompting you for passwords when necessary, saving output files, etc.

  **<a name="Shred">Warning:</a>** When gpg encrypts or decrypts a file,
  it usually _leaves the original file intact!_.  You must remember to
  delete the original file yourself, securely if possible.  In Linux, you can
  use `shred -u` (shred just overwrites by default; the
  `-u` is necessary to delete the file afterward) or
  `wipe` commands to delete securely.  On
  Windows, [sdelete](http://technet.microsoft.com/en-us/sysinternals/bb897443.aspx)
  works well.  (Although secure deleting isn't guaranteed to work on solid
  state drives or flash drives due to wear-leveling algorithms.  If you're
  using one of these, and want to securely delete, you have to write
  over _all your free space_ with a tool like `wipe`
  or `sdelete`) However, don't believe the hype that you need to
  do dozens of overwrite
  steps.  [This
  is very likely urban legend, or marketing lies.](http://www.nber.org/sys-admin/overwritten-data-gutmann.html)  One overwrite is
  probably plenty.

  ## <a name="ManuallyEncrypting">Manually Encrypting</a>

  ### <a name="EncryptingForEmail">Encrypting for E-mail</a>

  If you don't have a fancy e-mail plugin that helps you encrypt your
  messages, it's easy enough to do from the command line.  You'll need to
  save your message to a file.

  `gpg --encrypt --sign --armor -r _recipient@email_ -r
  _your@email.com_ _filename_`

  There are several important things in this command.

  *   `--encrypt` tells gpg to encrypt the message using
  public-key encryption.

  *   `--sign` adds a digital signature that lets you guarantee
  that the message was generated by you and was not corrupted nor modified in
  transmission.  This is theoretically optional, but see the [Signing Messages](https://futureboy.us/pgp.html#SigningMessages) section below for why this
  is very important.

  *   `--armor` wraps your output in plaintext "ASCII
  armor". "ASCII armor" is just a way of turning raw binary data (which will
  probably get corrupted if you try to send it through most e-mail programs)
  into a format using only limited ASCII characters, line-wrapped, with
  appropriate headers, and suitable for e-mailing.  This is necessary if
  you're pasting this into the body of an e-mail, or usenet posting, or forum
  posting, etc.

  *   `-r _recipient_` Specifies recipients of the message.
  You must already have imported the public keys of the recipients.  You can
  specify multiple recipients.  If you don't specify recipients on the
  command-line, gpg will prompt you to enter them interactively.  These
  recipients can also be key IDs.

  **Warning!  This is important and interesting!** Note that in the
  example above, _your_ email address is specified as one of the
  recipients.  If you do not explicitly add _your own_ address to
  the list of recipients, _you will not be able to decrypt the
  message!_ That is interesting and important and awesome.  You may
  want to write something and send it to someone _that you cannot ever
  possibly be compelled to decrypt!_ It will be impossible for you to
  decrypt, even though you wrote it and encrypted it!  That is cool.
  Read the [Why Public-Key Encryption is Cool](https://futureboy.us/pgp.html#Cool) section
  below for more about why public-key encryption is cool.

  *   `_filename_` is the filename of the file you're
  encrypting.  This is not strictly required.  If you don't specify a
  filename, GPG will listen for input, and you can type a message directly or
  cut and paste it in.  This is awkward, though.  When you're done pasting,
  you may need to send your operating system's "end-of-file" character.  This
  is `Ctrl-D` in most Unixlike systems and `Ctrl-Z` in
  Windows-like systems.

  **Warning:** (I'm repeating this again.)  When gpg encrypts or decrypts
  a file, it usually _leaves the original file intact!_.  You must
  remember to delete the original file yourself, securely if possible. See
  the [warning above](https://futureboy.us/pgp.html#Shred) for more details on how to do this.

  ### <a name="EncryptingFiles">Encrypting Files</a>

  GPG is not just for e-mail!  You may want to use it to protect your
  sensitive files also.  Encrypting your files is just about like encrypting
  an e-mail.  The simplest command line is:

  `gpg --encrypt _filename_`

  This will prompt you for the recipients (which should include your own
  e-mail address so you can decrypt it!)

  A more complete command-line might look like:

  `gpg --encrypt --sign -r _your@email.com_ _filename_`

  Some interesting things to note and optional arguments:

  *   `--encrypt` tells gpg to encrypt the message using
  public-key encryption.  (See the [Symmetric
  Encryption/Decryption](https://futureboy.us/pgp.html#Symmetric) section below for alternate ways to encrypt a
  file with a simple password and no public keys.)

  *   `--sign` adds a digital signature that lets you guarantee
  that the message was generated by you and was not corrupted nor modified in
  transmission.  This is theoretically optional, but very important.

  Think about it: how do you know that someone didn't replace your
  encrypted file with a different one?  By digitally signing the
  message, you can get a strong guarantee that you're the one who encrypted
  the message and that it hasn't been tampered with or corrupted.  See [Signing Messages](https://futureboy.us/pgp.html#SigningMessages) section below for more on
  digital signatures.

  *   `--armor` (optional, probably unnecessary) wraps your output
  in plaintext "ASCII armor". "ASCII armor" is just a way of turning raw
  binary data (which will probably get corrupted if you try to send it
  through most e-mail programs) into a format using only limited ASCII
  characters, line-wrapped, with appropriate headers, and suitable for
  e-mailing.  This is necessary if you're pasting this into the body of an
  e-mail, or usenet posting, or forum posting, etc.  Note that this will
  increase the size of your message on disk.

  *   `--output _filename_` (optional) specify the output file.

  *   `-r _recipient_` Specifies recipients of the message.
  Can also be written `--recipient`.  You must already have
  imported the public keys of the recipients.  You can specify multiple
  recipients with multiple `-r` arguments.  If you don't specify
  recipients on the command-line, gpg will prompt you to enter them
  interactively.  These recipients can also be key IDs.

  **Warning!  This is important and interesting!** Note that in the
  example above, _your_ email address is specified as one of the
  recipients.  If you do not explicitly add _your own_ address to
  the list of recipients, _you will not be able to decrypt the
  file!_  That is interesting and important and awesome.  You may
  want to create a file for another person _that you cannot ever
  possibly be compelled to decrypt!_  It will be impossible for you to
  decrypt, even though you wrote it and encrypted it!  That is cool.  Read
  the [Why Public-Key Encryption is Cool](https://futureboy.us/pgp.html#Cool) section below
  for more about why public-key encryption is cool.

  *   `_filename_` is the filename of the file you're
  encrypting.  This is not strictly required.  If you don't specify a
  filename, GPG will listen for input, and you can type a message directly or
  cut and paste it in.  This is awkward, though.  When you're done pasting,
  you may need to send your operating system's "end-of-file" character.  This
  is `Ctrl-D` in most Unixlike systems and `Ctrl-Z` in
  Windows-like systems.

  **Warning:** (I'm repeating this again.)  When gpg encrypts or decrypts
  a file, it usually _leaves the original file intact!_.  You must
  remember to delete the original file yourself, securely if possible. See
  the [warning above](https://futureboy.us/pgp.html#Shred) for more details on how to do this.

  ## <a name="Attachments">Attachments and PGP/MIME</a>

  What do you do if you want to send an encrypted file attachment in an
  e-mail?

  There is a standard called PGP/MIME that try to standardize the handling of
  encrypted attchments.  You cannot be sure that your recipient's e-mail
  client will be able to handle them, so I strongly recommend _never using
  them_.  Enigmail doesn't even handle its _own_ attachments that
  it creates well.

  Examples of situations that will cause PGP/MIME or S/MIME attachments to
  fail or be lost:

  *   Most web-based email services.
  *   Most phone- and tablet-based email software.
  *   List servers or remailers that strip attachments.
  *   List servers that just don't handle all attachments perfectly.
  *   Corporate firewalls that remove attachments.
  *   Overeager malware scanners.
  *   Simple, secure e-mail clients that can only display plaintext.
  *   Not-yet-ready-for-attachments e-mail tools like Enigmail itself.

  I strongly recommend _always_ sending encrypted messages or
  encrypted attachments as ASCII-armored OpenPGP blocks directly in the body
  of an e-mail.  This will ensure that any e-mail program will still be able
  to handle them.

  You can hand-encrypt any attachments using:

  `gpg --armor --encrypt --sign -r _your@email.com_
  -r _recipient@email.com_ _filename_`

  as outlined in the [Encrypting Files](https://futureboy.us/pgp.html#EncryptingFiles) section
  above.  Then just paste the results into the body of your e-mail.  You can
  paste in multiple attachments this way, too.

  ### <a name="AttachmentsInEnigmail">Attachments in Enigmail</a>

  Enigmail is buggy and insecure when sending and receiving encrypted
  attachments or PGP/MIME.  _I don't recommend it at the moment.  In fact,
  the bugs are so severe that Enigmail's behavior may allow others to obtain
  your entire secret key._

  Enigmail fails, for instance, to import a public key or other attachments
  that it attached itself.  You can test this by sending encrypted
  attachments and public keys to yourself.

  Enigmail is also insecure in handling PGP/MIME (and possibly S/MIME)
  attachments because it appears to always automatically and silently decrypt
  the message for you, _even if you have Enigmail configured to not
  decrypt by default!_ This is very bad if someone's looking over your
  shoulder, or detecting emanations from your monitor (e.g TEMPEST) or doing
  [sound-based attacks](http://www.tau.ac.il/~tromer/acoustic/).
  You may not even notice that the message was encrypted, and forget to
  encrypt your reply, or forget to verify the signature, or do something that
  compromises your security. It turns out that this is a known bug [Enigmail Bug #226](http://sourceforge.net/p/enigmail/bugs/226/)
  which the developers have inexplicably labeled as "Minor."  Augh.  They are
  obviously oblivious to the literature.  In fact, the _creators_ of
  the RSA algorithm have explicitly stated in one of the most
  widely-circulated papers on GPG that this particular bug in Enigmail is
  what lets them completely steal your private key, using nothing but a
  microphone near your computer or an electrical connection (e.g. touching
  your skin or monitoring your computer's electricity usage) while you
  receive an e-mail!

  Even if you fix the problem above, Enigmail is _still_ buggy when
  handling PGP/MIME messages, as it will try to auto-save your messages as
  you write them, which can pop up a dialog asking you to choose recipients
  to encrypt to while you're typing, causing you to randomly select
  recipients as you type.  It's just totally broken and annoying.

  For these reasons, I recommend using the manual procedure above, but here
  are some tips for using Enigmail if you're lazy and don't care if your
  attachments get lost or are unreadable by your recipient.

  #### <a name="DisablingPGPMIME">Disabling PGP/MIME in Enigmail</a>

  The place to turn off PGP/MIME in Thunderbird/Enigmail has been continually
  changing, but now it's currently hidden under each e-mail account on the
  (usually) left-hand side of your screen under `OpenPGP Security`
  where the option `Use PGP/MIME by default` should be unchecked.
  Here's the [current
  screenshot from the Enigmail project](https://www.enigmail.net/documentation/per-account.php) showing where PGP/MIME should be
  turned off for each account.

  When sending encrypted e-mails with attachments in Enigmail, you will be
  presented with a dialog asking how you want files to be attached:

  ![Enigmail file
  attachment prompt.  Choose the option for using inline PGP.](https://futureboy.us/images/smime.png)

  Choose the option "Encrypt/sign each attachment separately and send the
  message using inline PGP."  However, this doesn't even do the right thing.
  Its results are unfortunately _not_ identical to the recommended
  "hand-encrypt and paste" technique described above.  It currently still
  adds multiple attachments, which may get stripped out by mail filters or
  lost in web-based e-mail clients.  Enigmail is then often unable to open
  these attachments reliably.  It certainly can't open public keys that it
  attaches.  Really, just don't use Enigmail for attachments right now.
  Hand-encrypt them as shown in the previous section.  It'll simply work
  better for more people.

  In short, all encrypted communications will be accessible to the most
  people if you always just use ASCII-armored OpenPGP blocks in the body of a
  plaintext message.

  ## <a name="SigningMessages">Signing Messages</a>

  In addition to encryption, gpg allows you to digitally "sign" messages,
  which has multiple benefits:

  *   It lets you ensure that a message has not been corrupted nor modified
  in transmission.

  *   It allows someone to verify that _you_ signed it.  (To be more
  precise, to verify that the signer of the message used your secret key,
  given that they've verified your public key with you, and that your secret
  key hasn't been compromised.)

  You should always sign your encrypted messages.  Think about it.
  _Everyone_ potentially has your public key.  That's expected.
  _Anyone_ can encrypt a message to you using your public key, and
  pretend that it's from someone you know.  (It's easy to spoof e-mails, but
  that's another discussion.)  _Only if you verify (via the digital
  signature) that the message was signed by someone whose key you have
  verified, can you trust the communication._

  _Corollary:_  You should actively distrust unsigned encrypted
  communications.  If someone's trying to impersonate your friends, they'll
  just conveniently "forget" to sign their messages.

  A signed message gives a mathematically _very_ strong certainty
  that the message was signed by you.

  In your e-mail client, always choose to sign _and_ encrypt a
  message.  Below are some ways to sign messages manually.

  ### <a name="EnigmailAutomaticSigning">Configuring Enigmail for Automatic Signing</a>

  By default, Enigmail does _not_ automatically sign encrypted
  e-mails.  This is a bad choice, in my opinion (stated in the section above.)

  You can, however, make Enigmail automatically sign all encrypted mails.
  The setting is _very_ hard to find, though.  You need to do the
  following:

  *   The first thing you want to do in Enigmail is to make all of its settings
  visible.  If you haven't done so already, you can do this from the menu
  items `Enigmail | Preferences | Display Expert Settings`.  The
  basic settings are inadequate.

  *   Start to compose a new e-mail.  That is, click the "Write" button.

  *   In the "Write" window, choose the _top_  menubar item
  `Enigmail | Default Composition Options | Signing/Encryption
  Options`.

  *   Check the `Sign encrypted messages by default` box.

  *   Click OK.

  ### <a name="SigningPlaintext">Signing a Plaintext Message</a>

  Sometimes you just want to sign an unencrypted message to make it clear
  that you produced it and that it hasn't been tampered with nor corrupted in
  transmission.  For example:

  *   Sending an important vote.

  *   Important business communications.

  *   Maybe you're mailing a URL that looks suspicious and spammy, and your
  recipient wants to validate that it's actually from you and not from a
  spammer or a virus.  (Saying "this is really from me" in the e-mail is
  not good enough!)

  *   Being very certain that the message is not corrupted in transmission.

  *   Allowing recipients to verify that data comes from you and is valid.
  For example, a school could prove that test scores came from them and
  were not tampered with.  (Institutions should use this more!)

  The `--clearsign` option will wrap the message in an
  ASCII-armored signature but will not otherwise modify its contents.  This
  allows even the losers who don't use gpg to read the body of the message,
  but allows gpg users to verify that you wrote it and that the message
  wasn't changed.

  `gpg --clearsign _filename_`

  <pre>-----BEGIN PGP SIGNED MESSAGE-----
    Hash: SHA256

    I vote YES on this important measure.

    -----BEGIN PGP SIGNATURE-----
    Version: GnuPG v1
    Comment: See Alan's GPG guide at https://futureboy.us/pgp.html

    iQIcBAEBCAAGBQJT3MFeAAoJEF8rR1bthz0jslMP/RMRODVKLmLwZ3sMR62COGc/
    0yQSh3c37qkkVjD0RvgdziHuCSSYelhNl7UMQofpdLonnJgPW3svlftE3Gn11JLp
    ZYv2iMwCzwyM2eLYpSQoJBNnGZzQDGnZRBkFOwdkkohUSBjhPjiszYw3KwnpsuxG
    I+m81IMJATR0wOylLumVdjbvS1/f9bOzBRvhgu2HS54lfPnl162RRZpycrrb5IOi
    07QWIlUGVUdAxFUq4Jlm99KB17lQhri3zm6m7O5k0faD3IKFRTQGKseq7j88pRs6
    j85v/cc35CHW9+66jcz7Y3UtOIj3gqDQd/Wj05YP01QSwSCuuVAezvXngljF8fLP
    OKQhFpLoLnWvDPgX3nKwGbX52qZwLGN0bZduhOmMPYwKAEFAYDOOW7q+i/dyz5xT
    od54j32QiNkSqDCVkvOT6dKiCdCa8GvtwwXPKa9X7+VZB2xYeJorJiaIesD7wyVN
    CQDx11uMGMkpZ/BmCIA5mDIkDnUTIxHxNFpn2kS6nHJqmJ/LleTpAKLhPWuY1U28
    YVraBzmAZ/Wj2Frq0utPi4cFf5r3x9jXIzie4fYrUjMKCN+CNfLL15Py/z9OY1ux
    vvYdMiLAzL1Ujvjpyw7sCdc2KnbXaM9jmbBGjmVCMX/wGcGKT6cIxYnkR4NOW62L
    jaBgelaHIL5kZ+E/kpS6
    =wh+e
    -----END PGP SIGNATURE-----
  </pre>

  ### <a name="VerifyingSignatures">Verifying Signatures</a>

  People who have verified your public key can verify messages that you've
  signed by passing the output back into gpg:

  `gpg --verify vote.txt.asc`

  `
  gpg: Signature made Sat 02 Aug 2014 04:45:50 AM MDT using RSA key ID ED873D23

  gpg: Good signature from "Alan Eliasen <eliasen@mindspring.com>"
  `

  If they haven't verified and signed your public key, then they will be
  warned that the key is untrusted.  This means that all that they can tell
  for certain is that the message wasn't corrupted in transmission, _but it
  really could have been written by anyone!_  Beware "Untrusted good
  signature!"  It means that the signature is by someone whose fingerprint
  you haven't verified.

  ### <a name="DetachedSignature">Detached Signature</a>

  Sometimes you want to sign a file, but without modifying it like the
  `--clearsign` option above does, because people would need to
  edit the file or use gpg to get at the contents.

  Say, you're sending an executable file to someone.  You don't want to
  tamper with the executable file, but executable files are scary and
  potentially very dangerous.  So how can you guarantee to the recipient
  that nobody has tampered with the file and that it actually came from you?
  By creating a "detached signature" which is a separate file that contains
  a signature for the specified file.  This is achieved through the
  `--detach-sign` command:

  `gpg --detach-sign _filename_`

  Then you ship the signature file along with the original file.  The
  recipient can verify that you signed the file and that it has not been
  modified with the `--verify` command:

  `gpg --verify _filename.sig_`

  `
  gpg: Signature made Sat 02 Aug 2014 04:45:50 AM MDT using RSA key ID ED873D23

  gpg: Good signature from "Alan Eliasen <eliasen@mindspring.com>"
  `

  ### <a name="ProvingAnonymous">Proving You Wrote Something but Remaining Temporarily Anonymous</a>

  Let's say you found out that a huge company (we'll call them Mapple) wrote
  a really crappy incompetent insecure website that leaked a lot of their
  customers' information that anyone could access trivially by adding 1 to a
  number.

  Now, you're not sure if the company is awesome and honest and will pay you
  a handsome bug bounty for pointing out their incompetent security hole and
  helping them protect their customers' information, or if they are
  psychotic morons who will claim _post-facto_ that your access of
  information they intentionally published on a public webserver without any
  access control was "unauthorized" and have you charged under the insanely
  incompetently-written and outdated Computer Fraud and Abuse Act ([CFAA](https://www.eff.org/issues/cfaa)).

  So, how do you report this anonymously?  Well, one very strong way would be
  to generate a new keypair without your name on it, publish that public key,
  and sign all your messages with the corresponding secret key.  This lets
  you do a few things:

  *   You can prove that all subsequent messages signed with the same key
  are from the same person, even if you jump to different e-mail addresses
  or communication channels.

  *   If they decide to be honest and offer you a bounty for your services
  to them and their customers, you can prove in the future that you're the
  person in possession of the corresponding secret key that signed the
  messages, for example, by decrypting something sent to you encrypted with
  your public key.  Nobody else would be able to falsely claim that they're
  the submitter without verifying that they have the corresponding secret
  key.

  *   If they are evil about it, you can remain anonymous to them.  If
  you want to prove to others that you made the disclosure, you can, by
  signing a message with the same secret key or decrypting information sent
  to you that was encrypted with your public key (by using your secret key.)

  (This is a mathematically super-strong version of the old trick of ripping
  a dollar bill in half, and sending half of it to someone.  If they want to
  verify your identity, only you will have the other half of the bill.  A
  dollar bill, with distinctive tearing pattern and matching serial numbers,
  is hard to forge.)

  ## <a name="UpdatingKeys">Updating Keys</a>

  People are constantly updating their keys for various reasons:

  *   Keys get compromised or lost and they are revoked.
  *   Keys are signed by more people, building a [Web of
  Trust](https://futureboy.us/pgp.html#WebOfTrust).
  *   Users change the encryption algorithms they prefer.  (See the [Using Stronger Algorithms](https://futureboy.us/pgp.html#StrongerAlgorithms) section for more
  about this.)

  Updates to keys can be published to public key servers, including new
  signatures.  You can periodically update your keys by using

  `gpg --refresh-keys`

  This lets you ensure that the keys you're using haven't been revoked.  You
  might even find that more people have signed your public key.  (And they
  better have validated your key fingerprint and your identity using the [verification procedure](https://futureboy.us/pgp.html#ProcedureForVerification) outlined above,
  or they can't be trusted to sign keys properly and you should assign them a
  low trust rating!)

  Note that other people can sign _your_ public key and upload the
  signed key to a public webserver!  So you might even find that your own key
  has been updated!

  ### <a name="UpdatingKeysEnigmail">Updating Keys in Enigmail</a>

  Enigmail can update all of the keys in your keyring from a public key
  server.  The way to trigger this is from the menu items:
  `Enigmail` | `Key Management` | `Keyserver`
  | `Refresh all Public Keys`.  Again, I might suggest that
  `pgp.mit.edu` has been a reliable keyserver for me.

  ### <a name="ListingKeys">Listing Your Keys</a>

  You can get a list of the keys on your keyring and their corresponding key
  IDs with:

  `gpg --list-keys`

  If you enter part of the name or e-mail address or key ID as the last
  argument on the command-line, then only keys that match that pattern will
  be listed.

  `gpg --list-keys Alan`

  ### <a name="WhoSigned">Who Signed My Key?</a>

  Now that you've updated keys from a keyserver, you might want to see who
  has signed your key.  After all, _anyone_ can sign _any_ key
  and re-upload that key to a key server.  You can see the signatures with
  the `--list-sigs` command to gpg:

  `gpg --list-sigs _your@email.address_`

  In Enigmail, you can see the signatures for a key by going to `Enigmail
  | Key Management`, searching for a key, right-clicking on that key,
  and then choosing `View Signatures`.

  Or you can browse your key on a public keyserver, like [pgp.mit.edu](http://pgp.mit.edu/).  This is advantageous because
  if you haven't imported someone's key yet, they will just show up as a key
  ID number.

  Again, if someone signed your key without validating the fingerprint with
  you, they are actively damaging the web of trust.  You should import their
  public key just so you can tell your software to actively distrust it as
  outlined in the [Signing a Key](https://futureboy.us/pgp.html#SigningAKey) section.

  (After I published this document, an out-of-control signer whom I've never
  met signed my key and published the changes to a public website.  I had to
  download his public key so I could tell gpg to actively distrust his
  signatures!)

  ## <a name="WebOfTrust">Building a Web of Trust</a>

  In the examples above, I stress the importance of _verifying_
  people's public keys with them.  But sometimes you can't do that
  directly.  So how can you verify someone else's public key?

  Let's say I want to talk to Bob.  I've downloaded a public key with his
  name from a keyserver, but I can't be sure that key belongs to him.  I
  could maybe call him on the phone and verify his key that way, but I don't
  know his voice, and I don't have his phone number.  Or maybe he's even
  under duress.

  Luckily, my friend Alice has signed his public key.  I trust Alice to have
  verified his key properly.  I have validated and trusted Alice's public
  key personally.  Thus I have a good reason to believe that Bob's key
  really belongs to him.

  This is why it's important to validate other people's keys very carefully
  and to build a web of trust--so you can communicate with people whose keys
  you can't personally verify.

  See the [Signing a Key](https://futureboy.us/pgp.html#SigningAKey) section above to see how
  to sign someone else's key and upload it to a keyserver.

  Conversely, you may _not_ want to publicly sign the keys of people
  you communicate with.  You may not want others to know who you communicate
  with.  You may have more than one keypair, and use them selectively for
  communications with a single person once they've demonstrated strong
  cryptographic practices.

  This is serious
  business.  [An
  example from Syria](http://www.cjr.org/feature/the_spy_who_came_in_from_the_c.php?page=all) shows how people die when others don't protect
  their communications.

  If you don't want anyone to be able to analyze who you're talking to, even
  by traffic analysis of key IDs, you can
  specify [hidden recipients](https://futureboy.us/pgp.html#HiddenRecipients) in your
  messages.

  ## <a name="GoodPractices">Good Encryption Practices</a>

  By using encryption improperly, you can make your encrypted communications
  easier to break.  Some of the tips here are speculative and may not apply
  to all cryptographic algorithms, but many cryptographic algorithms are
  subject to common types of attacks.  These tips will help mitigate those
  potential weaknesses if algorithms are found to be vulnerable to these
  types of attacks.

  _TODO:  Improve ALL THE THINGS._  [Send me more examples of good and bad
  cryptographic practice, and ciphers that have been broken by poor
  cryptographic practice.](mailto:eliasen@mindspring.com)

  *   **Don't be predictable.**  This is the way that much crypto has
  historically been broken--by knowing words or phrases that are likely to
  occur in the message.  This is known as
  a ["known-plaintext"](https://en.wikipedia.org/wiki/Known-plaintext_attack)
  attack.  For example, the WWII German Enigma machine codes were
  partially broken because people would end with expected phrases like "Heil
  Hitler!" or from spelling out numbers.  (Looking for the number "eins",
  (1), the most common number, was a useful tactic in breaking Enigma.)

  You think this is academic and known-plaintext attacks can't happen?
  Well, take a look at [this
  recent break on the widely-used RC4 cipher](http://sac2013.irmacs.sfu.ca/slides/s9.pdf).  (It's used in SSL/TLS
  and in WEP/WPA in wi-fi.)  It was found that if you knew a small amount
  of plaintext, you could recover the rest of the message (given a fairly
  large amount of encrypted communications, to be sure.)  With as little as
  6 bytes of plaintext, and a large number of communications, the rest of
  the message could be decrypted with high probability.  (The more bytes
  are known, the easier it is to break.) Also, keep in mind that breaks in
  cryptographic algorithms only get worse.

  *   **Don't be polite.** As a corollary of the above, don't start and
  end your message with predictable phrases or pleasantries.

  *   **Don't send HTML-formatted encrypted emails.** There's a large
  amount of predictable boilerplate in HTML.

  *   **No signatures!** As a corollary of the above, when sending
  encrypted messages, don't include your usual .sig file with your name,
  e-mail address, phone number, password, website, company policy, etc.

  This doesn't mean "no cryptographic signatures!"  You still want
  cryptographically strong signatures like the kind you get with
  `--sign`.  Smart e-mail add-ons like Thunderbird with Enigmail
  can suppress your signature when using encryption.  Or you should encrypt
  just the meat of your email (and not the signature) if you _need_
  that silly signature.

  *   **Don't quote previously-encrypted text.**  When replying to an
  encrypted message, _don't quote the original text._  Again,
  having large stretches of expected text has been the downfall of many
  cryptographic algorithms.

  *   **Don't encrypt the same message multiple times.**  Some codes have
  weaknesses that if the same plaintext message is encoded several times
  (say, to several different people, or to the same person multiple
  times,) then more information can be derived about the contents or the
  key.  If someone isn't able to read your encrypted message, don't send
  it again.  After all, they're not following good cryptographic practice
  if they can't read it, and you should limit encrypted communications
  with them.  Or, if you must send it again, alter it as much as possible
  before encrypting and sending it again.  If encrypting the same message
  to multiple people, encrypt to all of them at once (assuming you want
  them to know who you're communicating with.  They will at least see the
  key ID numbers.)

  *   **Don't have encrypted and unencrypted versions of the same
  information.**  As [noted above](https://futureboy.us/pgp.html#Shred), gpg
  does _not_ automatically delete the plaintext version of a file
  when you encrypt it!  Read that section on securely deleting files if
  possible.

  *   **Garbage is good.**  One of the hard problems in cryptography is
  identifying when a message has been successfully decrypted.  How do you
  know?  When it all comes out as mostly alphanumeric characters?  When
  its word frequency looks like English?  Make it hard for the bad guys.
  Jam in a bunch of random bytes into your message if you can.  It'll make
  it harder to even detect the fact that the message was decrypted
  properly.  Send your friends encrypted random bytes every day just for
  fun because screw the surveillance state we live in!  If everyone did
  this, it would be utterly prohibitive to try and decrypt all of the
  random data flying around.

  *   **If it's received encrypted, store it encrypted.** Some e-mailer
  plugins will offer to decrypt messages and store the decrypted versions in
  your mail folder.  Don't do this.  It allows someone to mount a
  chosen-plaintext attack on you just by sending you an encrypted message.
  Yes, it will make your messages impossible to search for content.  But
  that's good.

  *   **Don't encrypt stuff from untrusted sources.**  There is a class
  of attacks called
  a ["chosen-plaintext"](https://en.wikipedia.org/wiki/Chosen-plaintext_attack)
  attack.  Some encryption algorithms can be weakened or completely
  defeated if the attacker is allowed to choose the text that you are
  going to encrypt with your key.  Always refuse to encrypt something
  specific that a third party asks you to encrypt, especially if it's
  lengthy.

  *   **Hide your encryption entirely!** There's a branch of cryptography
  called "steganography" which hides secret communications in innocuous
  places that are very hard to detect.  For example, by slightly modifying
  the least-significant-bits in the pixels of a JPEG image, you can hide
  encrypted messages in pictures of kittens!  Or, you can hide them by
  adding slight, undetectable noise to audio files.

  It becomes _very_ difficult and expensive to determine that a
  particular image even contains steganographic content.  That's the
  best way to hide your information, especially as the NSA has decided
  that using cryptography to protect your privacy is probable cause that
  you're a terrorist, and they allow themselves to keep encrypted
  content "for as long as necessary" to break it.

  I have built some web-based [Steganographic
  Tools](https://futureboy.us/stegano/) that let you experiment with steganography from your
  browser!  If you want to be more secure, of course, you'll run the
  steganography tools on your own machine.  That page tells you more
  about the `steghide` program.
  (Hint: in Fedora it's `yum install steghide` )

  ## <a name="Symmetric">Symmetric Encryption/Decryption</a>

  Sometimes you don't want to use public key encryption.  You can use
  old-fashioned "symmetrical" encryption where everyone shares a common
  password.  In gpg, you do this by using `--symmetric` instead
  of `--encrypt`:

  `gpg --symmetric _filename_`

  gpg will then prompt you for a password.

  **Warning:** (I'm repeating this again.)  When gpg encrypts or decrypts
  a file, it usually _leaves the original file intact!_.  You must
  remember to delete the original file yourself, securely if possible. See
  the [warning above](https://futureboy.us/pgp.html#Shred) for more details on how to do this.

  If you want to paste the encrypted file into an e-mail or something, you
  can use the `--armor` option.

  The encrypted file can be decrypted by passing it back into gpg:

  `gpg _filename.gpg_`

  If you want to force the encryption algorithm used, you can add the
  `--cipher-algo _name_` command-line option, for example
  `--cipher-algo AES256` .  The list of available encryption
  algorithms in your version of gpg can be found by running the `gpg
  --version` command.

  Symmetric encryption has its problems.  It doesn't let you simultaneously
  sign the message to indicate that it hasn't been tampered with or replaced
  with another file that someone else generated!  (You can, however, sign it
  manually later using the techniques in the [Signing Messages](https://futureboy.us/pgp.html#SigningMessages) section, but it's
  theoretically possible that an attacker can replace that file in the brief
  time between when you encrypted it and when you signed it.)

  If you use symmetric encryption, you also need to solve the age-old
  problem "how do I communicate the password securely?"

  ## <a name="Cool">Why Public-Key Encryption is Cool</a>

  *   In short, public-key encryption solves the age-old problem "how do I
  communicate a password securely?"  You no longer have to.  You just
  need the other person's public key, which can be published to the world.

  *   You can also encrypt a message _that you can not decrypt!_ This
  may sound silly, but you may want to write something to someone _that
  you cannot ever possibly be compelled to decrypt!_ It will be
  impossible for you to decrypt, even though you wrote it and encrypted it
  and even if you have the file in your possession and even if you have all
  your secret keys and you know all of your own passwords and have them
  written down!  That is cool.  (You can smile serenely while they're
  beating you with a rubber hose, knowing that you can't endanger the lives
  of your sources, nor give up your rights, even if you felt like that might
  be entertaining for a change.)  You can see how to do this physically in
  the [Encrypting Messages You Can't Decrypt](https://futureboy.us/pgp.html#OneWayEncryption)
  section.

  This actually has many important and practical uses:

  *   If you're a reporter (or other human) traveling abroad, you can
  encrypt materials using public-key encryption, to someone else's key, but
  _without_ encrypting to your _own_ public key.
  (**Warning**: some tools will encrypt to yourself by default.  Read
  on.)  It's easy to create a message that you can _never possibly_
  decrypt yourself, and cannot possibly be compelled to do so!  Ever!  You
  could encrypt them, say, using only the public key belonging to your
  newspaper's editor or lawyer.  (And if your newspaper's editor and lawyer
  don't have public keys, have them [contact me](mailto:eliasen@mindspring.com) and I will help
  them.  They need to do this.  Now.  Before they kill people.)  You can
  be detained and couldn't ever be compelled to give up the password, as
  _you never had it!_

  You don't have to be in [Syria](http://www.cjr.org/feature/the_spy_who_came_in_from_the_c.php?page=all)
  (although journalists who don't use encryption kill people; read the
  link) or North Korea for this type of Orwellian police state coercion
  to happen.  Even the otherwise-civilized United Kingdom has vile
  horrendous laws [that
  can jail you without trial if you don't give up passwords.](http://www.bbc.co.uk/news/uk-23776243)

  Edward Snowden has also stated that he has in his possession encrypted
  documents that he cannot possibly be compelled to decrypt, even under
  torture.  (But maybe other trusted people potentially can decrypt
  them.)  Public-key encryption is probably what he was hinting at.  Nice
  work.

  Also
  see the [Hidden Recipients](https://futureboy.us/pgp.html#HiddenRecipients) section of
  this document to see how to hide the people to whom you've encrypted.
  That may be _very_ important for journalists or dissidents or
  ordinary people who want to assert their rights to free association.
  It also allows you to post encrypted messages to public forums without
  anyone knowing who you're talking to.

  Also see my [Steganography tools](https://futureboy.us/stegano/) which let
  you hide the fact that any hidden communications are happening at all!
  You can hide secret communications in pictures of kitties.

  *   Let's say you have a web server that collects very sensitive user
  information.  You don't trust the security of the web server, but you have
  to keep the information on that web server for a while before you move it
  elsewhere.  Say, to a computer completely disconnected from the outside
  world.  With public key encryption, you can encrypt information with a
  public key stored on the web server.  However, the secret key would not
  ever be kept on that server!  Even if someone breaks your web server wide
  open and has total access to _every single file_, _and_
  every single algorithm, _and_ the public key, they will still
  _never, ever_ be able to decrypt the private information on the
  server _because the secret key needed to decrypt it is not on the
  server at all!_ [Miracles!](https://www.youtube.com/watch?v=N_2wK4LWvJA)

  *   If you rent space in a server farm, this can prevent malicious
  administrators at the hosting company (who probably hold superuser access
  on your machine, and can read all your files) from being able to do
  anything with your data.  And it keeps your web server administrator or
  database administrator from seeing that sensitive data, _even if they
  have complete access to every file on the computer._

  *   A real-world example of storing sensitive communications: The Federal
  Communication Commission's (FCC's) [Lifeline](http://shns.com/privacy-on-the-line) subsidized
  cell-phone program for low-income people leaked highly sensitive customer
  information for over 170,000 people, including Social Security numbers,
  birth dates, home addresses, and sensitive details about family finances
  from a public web server.  Think about how you could use public-key
  encryption to collect and encrypt this data securely on the webserver,
  and only be able to decrypt it somewhere else much safer.

  Again, see how to do this in the [Encrypting Messages You Can't Decrypt](https://futureboy.us/pgp.html#OneWayEncryption)
  section.

  *   It's easy to revoke access to one member of a group.  If everyone in a
  group shared a password, it would be very difficult to remove one person's
  access.  A different password might have to be created, and that password
  would have to be communicated securely to _all_ other members of a
  group.  Public-key encryption means that you can control exactly who is
  allowed to read future communications.  If you don't want someone to read
  it, just stop encrypting to that person's public key.  Even if they can
  still see your encrypted communications (like on a public mailing list,)
  they will no longer be able to decrypt it.

  ## <a name="TipsAndTricks">Fun Tips and Tricks</a>

  Here are a collection of fun tips and tricks and puzzles for using GPG.
  Please [send me more.](mailto:eliasen@mindspring.com)

  ### <a name="StrongerAlgorithms">Using Stronger Algorithms</a>

  This section is optional but important.

  By default, gpg uses weaker encryption algorithms than it could (especially
  if you generated your keys using an older version of the software.)  This is
  to ensure compatibility with older versions.

  Part of your public key specifies your preferences for the encryption
  algorithms that you want people to use when communicating with you.  These
  are, by default, somewhat weak.  You can view and modify these preferences
  to make your communications stronger.

  To view all of the algorithms supported by your version of gpg, type:

  `gpg --version`

  This will give an output that looks something like this:

  `gpg (GnuPG) 1.4.14

  Copyright (C) 2013 Free Software Foundation, Inc.

  License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>

  This is free software: you are free to change and redistribute it.

  There is NO WARRANTY, to the extent permitted by law.

  Home: ~/.gnupg

  Supported algorithms:

  Pubkey: RSA, RSA-E, RSA-S, ELG-E, DSA

  Cipher: IDEA, 3DES, CAST5, BLOWFISH, AES, AES192, AES256, TWOFISH,

  CAMELLIA128, CAMELLIA192, CAMELLIA256

  Hash: MD5, SHA1, RIPEMD160, SHA256, SHA384, SHA512, SHA224

  Compression: Uncompressed, ZIP, ZLIB, BZIP2

  `

  You can modify your public key's cipher preferences by interactively
  editing your key:

  `gpg --interactive --edit-key _your@email.address_`

  This will display a list of matching public keys.  You may need to enter
  the number of your key in that list so you can edit it.

  _Hint:_ You can always type `help` at the
  `gpg>` prompt to see all available commands.  There's lots of
  fun stuff hidden in here.

  Next, show your current algorithm preferences by typing at the
  `gpg>` prompt:

  <p class="code">
