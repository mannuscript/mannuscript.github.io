In this article I will be sharing my experience of using MySQL concat function for multiple purposes like creating insert queries and curl requests from existing data in MySql tables.

But before dwelling into the queries I wrote, let's understand the use of concat function:


**concat function** is used to concatenate strings in your sql query. 

`mysql> select concat('my', 'first', 'query') as firstQuery;`

Output:

    +----------------+
    | firstQuery     |
    +----------------+
    | myfirstquery   |
    +----------------+
    1 row in set (0.00 sec)




##concat\_ws
Another flavor of concat function is **concat\_ws** which stands for **concatenate with separator** and takes a separator character as first argument and inserts the separator between the strings to be concatenated.

 
`mysql> select concat_ws(' ','Already','feels', 'like', 'a', 'DBA');`

(Using space as separator)

    +------------------------------------------------------+
    | concat_ws(' ','Already','feels', 'like', 'a', 'DBA')     |
    +------------------------------------------------------+
    | Already feels like a DBA                             |
    +------------------------------------------------------+
    1 row in set (0.00 sec)


##Using concat in queries:
This is how one can use concat to concatenate strings with values from mysql rows:

`select concat('Your user id is: ', id) as id from users where user_email = 'mannu1200@gmail.com';`

Output:
    
    +----------------------+
    | id                   |
    +----------------------+
    | Your user id is: 42  |
    +----------------------+
    1 row in set (0.10 sec)

Here id and user_email are columns from the users table. This query shows how column name can be an argument of concat function.

Now since you have become a pro and feels like applying for DBA position, let's examine some of the use case for which I used concat function:

##A)Creating insert queries:
When I needed to copy some data from table A to table B:

`select concat('insert into tableB(app_txn_id,order_id) values(', app_txn_id, ',', order_id) from tableA where ts_senttime between "2016-10-20 00:00:00" and "2016-10-20 18:00:00" limti 5;`

This query is straightforward, it takes app\_txn\_id and order\_id from tableA and concat the values into "insert query string".

##B)Making Curl Requests:
Query for creating curl requests, appending column values into query params of the URL.

`select concat('curl -k "https://localhost:4242/v1/order/check?order_id=', order_id, '&status=', status, '"') from sales_order_item where created_at > "2016-10-20 00:00:00";`

These are the small hacks for which I used concat function depending upon the needs.

Comment if you are able to use concat function in more creative way...
