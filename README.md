# public-gpg
This document will explain how to import my gpg key.

## Importing GPG Public key

The public can be found at http://keys.gnupg.net/pks/lookup?op=get&search=0xBBE9890B714435ED

More convenient you can download the key with:

`wget https://raw.githubusercontent.com/Regamii/public-gpg/master/public.gpg`

To import the downloaded key you can issue the command:

`gpg --import public.gpg`

Now with the key imported signed files can be verified. sample.txt is a file that is
signed. This can be verified using the sample.txt.asc.

Verify the signature of sample.txt:

`gpg --verify sample.txt.asc sample.txt`

The output should show "Good signature" and the Primary key fingerprint should match what's shown below:

To get rid of the warning and thus adding the key to trusted signatures issue this command:

`gpg --fingerprint 3DCFCF94563E1446EBE24F1ABBE9890B714435ED`

My gpg fingerprint is "3DCF CF94 563E 1446 EBE2  4F1A BBE9 890B 7144 35ED"
