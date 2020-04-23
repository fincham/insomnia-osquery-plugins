# osquery-le-certificates-table

List useful properties of all the currently in-use Let's Encrypt certs (e.g. those which will auto-renew) from /etc/letsencrypt.

```
osquery> select * from le_certificates;
        common_name = acme.example.com
 fingerprint_sha256 = 6417b0e2c7027746840a982f444095389fccf011fd9ee2db02d623f1fcb24135
             serial = 3b1658404bdc32574ef1e67e2a05edc52235
         not_before = 2020-03-02 19:39:12
          not_after = 2020-05-31 19:39:12
  subject_alt_names = acme.example.com
            account = 44bdfc836cfa6ce0f2b662160ee63462
      authenticator = apache
          installer = apache
   manual_auth_hook = none
manual_cleanup_hook = none
         challenges = default
             server = https://acme-v02.api.letsencrypt.org/directory
```
