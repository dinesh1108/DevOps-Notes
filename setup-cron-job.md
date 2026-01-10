---
description: >-
  Cron Job is simply a scheduled task that your computer runs automatically at a
  specific time.  Think of it like setting an alarm clock for your server, but
  instead of just ringing, this alarm clock wa
---

# Setup Cron Job

Steps:

{% tabs %}
{% tab title="Install and Start Cronie" %}
#### <sup>1. Install the package</sup>

`sudo yum install -y cronie`

#### 2. Start the service

`sudo systemctl start crond`

#### 3. Enable it (optional but good practice)

`sudo systemctl enable crond`
{% endtab %}
{% endtabs %}

**To add the cron there are two ways like :**&#x20;

1. use `crontab -e` this wil only add the cron for current user&#x20;

* Whose crontab? The Current User (the one you are logged in as).
* Behavior: If you are logged in as `steve` and run this, you are editing the schedule for Steve.
* Privileges: Does not require `sudo` (unless you are already root).



2. `sudo crontab -u root -e`

* Whose crontab? The Root User (System Administrator).
* Behavior: Even if you are logged in as `steve`, this command forces the system to edit the schedule for Root.
* Privileges: Requires `sudo` because you are modifying the superuser's schedule.

3. The Schedule (`*/5 * * * *`)

&#x20;  Cron expressions consist of 5 fields representing time.

{% columns %}
{% column %}
Field

Minute

Hour

Day of Month

Month

Day of Week
{% endcolumn %}

{% column %}
Value

\*/5

\*

\*

\*

\*
{% endcolumn %}

{% column valign="middle" %}
Meaning

"Every 5 minutes"

Every hour of day

Every day of day.

Every month of day.

Every day of day.
{% endcolumn %}
{% endcolumns %}



**Key Concept:**

* `*` means "every".
* `*/5` means "every step of 5".
  * If you had written just `5`, it would run only at the 5th minute (e.g., 12:05), once per hour.
  * `*/5` ensures it runs at 12:00, 12:05, 12:10, etc.

#### 1. The Command (`echo hello > /tmp/cron_text`)

* `echo hello`: This prints the word "hello".
* `>`: This is the Redirect operator. It takes the output ("hello") and saves it to a file.
* `/tmp/cron_text`: The file where the text is saved.

2. Important Note on `>` vs `>>`:

* Since you used `>`, the file is overwritten every time the cron runs. The file will only ever contain a single line: "hello".
* If you had used `>>`, it would _append_ a new "hello" every 5 minutes, making the file grow larger and larger.

#### Summary

Every 5 minutes, the system will delete the contents of `/tmp/cron_text` and replace them with the single word "hello".
