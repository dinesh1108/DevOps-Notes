# To create Interactive shell for user

To create Interactive shell for user:

* Create user with `adduser -s username /sbin/nologin`&#x20;
* in this adduser is used to create the user
* `-s` stands for shell It tells Linux which program to run immediately after this user logs in.
* `username`  name of the user <mark style="color:$success;">eg: jim</mark>
* `/sbin/nologin`&#x20;
  * This is a special "polite" shell.
  * If a user assigned this shell tries to log in (via SSH or terminal), the system will print a message like _"This account is currently not available"_ and then immediately close the connection.

#### Why use this? (The "Service Account" Use Case)

You generally use this for security when creating system users for software like Nginx, Docker, or Apache.

* The Requirement: The Nginx software needs a user account (often named `nginx`) so it can own specific files and run processes without having full `root` powers.
* The Risk: You don't want a hacker (or a confused employee) to be able to SSH into the server _as_ the `nginx` user.
* The Solution: You give the `nginx` user the `/sbin/nologin` shell. The software can still run in the background as that user, but no human can log in as that user.

