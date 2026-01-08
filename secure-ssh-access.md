# Secure SSH Access

**Steps:**

* Log in to the server using your current access method.
* Open the SSH configuration file using a text editor (like `vi` or `nano`):
* `sudo vi /etc/ssh/sshd_config`
* It might be commented out with a `#` (e.g., `#PermitRootLogin yes`).
* Change the line to `no`. Make sure to remove the `#` if it exists.
* Save and close the file. (In `vi`, press `Esc`, type `:wq`, and hit `Enter`).
* Restart the SSH service to apply the changes:
*   `sudo systemctl restart sshd`

