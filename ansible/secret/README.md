# Secrets

This directory contains secrets that are required for running Void's infrastructure.

DO NOT CHECK FILES IN THIS DIRECTORY IN WITHOUT ENSURING THEY DO NOT
CONTAIN RESTRICTED INFORMATION.

## Description of Files

  * `buildmaster_github_secret`: Secret that GitHub will send to the
    buildbot to validate the authenticity of its event stream.
  * `buildmaster_github_webhook_password`: Secret that GitHub must
    supply to access the webhook provided by the buildbot.
  * `buildmaster_signing_key`: Master repository signing key for xbps
    to sign the repository files.
  * `buildmaster_signing_keyphrase`: Passphrase for the signing key
    defined above.
  * `buildmaster_slave_reposync_private`: Private half of an SSH
    keypair to be used for retreiving files from remote builders to
    the root mirror.
  * `buildmaster_slave_reposync_public`: Public half of an SSH
    keypair to be used for retreiving files from remote builders to
    the root mirror.
  * `buildmaster_users.yml`: Data file defining the users and their
    credentials to access the buildbot administrative interface.  The
    format is as follows:

    ```yaml
    ---
    buildmaster_users:
      - name: maldridge
        pass: 'password-with-special-chars'
    ```

  * `buildslave_credentials.yml`: Data file defining the machine
    credentials used by the buildbot to log into remote buildbot
    instances and invoke builds on them.  The format is as follows:

    ```yaml
    ---
    buildslave_credentials:
      x86_64-primary: "pure-random-bytes"
    ```

    The identifiers used in the map must match those provided in the
    `group_vars/build.yml` file.

  * `known_hosts`: A known_hosts file in the correct format for SSH
    which contains the host fingerprints for remote build machines.
  * `images.asc`: PGP public key associated with legacy installation
    images (Juan RP).
  * `void_image_key.asc`: PGP public key associated with legacy
    installation images (images@voidlinux.eu).
  * `void_image_key_secret.asc`: PGP private key associated with
    legacy installation images (images@voidlinux.eu).
  * `live_mirror_rsync_passwd`: Single line of ASCII text that will be
    used as the legacy rsync password where legacy passwords are still
    in use.
  * `live_mirror_syncusers.yml`: Data file containing addtional rsync
    users and passwords where rsync credentials are in use.  Format is
    as follows:

    ```yaml
    ---
    live_mirror_syncpasswds:
      vmirror: 'password-with-special-chars'
    ```

  * `popcorn_key`: Single line of ASCII text that will be used as the
    statrepo reset code.
  * `netauth_tls_certificate.pem`: TLS Certificate for NetAuth to
    authenticate the server.
  * `netauth_tls_certificate.key`: Private key for the TLS certificate
    that is used to identify NetAuth's connections.
  * `netauth_token.pem`: RSA Public key used to verify tokens issued by
    the NetAuth server.
  * `netauth_token.key`: RSA Private key used to sign tokens issued by
    the NetAuth server.