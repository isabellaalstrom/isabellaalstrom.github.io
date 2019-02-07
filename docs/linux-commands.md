### Commands I find useful

#### Check the 200 latest rows in the log (good for knowing why something went wrong)
Increase number for more rows, or skip to get the whole log. If log have rotated since incident add `.1` after syslog.

`sudo tail -n 200 /var/log/syslog`

#### Check ram memory
`free -m`

#### Check how much ram and cpu docker containers use
`sudo docker stats`

#### Subscribe to all messages published on Mosquitto mqtt broker
Replace `\#` with `monitor/#` to follow all messages on "monitor" topic, or other topic you'd like to follow.

`mosquitto_sub -u username -P password -v -t \#`

#### Rotate logs in /var/log
Good if logs grow too big. After running, delete all files with ".1".

`sudo logrotate -f /etc/logrotate.conf`

#### Check what's using cpu

`top`

#### Set up cron jobs to for example restart service, reboot or other stuff
`sudo crontab - e`

then

`55  *   *   *   * systemctl restart monitor.service`

The above cron expression runs at hh.55 every hour. [Cron expression examples](http://docwiki.embarcadero.com/Connect/en/Writing_a_CRON_Expression#CRON_Expression_Examples)

### Command cli for non Hass.io users
* [hassctl](https://github.com/dale3h/hassctl)