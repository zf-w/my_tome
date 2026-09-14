---
description: "September 2026."
tab_title: "September 2026 - Logs - Zhifeng"
---

# Saturday, September 12th, 2026

## Fortune Cookies

- A former acquaintance will unexpectedly resurface.
- You are guided by love and friendship.
- You will discover the importance of a smile.
- Your kind attitude will keep others afloat.
- Your generosity never ceases to impress those around you.

# Thursday, September 10th, 2026, Rainy

## Floor Cleaning

I’ve been meaning to clean the floor for a while, and I'm grateful I finally had some time to at least start. My previous roommate's mop has been there for a year. I removed the cleaning wipes, which had already dried out—it seems my roommate didn't close the lid tightly, so all the other tissues in the box went dry as well. I actually appreciate the medicinal smell they give off; it provides a real sense of tidiness.

## Chatting with Claude about using Memory-hard KDF to make work-sealed messages

It was quite interesting to learn a few ways to seal a message with either computational work or time. One method builds upon the difficulty of factoring a large number. Even though work-sealed messages might not be highly effective against surveillance, Claude agreed that they could reshape how people communicate with each other a bit.

## Reviewing Firefox Hardening

I re-searched the Internet and reviewed the repositories about hardening Firefox. I'm grateful there are resources like those.

- https://github.com/yokoffing/Betterfox
- https://github.com/arkenfox/user.js/
- https://github.com/Renatoissance/firefox-hardening-guide

## Brewing Coffee

I tried heating the water in the lower part of the brewer first. I wonder how different starting temperatures might affect the final brew.

# Friday, September 4th, 2026, Sunny

## Mounting as Home Directory

I tried using a virtual disk for a 'plug-in' home directory. Initially, I thought 16GiB would be sufficient, but the space filled up quickly. I tried to mount a larger disk and copy all the files to it, but it didn't work at first. I learned that I needed to use a special command to copy all the hidden information and attributes. I’m grateful it worked in the end!

# Thursday, September 3rd, 2026, Sunny

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