sqlite-headstart
# SQLite - Headstart

Based on "" at https://www.hostnextra.com/kb/how-to-install-sqlite3-on-centos-7/

## 100 - Install SQLite

In short, check the latest version on https://www.sqlite.org/download.html (here: sqlite-autoconf-3350500.tar.gz)

```
$ wget http://www.sqlite.org/2021/sqlite-autoconf-3350500.tar.gz
--2021-05-28 11:18:16--  http://www.sqlite.org/2021/sqlite-autoconf-3350500.tar.gz
Resolving www.sqlite.org (www.sqlite.org)... 2600:3c00::f03c:91ff:fe96:b959, 45.33.6.223
Connecting to www.sqlite.org (www.sqlite.org)|2600:3c00::f03c:91ff:fe96:b959|:80... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2956627 (2.8M) [application/x-gzip]
Saving to: ‘sqlite-autoconf-3350500.tar.gz’

100%[=============================================================================================>] 2,956,627   3.67MB/s   in 0.8s   

2021-05-28 11:18:17 (3.67 MB/s) - ‘sqlite-autoconf-3350500.tar.gz’ saved [2956627/2956627]

```
