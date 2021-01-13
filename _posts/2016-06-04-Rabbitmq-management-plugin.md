This is 3rd blog of Series [Getting started with Rabbitmq](http://mannumalhotra.in/tag/rabbitmq/) 
in which I am trying to explain how rabbitMq management plugin can make your life more interesting.

RabbitMq ships with a bunch of crucial plugins and [RabbitMq management](https://www.rabbitmq.com/management.html) being one of them. It provides you the set of APIs, a management panel and **rabbitmqadmin** a command line tool for administrating and managing rabbitMq server.

######Enabling the plugin:

`rabbitmq-plugins list` will enlist the default plugins as well as the additional plugins installed in your system.

**Output:**

    Configured: E = explicitly enabled; e = implicitly enabled
     | Status:   * = running on rabbit@197NODNB
     |/
    [e*] amqp_client                       3.6.1
    [  ] cowboy                            1.0.3
    [  ] cowlib                            1.0.1
    [e*] mochiweb                          2.13.0
    [  ] rabbitmq_amqp1_0                  3.6.1
    [  ] rabbitmq_auth_backend_ldap        3.6.1
    [  ] rabbitmq_auth_mechanism_ssl       3.6.1
    [  ] rabbitmq_consistent_hash_exchange 3.6.1
    [E ] rabbitmq_delayed_message_exchange 0.0.1
    [  ] rabbitmq_event_exchange           3.6.1
    [  ] rabbitmq_federation               3.6.1
    [  ] rabbitmq_federation_management    3.6.1
    [E*] rabbitmq_management               3.6.1
    [e*] rabbitmq_management_agent         3.6.1
    [  ] rabbitmq_management_visualiser    3.6.1
    [  ] rabbitmq_mqtt                     3.6.1
    [  ] rabbitmq_recent_history_exchange  1.2.1
    [  ] rabbitmq_sharding                 0.1.0
    [  ] rabbitmq_shovel                   3.6.1
    [  ] rabbitmq_shovel_management        3.6.1
    [  ] rabbitmq_stomp                    3.6.1
    [  ] rabbitmq_tracing                  3.6.1
    [e*] rabbitmq_web_dispatch             3.6.1
    [  ] rabbitmq_web_stomp                3.6.1
    [  ] rabbitmq_web_stomp_examples       3.6.1
    [  ] sockjs                            0.3.4
    [e*] webmachine                        1.10.3

To enable the plugin:
`rabbitmq-plugins enable rabbitmq_management`
