# BANDIT LEVEL 21 -> LEVEL 22

# Objetivo 

A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

## Commands you may need to solve this level

cron, crontab, crontab(5) (use “man 5 crontab” to access this)

# Datos de acceso

USERNAME: **bandit21**
PASSWORD:  WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff


# Solución
-  ls -la /etc/cron.d/
- cat /etc/cron.d/cronjob_bandit22
	- @reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
	** * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null*
-  cat /usr/bin/cronjob_bandit22.sh
	-#!/bin/bash
	chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
	cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
- cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
	- WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff



# Notas adicionales
