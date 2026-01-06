# Create user with expiry date

Creating a New User with an Expiry Date

Use the `-e` flag followed by the date in YYYY-MM-DD format.

* `sudo useradd -e 2026-12-31 -m -s /bin/bash jim`

Breakdown of the command:

* `-e 2026-12-31`: Sets the account to expire on December 31, 2026.
* `-m`: Creates the home directory for the user.
* `-s /bin/bash`: Sets the default shell (optional, but recommended for interactive users).
* `jim`: The username you are creating.



Either we can use to create user with expiry date by `sudo useradd -r 2026-01-06 username`

