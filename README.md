mod_auth_psql_hashed
====================

A module to enable the [Prosody] [1] XMPP/Jabber server to authenticate against hashed passwords stored in a PostgreSQL database. Also supports password changes and user creation/registration over XMPP. Thanks to the mod_auth_sql and mod_auth_wordpress modules from [prosody-modules] [2] for most of the code.

Requirements
============
  * A working Prosody server
  * The [pgcrypto] [3] module (install postgresql-contrib and run `CREATE EXTENSION pgcrypto;`)
  * A database table with columns for username (localpart), domain (domainpart), and hashed password
  * INSERT, UPDATE, and SELECT permissions on the table

Installation
============

Copy to `/usr/lib/prosody/modules`. [Configure the sql block in `prosody.cfg.lua`.] [4] (You don't need to set `storage`.) Optionally, set `psql_users_table`, `psql_localpart_column`, `psql_domainpart_column`, and `psql_password_column` in `prosody.cfg.lua`. (Re)start Prosody.

[1]: https://prosody.im/
[2]: https://code.google.com/p/prosody-modules/
[3]: http://www.postgresql.org/docs/9.1/static/pgcrypto.html
[4]: https://prosody.im/doc/modules/mod_storage_sql
