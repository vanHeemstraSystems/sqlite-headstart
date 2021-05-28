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

Uncompress the tar.gz file and install SQLite3 as shown below.

```
$ tar xvfz sqlite-autoconf-3350500.tar.gz
$ cd sqlite-autoconf-3070603
$ ./configure
$ make
$ make install
```

```make install``` command will displays the following output indicating that it is installing sqlite3 binaries under ```/usr/local/bin```

```
...
Libraries have been installed in:
   /usr/local/lib

If you ever happen to want to link against installed libraries
in a given directory, LIBDIR, you must either use libtool, and
specify the full pathname of the library, or use the '-LLIBDIR'
flag during linking and do at least one of the following:
   - add LIBDIR to the 'LD_LIBRARY_PATH' environment variable
     during execution
   - add LIBDIR to the 'LD_RUN_PATH' environment variable
     during linking
   - use the '-Wl,-rpath -Wl,LIBDIR' linker flag
   - have your system administrator add LIBDIR to '/etc/ld.so.conf'

See any operating system documentation about shared libraries for
more information, such as the ld(1) and ld.so(8) manual pages.
----------------------------------------------------------------------
 /bin/mkdir -p '/usr/local/bin'
  /bin/sh ./libtool   --mode=install /bin/install -c sqlite3 '/usr/local/bin'
libtool: install: /bin/install -c sqlite3 /usr/local/bin/sqlite3
 /bin/mkdir -p '/usr/local/include'
 /bin/install -c -m 644 sqlite3.h sqlite3ext.h '/usr/local/include'
 /bin/mkdir -p '/usr/local/share/man/man1'
 /bin/install -c -m 644 sqlite3.1 '/usr/local/share/man/man1'
 /bin/mkdir -p '/usr/local/lib/pkgconfig'
 /bin/install -c -m 644 sqlite3.pc '/usr/local/lib/pkgconfig'
make[1]: Leaving directory `/home/cloud_user/sqlite3/sqlite-autoconf-3350500'
```

## 200 - Create a sample SQLite database
The example shown below does the following:

- Create a new SQLite database called “company.db”.
- Create “employee” table with three fields 1) Employee Id 2) Name and 3) Title
- Insert 5 records into the employee tables.
- Verify the records
- Exit SQLite3

```
$ sqlite3 company.db
SQLite version 3.7.6.3
Enter ".help" for instructions
Enter SQL statements terminated with a ";"

sqlite> create table employee(id integer,name varchar(20),title varchar(10));

sqlite> insert into employee values(101,'John Smith','CEO');
sqlite> insert into employee values(102,'Raj Reddy','Sysadmin');
sqlite> insert into employee values(103,'Jason Bourne','Developer');
sqlite> insert into employee values(104,'Jane Smith','Sale Manager');
sqlite> insert into employee values(104,'Rita Patel','DBA');

sqlite> select * from employee;
101|John Smith|CEO
102|Raj Reddy|Sysadmin
103|Jason Bourne|Developer
104|Jane Smith|Sale Manager
104|Rita Patel|DBA

sqlite>[Press Ctrl-D to exit]
```



