te a key:
gpg --gen-key
**generally you can select the defaults.
</p>

**to export a public key into file public.key:
gpg --export -a "User Name" &gt; _public.key_**
This will create a file called public.key with the ascii representation of the public key for User Name. This is a variation on:
gpg --export
which by itself is basically going to print out a bunch of crap to your screen. I recommend against doing this.
gpg --export -a "User Name"
prints out the public key for User Name to the command line, which is only semi-useful

**to export a private key:
gpg --export-secret-key -a "User Name" &gt; _private.key_**
This will create a file called private.key with the ascii representation of the private key for User Name.
It's pretty much like exporting a public key, but you have to override some default protections. There's a note (*) at the bottom explaining why you may want to do this.

**to import a public key:
gpg --import _public.key_**
This adds the public key in the file "public.key" to your public key ring.

**to import a private key:
gpg --allow-secret-key-import --import _private.key_**
This adds the private key in the file "private.key" to your private key ring. There's a note (*) at the bottom explaining why you may want to do this.

**to delete a public key (from your public key ring):
gpg --delete-key "User Name"
**This removes the public key from your public key ring.
NOTE! If there is a private key on your private key ring associated with this public key, you will get an error! You must delete your private key for this key pair from your private key ring first.

**to delete an private key (a key on your private key ring):
gpg --delete-secret-key "User Name"
**This deletes the secret key from your secret key ring.

**To list the keys in your public key ring:
gpg --list-keys
**

**To list the keys in your secret key ring:
gpg --list-secret-keys
**

**To generate a short list of numbers that you can use via an alternative method to verify a public key, use:
gpg --fingerprint &gt; _fingerprint_
**This creates the file fingerprint with your fingerprint info.

**To encrypt data, use:
gpg -e -u "Sender User Name" -r "Receiver User Name" _somefile_**
There are some useful options here, such as -u <userid> to specify the secret key to be used, and -r <userid> to specify the public key of the recipient.
As an example: gpg -e -u "Charles Lockhart" -r "A Friend" mydata.tar
This should create a file called "mydata.tar.gpg" that contains the encrypted data. I think you specify the senders username so that the recipient can verify that the contents are from that person (using the fingerprint?).
NOTE!: mydata.tar is not removed, you end up with two files, so if you want to have only the encrypted file in existance, you probably have to delete mydata.tar yourself.
An interesting side note, I encrypted the preemptive kernel patch, a file of 55,247 bytes, and ended up with an encrypted file of 15,276 bytes.
</userid></userid>

**To decrypt data, use:
gpg -d _mydata.tar.gpg_
**If you have multiple secret keys, it'll choose the correct one, or output an error if the correct one doesn't exist. You'll be prompted to enter your passphrase. Afterwards there will exist the file "mydata.tar", and the encrypted "original," mydata.tar.gpg.
<p>NOTE: when I originally wrote this cheat sheet, that's how it worked on my system, however it looks now like "gpg -d mydata.tar.gpg" dumps the file contents to standard output. The working alternative (worked on my system, anyway) would be to use "gpg -o outputfile -d encryptedfile.gpg", or using mydata.tar.gpg as an example, I'd run "gpg -o mydata.tar -d mydata.tar.gpg". Alternatively you could run something like "gpg -d mydata.tar.gpg > mydata.tar" and just push the output into a file. Seemed to work either way.

Ok, so what if you're a paranoid bastard and want to encrypt some of your own files, so nobody can break into your computer and get them? Simply encrypt them using yourself as the recipient.

I haven't used the commands:
**gpg --edit-key
gpg --gen-revoke**

*   --gen-revoke creates a revocation certificate, which when distributed to people and keyserve
