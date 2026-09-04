---
description: "September 2026."
tab_title: "September 2026 - Logs - Zhifeng"
---

# September 3rd, 2026, Sunny

The weather has been a bit unpredictable lately. I'm starting to get worried about the upcoming winter.

## Restarting an old server

According to the logs, the database failed to start after a reboot months ago. Interesting...

It turns out I needed to restart the database service and switch from "US/Central" to "localtime" for certain entries in the `postgresql` configuration file.

**Reference Link:** [Stack Overflow](https://stackoverflow.com/questions/65092546/postgresql-invalid-data-directory-cant-open-pid-file-var-run-postgresql-10)

**Helpful commands:**
```bash
pg_lsclusters
sudo chmod 700 -R /var/lib/postgresql/$YOUR_POSTGRESQL_VERSION/main
sudo -i -u postgres
/usr/lib/postgresql/$YOUR_POSTGRESQL_VERSION/bin/pg_ctl restart -D /var/lib/postgresql/$YOUR_POSTGRESQL_VERSION/main
```

# September 2nd, year 2026, Sunny

Had a nightmare yesterday.

## Recent Fortune Cookies

- Approach life with bold enthusiasm.
- Seek out new passions.
- Never forget how much you are loved.
- There is enough to go around
- A former acquaintance will unexpectedly resurface.