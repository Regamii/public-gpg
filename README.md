# public-gpg
This document will explain how to import my gpg key. And verifying signatures as
well as adding the fingerprint to trusted fingerprints. The public can be found at
http://keys.gnupg.net/pks/lookup?op=get&search=0xBBE9890B714435ED

More convenient you can download the key with:

`wget https://raw.githubusercontent.com/Regamii/public-gpg/master/public.gpg`

To import the downloaded key you can issue the command:

`gpg --import public.gpg`

Now with the key imported signed files can be verified. sample.txt is a file that is
signed. This can be verified using the sample.txt.asc.

Verify the signature of sample.txt:

`gpg --verify sample.txt.asc`

My gpg fingerprint is "3DCF CF94 563E 1446 EBE2  4F1A BBE9 890B 7144 35ED" The output
should show "Good signature" and the Primary key fingerprint should match what's
shown below:

```
gpg: assuming signed data in 'sample.txt'
gpg: Signature made wo  8 jan 11:49:07 2020 CET
gpg:                using RSA key 3DCFCF94563E1446EBE24F1ABBE9890B714435ED
gpg: Good signature from "Wybren Terpstra <wterpstra@protonmail.com>" [unknown]
gpg: WARNING: This key is not certified with a trusted signature!
gpg:          There is no indication that the signature belongs to the owner.
Primary key fingerprint: 3DCF CF94 563E 1446 EBE2  4F1A BBE9 890B 7144 35ED
```

To get rid of the warning and thus adding the key to trusted signatures issue this command:

`gpg --fingerprint 3DCFCF94563E1446EBE24F1ABBE9890B714435ED`

```
pub   rsa4096 2019-11-11 [SC]
      3DCF CF94 563E 1446 EBE2  4F1A BBE9 890B 7144 35ED
uid           [ unknown] Wybren Terpstra <wterpstra@protonmail.com>
sub   rsa4096 2019-11-11 [E]
```

The above output will verify that indeed the key is added to trusted identities.
