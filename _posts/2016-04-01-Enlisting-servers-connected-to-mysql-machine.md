Few days back our [DBA](http://dbpandit.com) updated the DNS entry of one of the slave to point it to newly created machine, with better configuration and disk space.

Now we were required to switch all mysql connections (built by our app servers) from old machine to new one.

`show processlist` gave me huge list of connections which made the enlisting of unique servers a tedious task. Hence I spent some time and wrote this query:

`select count(1), user, substring(host, 1, length(host) - 6) as host from information_schema.processlist group by substring(host, 1, length(host) - 6);`



    Where
    user : User through which your host is connected to mysql server.
    host : host machine's DNS/IP
    substring(host,1,length(host)-6) : To remove the port number from the host.

**Output:**

        +----------+----------+------------------------------+
    | count(1) | user     | host                         |
    +----------+----------+------------------------------+
    |        1 | random | XX.XX.X.XXX                  |
    |       20 | random | randomXXXXXXX.XXX.ptm      |
    |       20 | random | randomXXXXXXX.XXX.ptm      |
    |        2 | random | randomXXXXXXX.XXX.ptm  	 |
    |        2 | random | randomXXXXXXX.XXX.ptm  	 |
    |        2 | random | randomXXXXXXX.XXX.ptm  	 |
    |        2 | random | randomXXXXXXX.XXX.ptm  	 |
    |        4 | random | randomXXXXXXX.XXX.ptm 	 |
    |        8 | random | randomXXXXXXX.XXX.ptm 	 |
    |        7 | random | randomXXXXXXX.XXX.ptm 	 |
    |        6 | random | randomXXXXXXX.XXX.ptm 	 |
    |       19 | random | randomXXXXXXX.XXX.ptm   	 |
    |       13 | random | randomXXXXXXX.XXX.ptm   	 |
    |       44 | random | randomXXXXXXX.XXX.ptm      |
    |       42 | random | randomXXXXXXX.XXX.ptm      |
    |       47 | random | randomXXXXXXX.XXX.ptm      |
    |       50 | random | randomXXXXXXX.XXX.ptm      |
    |       54 | random | randomXXXXXXX.XXX.ptm      |
    |       52 | random | randomXXXXXXX.XXX.ptm      |
    |        2 | random | randomXXXXXXX.XXX.ptm  	 |
    +----------+----------+------------------------------+
