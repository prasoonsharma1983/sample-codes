# sample-codes
Collection of sample codes

#### Log rotation ############
/var/log/custom.log {
    daily
    rotate 7
    delaycompress
    compress
    notifempty
    missingok
    create 0640 root root
}

**Explanation:**
/var/log/custom.log: Specifies the log file to be rotated.
daily: Rotate the log file every day.
rotate 7: Keep 7 rotated log files before deleting them.
delaycompress: Delay compression of the log files until the next rotation cycle.
compress: Compress the log files after they have been delayed for one rotation cycle.
notifempty: Do not rotate the log file if it is empty.
missingok: Do not issue an error message if the log file is missing.
create 0640 root root: Create a new log file with specified permissions and ownership after rotation.

**Verify the configuration:**

Run the following command to check the configuration for syntax errors:

sudo logrotate -d /etc/logrotate.d/custom
